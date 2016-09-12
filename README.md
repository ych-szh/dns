## 说明
供墙内用户使用google youtube 都可以，有问题发issue

## 使用方法
1. 首先安装好[docker](https://www.docker.com/products/docker#/mac)

2. 启动dns服务
```
# 直接执行命令，不用拉取项目
docker run -d --name dns -p 53:53/tcp -p 53:53/udp --cap-add=NET_ADMIN firesh/dns --log-facility=-
```

3. 设置dns，本机设置dns为127.0.0.1即可。

## Build
```
docker build -t dns . &&\
docker run -d --name dns -p 53:53/tcp -p 53:53/udp --cap-add=NET_ADMIN dns --log-facility=-
```

## 申明
- IP封一个少一个，仅供技术人员自行使用，请勿发布公网使用。
- dnsmasq配置来源：[https://github.com/fengixng/google-hosts](https://github.com/fengixng/google-hosts)