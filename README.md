***This is a fork to make releases of gpt4free ARM64 docker images available***


Tested on Ubuntu.
Requirements
1. docker
2. qemu-user-static

![248433934-7886223b-c1d1-4260-82aa-da5741f303bb](https://github.com/xtekky/gpt4free/assets/98614666/ea012c87-76e0-496a-8ac4-e2de090cc6c9)
Written by [@xtekky](https://github.com/hlohaus) & maintained by [@hlohaus](https://github.com/hlohaus)

<div id="top"></div>


To get started:

Install qemu-user-static

```sh
apt install -y qemu-user-static
```

Download the ARM64 image

```sh
docker pull ghcr.io/rhee876527/gpt4free-arm:latest
```
or

```sh
docker pull ghcr.io/rhee876527/gpt4free-arm:0.2.0.3
```

Sample compose to get started:

```services:
  gpt4free:
    container_name: gpt4free
    image: ghcr.io/rhee876527/gpt4free-arm:latest
    volumes:
      - ./:/app
    shm_size: 2gb
    cap_drop:
      - ALL
    restart: unless-stopped
    security_opt:
      - no-new-privileges
    environment:
      - LOGGING=True  #True or False
#      - CHAT_PROXY=http://127.0.0.1:10082  # your http proxy url
    ports:
      - '1337:1337'
      - 'whatever*port*you*want:8080'
      - '7900:7900'
```









> By using this repository or any code related to it, you agree to the [legal notice](LEGAL_NOTICE.md). The author is not responsible for any copies, forks, re-uploads made by other users, or anything else related to GPT4Free. This is the author's only account and repository. To prevent impersonation or irresponsible actions, please comply with the GNU GPL license this Repository uses.


