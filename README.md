
# 二进制文件下载地址：[release](https://github.com/xkznks/crack-soga/releases)


## 一键安装

``` bash
bash < <(curl -Ls https://raw.githubusercontent.com/xkznks/crack-soga/main/install.sh)
```

## 同步时间：
```
yum install -y ntp
systemctl enable ntpd
ntpdate -q 0.rhel.pool.ntp.org
systemctl restart ntpd
```

## 节点格式：
```
ip;80;2;ws;;path=/xxx|server=域名|host=CDN域名
```
编辑 /etc/soga/soga.conf

## 启动soga：
```
soga start
```
## Docker安装
```
yum install -y yum-utils
yum-config-manager \
    --add-repo \
    https://download.docker.com/linux/centos/docker-ce.repo
yum install docker-ce docker-ce-cli containerd.io -y
systemctl start docker
systemctl enable docker
```
```
# 拉取镜像
docker pull rmanluo/crack-soga
# 运行镜像，参数请参考soga自带教程。
docker run --restart=always --name crack-soga -d -v /etc/soga/:/etc/soga/ --network host rmanluo/crack-soga \
--type=sspanel-uim \
--server_type=v2ray \
--api=webapi \
--webapi_url=https://xxx.com/ \
--webapi_mukey=xxx \
--soga_key=cracked_by_RMan \
--node_id=1
```

