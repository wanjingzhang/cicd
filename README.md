"# cicd"

### 常见本地自动化 在hooks阶段

git hooks

npm hooks：
post install(sass执行脚本，执行请求的发送，获取sass的相关的依赖，有可能请求其他的包所以速度会变慢，需要修改镜像)
在发布、下载阶段的回调，在里面编译，测试，eslint，pretty

通过lint-staged，可以快速在git操作阶段对事件进行执行，
配置:

* package.json{lint-staged:{"*":"your-cmd"}}
* .lintstagedrc {"*":"your-cmd"}
匹配到左边的*内容，就会执行右边的指令。 *.js 如果修改了js文件，会执行yarn test的命令

安装依赖了husky库
 yarn add lint-staged husky -S
添加husky在package.json

git add .
git commit -m "test"
git commit -m "绕过test" -n

ci
实际上在中心化git服务器上做这些操作。比起本期更加安全，本地可以绕过-n检查。
在远端进行操作，Travis.CI circle.CI,Travis要收费的1美元 然后过几天再还回来。
