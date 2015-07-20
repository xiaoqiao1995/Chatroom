# Chatroom
本系统使用php+ajax轮询实现即时通讯的聊天室

文件描述
===============================================
1.login.php
    聊天室登录页面（账号密码来自于数据库，未实现注册功能）
    
2.chatindex.php
    聊天室页面，登录后的用户在此发送消息以及查看聊天记录
    
3.getMsg.php
    ajax通过此页面获取聊天记录
    
4.getUSers.php
    ajax通过从页面获取在线用户信息
    
5.sendMsg.php
    聊天室中点击发按钮，将输入信息发至此页面，将数据存储至数据库

相关说明
===============================================
1.进入聊天室页面后，用户发送消息，发送的消息以及相关信息（时间、发送者）被发送至sendMsg()，这些信息被存储至数据库chatinfo表

2.ajax每两秒执行getMsg()方法，通过向getMsg.php发送get请求，从数据库chatinfo表中读取消息列表（每次读取最后一条或者几条最新的数据）并显示出来

3.ajax每两秒执行getUsers()方法，通过向getUsers.php发送get请求，在数据库usersonline表中对在线用户信息（用户名，在线时间）进行更新，并获取在线用户信息并显示出来
