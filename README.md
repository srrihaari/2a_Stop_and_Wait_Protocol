# 2a_Stop_and_Wait_Protocol
## AIM 
To write a python program to perform stop and wait protocol
## ALGORITHM
1. Start the program.
2. Get the frame size from the user
3. To create the frame based on the user request.
4. To send frames to server from the client side.
5. If your frames reach the server it will send ACK signal to client
6. Stop the Program
## PROGRAM
## CLIENT:
```
import socket
s=socket.socket()
s.bind(('localhost',8000))
s.listen(5)
c,addr=s.accept()
while True:
    i=input("Enter a data: ")
    c.send(i.encode())
    ack=c.recv(1024).decode()
    if ack:
        print(ack)
        continue
    else:
        c.close()
        break
```
## SERVER:
```
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True:
    print(s.recv(1024).decode())
    s.send("Acknowledgement Recived".encode())
```

## OUTPUT
![WhatsApp Image 2024-05-10 at 11 49 30_e107a092](https://github.com/srrihaari/2a_Stop_and_Wait_Protocol/assets/145550674/1f0c9b37-15d7-4e26-8cec-f672c25b705d)

![WhatsApp Image 2024-05-10 at 11 49 33_89cd9d94](https://github.com/srrihaari/2a_Stop_and_Wait_Protocol/assets/145550674/1fcea408-ec63-47f9-91ef-75cf450339fc)


## RESULT
Thus, python program to perform stop and wait protocol was successfully executed.
