WAF Test Project 

1. HTTP packet tool - HTTP.pl
Usage http://danqingdani.blog.163.com/blog/static/18609419520144202591392/

2. HTTP packet tool - HTTPFromFile.pl
read HTTP Request from file and send it

For example: send a xss request to test if the WAF can block

I: construct request package content

echo -ne 'GET /?a=%3Cscript%3Ealert(1)%3C/script%3E HTTP/1.1\r\nHost: www.tanjiti.com\r\nUserAgent: curl 0.9\r\n' >xss.t

II: send xss request use HTTPFromFile.pl

perl HTTPFromFile.pl -code 403 -host www.tanjiti.com -port 80 -file xss.t

WAF Evauation Method detail http://danqingdani.blog.163.com/blog/static/1860941952014101462723470/ 
