# EX01 Developing a Simple Webserver
## Date: 11-11-2026
## REG NO:26000807

## AIM:
To develop a simple webserver to serve html pages and display the list of protocols in TCP/IP Protocol Suite.

## DESIGN STEPS:
### Step 1: 
HTML content creation.

### Step 2:
Design of webserver workflow.

### Step 3:
Implementation using Python code.

### Step 4:
Import the necessary modules.

### Step 5:
Define a custom request handler.

### Step 6:
Start an HTTP server on a specific port.

### Step 7:
Run the Python script to serve web pages.

### Step 8:
Serve the HTML pages.

### Step 9:
Start the server script and check for errors.

### Step 10:
Open a browser and navigate to http://127.0.0.1:8000 (or the assigned port).

## PROGRAM:
~~~
from http.server import HTTPServer, BaseHTTPRequestHandler

content = """<!DOCTYPE html>
<html>
<head><title>TCP/IP Protocol Suite</title></head>
<body style="font-family:sans-serif; margin:30px;">
    <h1>TCP/IP Protocol Suite</h1>
    <h3>1. Application Layer</h3>
    <ul><li>HTTP/HTTPS (Web)</li><li>DNS (Name Resolution)</li><li>SMTP (Email)</li></ul>
    <h3>2. Transport Layer</h3>
    <ul><li>TCP (Connection-oriented)</li><li>UDP (Connectionless)</li></ul>
    <h3>3. Internet Layer</h3>
    <ul><li>IP (Routing & Addressing)</li><li>ICMP (Diagnostics)</li><li>ARP (Address Resolution)</li></ul>
    <h3>4. Network Access Layer</h3>
    <ul><li>Ethernet (Wired)</li><li>Wi-Fi (Wireless)</li></ul>
</body>
</html>"""

class myhandler(BaseHTTPRequestHandler):
    def do_GET(self):
        self.send_response(200)
        self.send_header('content-type', 'text/html; charset=utf-8')
        self.end_headers()
        self.wfile.write(content.encode())

print("Server running on http://localhost:680 ...")
HTTPServer(('', 680), myhandler).serve_forever()

~~~


## OUTPUT:
![alt text](<Screenshot 2026-11-03 140342.png>)
![alt text](<Screenshot 2026-11-03 140402.png>)

## RESULT:
The program for implementing simple webserver is executed successfully.

