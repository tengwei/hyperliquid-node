This file contains optional configuration. Refer to `README.md` the essential information.

## Running as a System Service
Many node operators prefer to run the node as a system service.

Create the system service config file:
```
sudo nano /etc/systemd/system/hl-visor.service
```

Add the required information to the config, replace ALL instances of USERNAME:
```
[Unit]
Description=HL-Visor Non-Validator Service
After=network.target

[Service]
Type=simple
User=USERNAME
WorkingDirectory=/home/USERNAME
ExecStart=/home/USERNAME/hl-visor run-non-validator
Restart=always
RestartSec=10

[Install]
WantedBy=multi-user.target

```
Enable the service:
```
sudo systemctl enable hl-visor.service
```

Start the service:
```
sudo systemctl start hl-visor
```

And finally to follow the logs use command:
```
journalctl -u hl-visor -f
```

### Running with Docker
To build the node, run:

```bash
docker compose build
```

```bash
docker-compose build
```

To run the node, run:

```bash
docker compose up -d
```

```bash
docker-compose up -d
```
sudo docker exec -it 92b1b94f1ae8 /bin/bash


ps aux | grep hl-visor

ps aux | grep hl-node

RUST_LOG=DEBUG

RUST_LOG=DEBUG ./hl-visor run-non-validator --write-trades --write-order-statuses --serve-eth-rpc

RUST_LOG=DEBUG ./hl-node --chain Mainnet run-non-validator  --write-trades --write-order-statuses --serve-eth-rpc --actions-and-responses


./hl-node --chain Mainnet run-validator

lsof -p 43335


netstat -an | grep :20944
netstat -an | grep 4000
netstat -an | grep 4001
netstat -an | grep 4002
netstat -an | grep 4003
netstat -an | grep 4004
netstat -an | grep 4005
netstat -an | grep 4006
netstat -an | grep 4007
netstat -an | grep 4008
netstat -an | grep 4009
netstat -an | grep 4010


ss -tulnp | grep 4007


wscat -c ws://57.182.103.24:4001/ws


tcpdump -i any port 4001 -vvv -X


netstat -an | grep 3999


sudo tcpdump -i any port 4001 -w capture.pcap
sudo tcpdump -i any port 8080 -A
sudo tcpdump -i any host 192.168.1.100 -A


tcpdump -r capture.pcap -A


scp root@8.211.158.224:/root/capture.pcap ./


