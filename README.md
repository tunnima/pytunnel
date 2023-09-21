map: https://github.com/tunnima/my-docs
```text
روی همراه اول تست نشده
```
# installation:
https://pypi.org/project/pytunnel/

**server A.A.A.A:**
```text
python3 -m pytunnel --bind 0.0.0.0:8001
```
**client B.B.B.B:**
```text
python3 -m pytunnel --port 3124 --target 127.0.0.1:4445 --server 37.152.185.228:8002
```

# MAIN:
pytunnel
===============
A TCP tunnel server/client by Python.

Install
===============
```
 pip install pytunnel
```

Useage
===============
If you want local computer port 8080 can be access through server(IP:192.168.1.102) port 1090

Setp1. Run the following command at server computer:

```bash
python -m pytunnel --bind 0.0.0.0:1990
```

It will start a tunnel server at port 1990.

Setp2. Run the following command at local computer:
```bash
python -m pytunnel --port 1090 --target 127.0.0.1:8080 --server 192.168.1.102:1990
```

It will make a tunnel with 192.168.1.102:1090 and 127.0.0.1:8080.

Now, you can open 192.168.1.102:1090 to access the local computer port 8080.

Other
===============

You can use ```-e``` to set the password:

```bash
# server
python -m pytunnel --bind 0.0.0.0:1990 -e "abcdef"
# client
python -m pytunnel --port 1090 --target 127.0.0.1:8080 --server 192.168.1.102:1990 -e "abcdef"
```

Client can use ```-c``` to excute a command at the server computer:

```bash
# show server status
python -m pytunnel --server 192.168.1.102:1990 -c "status"

# let server exit
python -m pytunnel --server 192.168.1.102:1990 -c "exit"

# kill some client, the client-key can found with "status" command
python -m pytunnel --server 192.168.1.102:1990 -c "kill client-key"
```

[Click to view more information!](https://github.com/sintrb/pytunnel)
