# Docker-PrinterNightmare

A docker image for the PoC python impacket implementation of CVE-2021-1675 by cube0x0.

The python PoC is not mine and is located at https://github.com/cube0x0/CVE-2021-1675

## Why is this useful?

If you already have an existing impacket install and don't want to remove it, you can use this so that the PoC works. It runs the authors custom version of impacket in docker so there are no conflicts.

Instructions:

Must be run on Linux. Required packages:

- Docker
- git (so things can be cloned)

1. Create a new folder and put the dockerfile inside of it. Then run the following commands AS ROOT OR WITH SUDO/ELEVATED PRIVILEGES:

```
docker build -f CVE-2021-1675.docker -t cve-2021-1675 ./
docker run -it --rm cve-2021-1675
```


2. A shell (/bin/bash/) will spawn and you can now run the PoC:

```
cd CVE-2021-1675
python3 CVE-2021-1675.py
```