先https://www.msys2.org/
安装mingw32-make命令和gcc编译器（打开mingw 64 运行pacman -Syu和pacman -S mingw-w64-x86_64-gcc）
# Socket 聊天系统

一个基于 Socket 的多用户聊天系统，支持实时消息传递和用户状态管理。

## 功能特点

- 支持多用户同时在线聊天
- 实时消息广播
- 用户在线状态显示
- Web 监控界面
- 支持中文消息

## 系统要求

- Windows 操作系统
- MinGW-w64 编译器
- Make 工具

## 编译和运行
1.mkdir obj
2.mkdir bin
3.mingw32-make
4.mingw32-make run-server（服务器）
5.用户端两种：mingw32-make run-client           运行bin/test_client.exe


## 使用说明

1. 启动服务器后，可以通过 `http://localhost:8080` 访问 Web 监控界面
2. 客户端连接默认使用 `127.0.0.1:8888`
3. 在客户端输入昵称后即可开始聊天
4. 输入 `quit` 或 `exit` 退出程序
5. 输入 `help` 查看帮助信息
6. 开放本地端口可以在其他电脑运行
   具体：1. 服务器端（A电脑）
编译并运行服务器
在A电脑上，进入项目目录，执行：
 mingw32-make
 mingw32-make run-server
查找A电脑的局域网IP地址
在A电脑上打开命令行，输入：
 ipconfig 找到“IPv4 地址”，比如 192.168.1.100。
确保防火墙允许8888端口（聊天端口）和8080端口（Web监控端口）被访问
可以临时关闭防火墙测试，或在防火墙设置中允许这两个端口的入站连接。
2. 客户端（B电脑）
获取项目代码
可以用 Git 克隆您的仓库，或直接拷贝整个项目文件夹到B电脑。
修改客户端代码，连接服务器IP
test_client改成：文件中test_client2.txt(加自己公网ip）

## 项目结构

```
chat_system/
├── include/         # 头文件
├── src/            # 源代码
├── bin/            # 编译输出目录
├── obj/            # 目标文件目录
├── web/            # Web 监控界面
├── Makefile        # 构建脚本
└── README.md       # 项目说明
```

## 许可证

MIT License 
