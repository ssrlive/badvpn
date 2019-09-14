# Tun2socks network-layer proxifier

The tun2socks program "socksifes" TCP connections at the network layer.
It implements a TUN device which accepts all incoming TCP connections (regardless of destination IP), and forwards the connections through a SOCKS server.
This allows you to forward all connections through SOCKS, without any need for application support.
It can be used, for example, to forward connections through a remote SSH server.

## Introduction

It was originally [Badvpn Tun2socks](https://github.com/bemasc/badvpn). [Shadowsocks](https://github.com/shadowsocks/badvpn) implemented it on Android,and used udpgw to realize UDP conversion. Now I refer to [bemasc](https://github.com/bemasc/badvpn/tree/bemasc-udp) to add SOCKS UDP ASSOCIATE to it.

## Requirements

Tun2socks works on Android(Platform target android-18 or above) and Linux(Not tested,please use [badvpn bemasc-udp branch](https://github.com/bemasc/badvpn/tree/bemasc-udp))
--socks5-udp use SOCKS UDP ASSOCIATE,do not use it with --enable-udprelay and --udpgw-remote-server-addr

## Installation

```
cd tun2socks dir
ndk-build
```

```
libtun2socks --netif-ipaddr <netif-ipaddr> --socks-server-addr=<socks-server-addr> --sock-path=<sock-path> --socks5-udp
```
