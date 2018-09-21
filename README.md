# GitLab 社区版

----------

# 1、参数配置

1、配置URL（必须）
  
配置http模式下的external url，格式如:http://ip，或者http://域名

2、端口配置（可选）
 
- http模式的访问端口，默认80
- https模式的访问端口，默认443
- ssh访问端口，默认22

3、容器数据（可选）
  
Docker容器数据应该存储于卷中，在这里我们使用最简单的本地命名卷：

* `gitlab-config` 存储 GitLab 配置信息，默认映射路径：/srv/gitlab/config
* `gitlab-data` 存储数据库，默认映射路径：/srv/gitlab/data
* `gitlab-logs` 存储日志，默认映射路径：/srv/gitlab/logs

4、GITLAB_OMNIBUS_CONFIG参数配置（可选）
  
  GITLAB_OMNIBUS_CONFIG参数就是gitlab.rb中的参数集合。

  配置格式如下：

          external_url 'http://gitlab.example.com'
          gitlab_rails['time_zone'] = 'Asia/Shanghai'
          # 需要配置到 gitlab.rb 中的配置可以在这里配置，每个配置一行，注意缩进。
          # 比如下面的电子邮件的配置：
          # gitlab_rails['smtp_enable'] = true
          # gitlab_rails['smtp_address'] = "smtp.exmail.qq.com"
          # gitlab_rails['smtp_port'] = 465
          # gitlab_rails['smtp_user_name'] = "xxxx@xx.com"
          # gitlab_rails['smtp_password'] = "password"
          # gitlab_rails['smtp_authentication'] = "login"
          # gitlab_rails['smtp_enable_starttls_auto'] = true
          # gitlab_rails['smtp_tls'] = true
          # gitlab_rails['gitlab_email_from'] = 'xxxx@xx.com'



# 2、运行

从应用商店下载并成功运行后，GitLab会启动数据配置，这个时间大约需要2~3分钟，这2~3分钟内无法登录Web UI，直到数据配置完成。


# 3、登录

启动 GitLab 后，第一次访问时，会要求设置 `root` 用户的密码，密码不得小于8位。设置好后，就可以登录使用了。

对于早期版本，可以使用默认的 `root` 用户密码 `5iveL!fe` 登录。


# 4、相关信息

* GitLab Docker 相关操作请参考：<http://docs.gitlab.com/omnibus/docker/>
* GitLab 官方英文社区版 Docker 镜像：<https://hub.docker.com/r/gitlab/gitlab-ce/>
* GitLab 官方英文企业版 Docker 镜像：<https://hub.docker.com/r/gitlab/gitlab-ee/>
