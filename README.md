# 3a.CREATION FOR ECHO CLIENT AND ECHO SERVER USING TCP SOCKETS
# AIM
To write a python program for creating Echo Client and Echo Server using TCP
Sockets Links.
## ALGORITHM:
1. Import the necessary modules in python
2. Create a socket connection to using the socket module.
3. Send message to the client and receive the message from the client using the Socket module in
 server .
4. Send and receive the message using the send function in socket.
## PROGRAM
server
```
import socket

s = socket.socket(socket.AF_INET, socket.SOCK_STREAM)

s.bind(('localhost', 8000))
s.listen(5)

print("Server is waiting for connection...")

c, addr = s.accept()

print("Connected to:", addr)

while True:
    msg = c.recv(1024).decode()

    if not msg or msg.lower() == 'exit':
        break

    print("Client >", msg)
    c.send(msg.encode())

c.close()
s.close()
```
client
```
import socket

s = socket.socket(socket.AF_INET, socket.SOCK_STREAM)

s.connect(('localhost', 8000))

while True:
    msg = input("Client > ")

    if msg.lower() == 'exit':
        break

    s.send(msg.encode())

    print("Server >", s.recv(1024).decode())

s.close()
```
## OUPUT
<img width="886" height="398" alt="image" src="https://github.com/user-attachments/assets/2e0364bf-2af3-41c2-bd8f-e39933182a84" />


## RESULT
Thus, the python program for creating Echo Client and Echo Server using TCP Sockets Links 
was successfully created and executed.
