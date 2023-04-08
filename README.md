# Worker setup
- Get docker service location with `sudo systemctl status ssh`
- Add `-H tcp://0.0.0.0:2375`
- Restart Docker `sudo systemctl daemon-reload; sudo systemctl restart docker.service`
- Watch traffic on 2375 `sudo tcpdump -i any port 2375`
- Open up port 2375 `sudo iptables -A DOCKER -d 0.0.0.0/0 -p tcp --dport 2375 -j ACCEPT`
