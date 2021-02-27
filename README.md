# Heroku rclone
## 概述
用于在 Heroku 上部署 rclone。
## 部署rclone
[![Deploy](https://www.herokucdn.com/deploy/button.png)](https://dashboard.heroku.com/new?template=https://github.com/wellsyue/heroku-rclone.git)
## 部署rclone+6pan
[![Deploy](https://www.herokucdn.com/deploy/button.png)](https://dashboard.heroku.com/new?template=https://github.com/wellsyue/heroku-rclone.git/tree/6pan)
## ENV 设定
### config
rclone config文件内容
## 运行
### 安装heroku、连接终端
```
curl https://cli-assets.heroku.com/install-ubuntu.sh | sh
heroku run bash -a myapp
```
### 运行rclone
#### 加载rclone配置
```
bash configure.sh
```
#### 编辑rclone配置
```
rclone config
```
### 运行fclone
```
fclone
```
### 运行six-cli
```
six login
```
### fclone自动化复制
```shell
heroku run "bash configure.sh && fclone -P copy 1:1 2:1 --drive-server-side-across-configs --stats=1s --stats-one-line -vP --checkers=256 --transfers=256 --drive-pacer-min-sleep=1ms --check-first"  -a myapp
```
