# Spring-activeMQ
  在业务逻辑的异步处理，系统解耦，分布式通信以及控制高并发的场景下，消息队列有着广泛的应用。本项目基于Spring这一平台，整合流行的开源消息队列中间件ActiveMQ,实现一个向ActiveMQ添加和读取消息的功能。并比较了两种模式：生产者-消费者模式和发布-订阅模式的区别。
包含的特性如下：  
  
1.使用时，将war文件放入tomcat的webapps目录下，启动服务器，开启activeMQ，访问http://localhost:8080/Spring-activeMQ/demo  ，我们可以在页面顶端看到一个黑色的控制台，用于监控消息的内容，如下图：
 ![alt text](https://github.com/shenzhanwang/Spring-activeMQ/blob/master/%E6%88%AA%E5%9B%BE/1.jpg)  
 

2 在项目中，我们为消息的生产者和发布者分别注册了两个消费者和订阅者，当有消息到达activeMQ时，消费者和订阅者会自动获取对应的消息，可以在前端控制台看到结果（前端页面控制台是基于websocket全双工通信协议实现的，可用于将服务器端的信息主动推送到浏览器，在本项目中不做重点介绍）；

 
3.填入要发送的消息，点击生产消息可以向消息队列添加一条消息，我们可以试着添加了四条消息，并观察控制台结果，可以发现每个消息只被某一个消费者接收； 

 
4.重复以上操作发布四条消息，可以看到订阅者的输出结果，表明每个发布的消息可以被两个订阅者全部接收；
 
   
5.以上结果表明，向队列生产的每条消息，只能被某一个消费者读取，而发布的消息，可以被每个订阅者重复读取，这是两种模式最大的区别，实际应用中要根据情况来选择。
 
  ![alt text](https://github.com/shenzhanwang/Spring-activeMQ/blob/master/%E6%88%AA%E5%9B%BE/QQ%E6%88%AA%E5%9B%BE20161109085633.jpg)
   ![alt text](https://github.com/shenzhanwang/Spring-activeMQ/blob/master/%E6%88%AA%E5%9B%BE/QQ%E6%88%AA%E5%9B%BE20161109085653.jpg)



 



