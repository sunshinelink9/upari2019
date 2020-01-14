# Springboot

### 1、什么是Spring

​		spring是一个开源框架（容器），2003年兴起的一个轻量级的java开发框架

​		![image-20200113142312737](C:\Users\sunshine\AppData\Roaming\Typora\typora-user-images\image-20200113142312737.png)

### 2、什么是springboot

​     	约定大于配置     贯彻“高内聚低耦合”的思想



### 3、spring自动装配原理

-   spring-boot-dependencies:核心依赖都在父类

- 我们写入或者引入一些springboot依赖的时候，不需要指定版本，就因为有这些版本仓库

- springboot会把所有的功能都变成一个个的启动器；我们需要什么样的功能，就只需要找到对应的启动器就行了

- ```
  @SpringBootApplication
  ```

  标注这是springboot的启动类
  
- 核心配置文件：spring.factores

- springboot 所有自动配置都是在启动的时候扫描并加载：spring.factories 所有的自动配置类都在这里面，但是不一定生效，要判断条件是否称了，只要导入了对应的start，就有对应的启动器了，有了启动器，我们自动装配就会生效，然后就配置成功！

- ![](https://note.youdao.com/yws/api/personal/file/EF5404E0E7B94AD6AF12A286A7DDECE9?method=download&shareKey=f0a048cec1e25936f391b74db15a2b38)



![](https://note.youdao.com/yws/api/personal/file/C3FFC5D1A9DD41559F074B4853780C22?method=download&shareKey=09b0272ad1a5343edadf2afdd1110cd9)

面试关于springboot的理解：1：图片1；自动装配；

​												   2：run（）方法



### 4、springboot配置

- 优先级：同一路径下的三个文件properties>yaml>yml；若application.yml 和bootStrap.yml 在同一目录下，则bootStrap.yml 的加载顺序要高于application.yml,即bootStrap.yml 会优先被加载；在不指定要被加载文件时，默认的加载顺序：由里向外加载，所以最外层的最后被加载，会覆盖里层的属性
- yaml对空格要求严格
- yaml可以给实体类赋值，
- ![image-20200114162237827](https://note.youdao.com/yws/api/personal/file/3914B406D0D54BC581E6F6B7BD8D418C?method=download&shareKey=0eb556aa2f69235a2bf9340779c957d0)
- 松散绑定，java中驼峰命名，配置文件中都是小写，用“-”分隔表示

- 使用@ConfigurationProperties(prefix = "persion")//指定配置文件中的对象，在配置文件中给类注入属性，如给mybatis的配置类注入url等属性
- @Validated，数据校验  <u>@Validated //数据校验 JSR303校验</u>   @Notnull @Email等注解去校验
- 复杂类型封装



### 5、