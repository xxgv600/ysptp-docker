docker compose安装命令：
services:
  ysp-live:
    image: ghcr.io/xxgv600/ysptp-docker:latest
    container_name: ysp-live
    restart: unless-stopped
    ports:
      - "8767:8767"
    volumes:
      - ./data:/app/data
    environment:
      - TZ=Asia/Shanghai
      - PYTHONUNBUFFERED=1
      - YSP_DATA_DIR=/app/data

然后：
docker compose up -d
docker logs -f ysp-live
