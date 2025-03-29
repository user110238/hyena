FROM debian:bullseye-slim

RUN apt-get update && apt-get install -y --no-install-recommends \
    suricata \
    iproute2 \
    libnetfilter-queue1 \
    iptables \
    && apt-get clean \
    && rm -rf /var/lib/apt/lists/*

EXPOSE 80 443 22

RUN mkdir -p /etc/suricata/rules /var/log/suricata /config

COPY entrypoint.sh /usr/local/bin/entrypoint.sh
RUN chmod +x /usr/local/bin/entrypoint.sh
ENTRYPOINT ["/usr/local/bin/entrypoint.sh"]
