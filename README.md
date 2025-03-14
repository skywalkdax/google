# google
```
services:
  chromium:
    image: lscr.io/linuxserver/chromium:latest
    container_name: chromium
    security_opt:
      - seccomp:unconfined #optional
    environment:
      - CUSTOM_USER=WEEK
      - PASSWORD=admin@123
      - PUID=1000
      - PGID=1000
      - TZ=Europe/London
      - CHROME_CLI=https://github.com/skywalkdax #optional
    volumes:
      - /root/chromium/config:/config
    cap_add:
      - NET_ADMIN
    ports:
      - 3010:3000   #Change 3010 to your favorite port if needed
      - 3011:3001   #Change 3011 to your favorite port if needed
    shm_size: "2gb"
    restart: unless-stopped
```
