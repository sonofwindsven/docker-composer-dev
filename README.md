# 简介
这是一个docker-compose的开发环境，使用者可以根据自己本地环境的开发目录配置volumes参数。数据库容器可以配置root密码和新用户。

# 安装
- 安装 `docker` 参考菜鸟教程： `https://www.runoob.com/docker/windows-docker-install.html`
- 安装 `docker-commpose` 参考菜鸟教程： `https://www.runoob.com/docker/docker-compose.html`

# 初始化镜像
- 切换到`php`目录下执行 `docker build -t "php:dev" ./`
- 切换到`golang`目录下执行`docker build -t "golang:dev" ./`

# 配置
使用者可以根据自己实际情况做如下修改：
- version 根据自己本地的docker-compose版本进行调整
- 可以修改services下面每个服务的 `ports`、`volumes`参数
- web、php服务我这里将/Users/changchaofeng/nginx/www开发目录，映射到 容器里面的 /www 目录下，同时将日志文件映射
- db服务可以配置`MYSQL_ROOT_PASSWORD`管理员密码等参数
- golang服务可以配置 `ports`、 `volumes`管理员密码等参数

# 运行环境
`docker-compose up -d`

# 调试
- 如果启动环境失败，可以根据 `docker-compose logs` 输出的错误信息进行调试。
- 如果改动了`docker-compose`文件，需要 `重启` 才会生效

# 常用命令
- `docker ps` 查看docker启动的容器
- `docker-compose restart` 重启
- `docker-compose stop` 关闭所有service
- `docker-compose version` 查看版本
- `docker-compose -h` 查看命令行帮助，了解更多命令