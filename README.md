### Team: 466 Crew
Taylor Bart<br>
Kamal Nadesan<br>
Matt Evans<br>
John Tiffany<br>
James Taylor<br>
*Attempted multiple challenges from Hack for the troops and Affinity CTFs. (omitted Balsn and a student CTF in my report because I had no significant results from those challenges)*
# Hack for the troops
I was able to solve one web challenge in this CTF and learned a new trick about editing cookies.<br>
### Web: SilentWater
You are presented a simple login page. At first I thought it was another sql injection attack, however the lack of output or source code anywhere made me start to doubt this assumption. I thought that possibly there was a vulnerability in the JS on the page where it was using failed=True as a get method in the http request. Since that lead to nowhere as well, I decided to see what other links I could find from this page and was able to find this:<br>
<br>
![](https://github.com/tbart27/11_16_20_writeups/blob/main/bakery.png)<br>
<br>
After messing with the logon and seeing that this had nothing to do with the flag, I decided to research other CTF methods. After a series of unrelated write ups I finally came across one that mentioned cookies. Immediately, I checked the challenge website's cookies and sure enough, there was a loggedIn=False cookie set.<br>
<br>
![](https://github.com/tbart27/11_16_20_writeups/blob/main/web1.PNG)Simply changing this cookie to true and refreshing the page was enough to allow me to get the flag<br>
<br>
`EAT_COOKIES`


# Affinity CTF
This was supposed to be an easier CTF and I was able to grab a stenography flag in this CTF.<br>
### STEGO: One is missing
A straight forward challenge where I pulled up the image in a text editor and scanned through the file until I noticed the hidden flag.<br>
<br>
![](https://github.com/tbart27/11_16_20_writeups/blob/main/stego1.PNG)<br>
<br>
`AFFCTF{HIDDENKITTEN}`

# Conclusion
Most of this CTF I ran into the same type of web problem where I would have to use a GET method from the server to return a file from the same machine. However, I didn't know the name of the file. This was literally in 3-4 different CTFs that I saw this weekend and I tried implementing URL fuzzers and trying gobuster with some wordlists but was unable to identify the server directory layouts. Early attempts of curl with spider option were also unsuccessful. Furthermore, I will start looking into the Cryptography challenges again because I am interested in Applied Cryptography and want some practice before starting that course. In Affinity, there was a simple shift cipher that I skipped and the next was named: Hongqiao. While installing the Jumbo version of John-the-ripper I installed the GPU dependencies incorrectly and this led to the system crashing. If it wasn't for this unfortunate accident, I was going to try and brute force the sha1 encryption on the message since I saw that the encrypted message was 40 characters long.<br>
<br>
My goals for future CTFs is to figure out how to map server directories and have either hashcat/John-the-ripper(Jumbo) functional so it can run in the background.
