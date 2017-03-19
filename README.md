# WordPress-vs.-Kali
WordPress different versions exploits using Kali

# Lab: FInd xss exploit in file uload during new post add
<img src="https://github.com/t17711/WordPress-vs.-Kali/blob/master/xss_atttachment.gif">

# Assignment
For assignment I used wordpress 4.2.2 version. The exploits I found with wpscan in kali linux were:

## Sqli injection
* I chose following error log

## XSS 
* in widgets customizer page, when I chose to add a text widget i got XSS 
<img src="https://github.com/t17711/WordPress-vs.-Kali/blob/master/xss_assignment.gif">
    
## CSRF
* For this i followed instruction from https://sumofpwn.nl/advisory/2016/cross_site_request_forgery_in_wordpress_press_this_function_allows_dos.html


SO i creates a web page called dos.html in localhost and filled it with this tag. My word press is in localhost:8000
* \<img src='http://localhost:8000/wp-admin/press-this.php?u=http%3A%2F%2Flocalhost%2Ffoo.txt&url-scan-submit=Scan&a=b'\> 


This makes browser download foo.txt file in my localhost server.
Then I visited the page as admin. This slowed down my server by sending a lot of press this request.
I can see the request on the docker logs.

My walk through is:
<img src='https://github.com/t17711/WordPress-vs.-Kali/blob/master/DOS_csrf.gif'>

