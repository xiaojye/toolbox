
### 🎉 What's this？
这是一款`在线工具箱`程序，您可以通过安装扩展增强她的功能  
通过插件模板的功能，您也可以把她当做网页导航来使用~    

### 😺 演示地址

* <https://wantoolx.com>

## 🎑 说明
> 严禁用于非法用途     

### 🎊 环境要求

* `PHP` >= 7.4
* `MySQL` >= 5.6
* `fileinfo`扩展
* 使用`Redis`缓存需安装`Redis`扩展

### 🚠 部署

* 设置运行目录（绑定目录）为`public`

* 设置伪静态

* Composer安装依赖
    + 配置阿里镜像源（国内服务器可选）
    ```
    composer config -g repo.packagist composer https://mirrors.aliyun.com/composer/
    ```
    + 升级compose
    ```
    composer self-update
    ```
    + 安装依赖
    ```
    composer install --no-dev
    ```
    
* 打开网站会自动跳转到安装页面，根据界面提示完成安装。

#### 🍰 伪静态

* Nginx
```
location / {
	if (!-e $request_filename){
		rewrite  ^(.*)$  /index.php?s=$1  last;   break;
	}
}
```
* Apache
```
<IfModule mod_rewrite.c>
  Options +FollowSymlinks -Multiviews
  RewriteEngine On

  RewriteCond %{REQUEST_FILENAME} !-d
  RewriteCond %{REQUEST_FILENAME} !-f
  RewriteRule ^(.*)$ index.php/$1 [QSA,PT,L]
</IfModule>
```

#### 🍓 鸣谢

* [netcccyun](https://github.com/netcccyun/toolbox)
* [aoaostar](https://github.com/aoaostar/toolbox)
* vue
* thinkphp
* layui
* layuimini
* DashLite
