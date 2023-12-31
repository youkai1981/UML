# UML规范

## 一. 目录

>1. 实体图/类图规范
>3. 时序图规范

## 二. 工具

建模工具： PowerDesigner  

网盘下载地址： 

>链接：https://pan.baidu.com/s/1vjRZOJgO19q_uPS68vFcCQ 
>提取码：sino 
>--来自百度网盘超级会员V2的分享



编写初心：尽量脱离编程开发语言，但不可避免有部分需要一个编程语言举例说明，所以本文使用`Java`语言

设计理念： 实例用的越少越好！ 表达的越清楚越好

## 三. 类图规范

### 3.1 概念

#### 3.1.1 什么是类图？

>官方话术：
>
>`UML实体图是一种在软件工程中使用的图形化建模工具，用于表示系统中的实体类及其之间的关系。实体类代表了系统中的具体对象或概念，并描述了它们的属性和行为。实体类之间的关系可以通过关联、聚合、组合、继承和接口实现等方式表示。UML实体图提供了一种标准化的表示方法，可以帮助开发人员更好地理解和设计软件系统的结构和功能。`
>
>
>
>概要：
>
>`UML实体图是一种用于描述系统中的实体类、它们之间的关系以及属性和方法的图形化表示方法。`

#### 3.1.2 类图优势

>1. `可视化设计`：实体图提供了一种图形化表示方式，可以帮助开发人员更直观地理解和设计系统的结构和关系。通过视觉化的方式，可以更容易地沟通和共享设计概念。
>
>
>
>2. `清晰的结构表达`：实体图清楚地展示了实体类、它们的属性和方法以及彼此之间的关系。这有助于在系统设计过程中明确每个实体类的职责和行为，并可以更好地进行模块化设计。
>
>
>
>3. `关系描述`：通过实体图，可以准确地描述实体类之间的关系，如关联、聚合、组合、继承和接口实现等。这有助于开发人员理解和设计对象之间的交互方式和依赖关系。
>
>
>
>4. `可重用性和扩展性`：实体图可以帮助识别出可重用的实体类和组件，以及它们之间的关系。这有助于开发人员将系统设计为可扩展和可维护的结构，从而提高代码的重用性和灵活性。

#### 3.1.3 实体图和类图的区别

>1. `关注点不同`：实体图通常用于展示系统中的实体类及其之间的关系，侧重于系统的静态结构。而类图则更加全面，既包含了实体类及其关系，也包含了类的属性和方法，以及类之间的行为和交互。
>2. `展示形式不同`：实体图通常使用简化的形式展示实体类，只显示类名和关系，一般省略属性和方法的具体细节。而类图则更加详细，显示了类的属性、方法和关系的详细信息，可用于更深入的分析和设计。
>
>
>
>3. `适用范围不同`：实体图主要用于领域建模，用于描述系统中的具体对象或概念。它们更关注系统的实体和它们之间的关系，对于需求分析和领域建模非常有帮助。类图则更加通用，适用于系统的设计和编程阶段，用于描述类的细节和系统的结构。
>
>
>
>4. `使用场景不同`：实体图常用于面向对象的分析和设计阶段，用于描述问题领域的概念和实体之间的关系。类图则可以用于整个软件开发过程中的不同阶段，从需求分析、设计到编码和测试，以及后续的维护和文档编写。
>
>
>
>总结：
>
>​	`用于数据传输相关对象为实体图，用于行为交互为类图`

### 3.2 创建流程

举例：` 业务字典模块`

#### 3.2.1 创建类图流程

1. 点击新建文件

![1689044963847](assets/1689044963847.png)

2. 创建类图

![1689044985422](assets/1689044985422.png)



#### 3.2.2 类图实例说明



实例说明：

> 1. 类实例（Class）： 指一个class对象，其中包含对象的属性以及方法
>
> 
>
> 2. 接口实例（Interface）： 表示Java接口（非Resuful接口），通常定义行为
>
> 
>
> 3. 类继承（generalization）：类继承是面向对象编程中的一个重要概念，它允许一个类继承另一个类的属性和方法。
>
> 
>
> 4. 接口实现（Realization）： 类实现接口，重写 接口中方法，接口定义行为，类实现行为



类实例（Class） ： ![1689046280207](assets/1689046280207.png)



接口实例（Interface）：	![1689046302511](assets/1689046302511.png)

类继承 （generalization）： ![1689046413891](assets/1689046413891.png)

接口实现（Realization）：![1689046425660](assets/1689046425660.png)



#### 3.2.3 类名方法接口规范

 **对标阿里巴巴开发规范**

**类名**：采用大驼峰命名法，首字母大写，其余每个单子字母大写，如`DictBizController`

类名关键字：

- DTO：

  >通常用于将领域对象（实体类）的数据转换为数据传输对象，Resuful中POST接口入参以DTO结尾
  >
  >如：   createDictBiz(CreateDictBizDto )，createDictBiz方法中使用CreateDictBizDto  作为入参
  >
  >```java
  >public R<DictBizVO> createBizDict(DictDTO dict) {
  >}
  >```

- VO：

  >Vo 通常用于表示视图层所需的数据
  >
  >如:
  >
  >```java
  >public R<DictBizVO> detail(DictBiz dict) {
  >}
  >```

- Query:

  >Query表示用于查询条件
  >
  >如： 根据姓名/手机号/性别筛选 数据
  >
  >姓名，手机号，性别封装为Query，可起名为 GetUserQuery
  >
  >```java
  >public R<User> createBizDict(GetUserQuery dict) {
  >}
  >```



>ps:
>
>Java中：
>
>所有控制器，全部以Controller结尾，如 `DictBizController`
>
>所有业务层接口，应该以Service结尾，以`I`开头，如 `IDictBizService`,
>
>所有业务层类，去掉业务层接口前缀`I`，在接口的名称后面添加`impl`，如 `DictBizServiceImpl`
>
>数据持久层可选择：`Dao/Mapper` 命名，建议Mapper，如 `DictBizMapper`

**方法**：

- 关键字

(借鉴`BladeX`,`阿里巴巴开发标准` 定义)

| 关键字 | 说明             | 样例                             |
| ------ | ---------------- | -------------------------------- |
| create | 新增             | createDictBiz(CreateDictBizDto)  |
| update | 编辑             | updateDictBiz(UpdateDictBizDto)  |
| remove | 删除             | removeDictBiz(RemoveDictBizDTO)  |
| get    | 查询单条数据     | getDictBizById(Long id);         |
| find   | 查询多条数据     | findDictBizByIdS(List<Long> ids) |
| page   | 分页查询         | pageDictBiz(PageDictBizDTO)      |
| by     | 条件             |                                  |
| count  | 统计数量         | countDictBiz()                   |
| exist  | 判断数据是否存在 | existDictBizByCode(String code)  |

其余常见方法`bladeX`：

- detail 获取详情
- list 获取列表
- page 分页获取列表
- save 新增
- update 修改
- submit(新增或修改)
- tree 获取树形结构
- remove(删除)



#### 3.2.4 类图参数说明

| 参数名称             | 参数说明                             | 举例       |
| -------------------- | ------------------------------------ | ---------- |
| Name                 | 表示类图中文名称（多数为英文翻译）   | 业务字典   |
| Code                 | 表示代码中实际类图名称（与name对应） | DictBiz    |
| Comment              | 表示对该类的其他备注                 |            |
| Extends              | 可选继承类（父类）                   |            |
| Visbility            | 访问修饰符                           | public     |
| Attributes(见下文)   | 属性                                 | age        |
| Operations（见下文） | 方法                                 | getDetails |



![1689057214717](assets/1689057214717.png)



`Attributes`属性介绍：

| 参数名称      | 参数说明   | 举例    |
| ------------- | ---------- | ------- |
| Name          | 中文名     | 名字    |
| Code          | 属性名     | name    |
| Data Type     | 属性类型   | String  |
| Visbility     | 访问修饰符 | private |
| Initial Value | 默认值     | 张三    |



![1689057515047](assets/1689057515047.png)



`operations`属性介绍

| 参数名称    | 参数说明   | 举例                       |
| ----------- | ---------- | -------------------------- |
| Name        | 方法中文名 | 获取用户总数               |
| Code        | 方法名     | countUser()                |
| Return Type | 返回值类型 | Long(多为其余类，可选引用) |
| Visbility   | 访问修饰符 | private                    |



![1689058065089](assets/1689058065089.png)

双击Name左侧空白方框，进行方法属性设置

![1689058802022](assets/1689058802022.png)



### 3.3  类图与实体图样例

#### 3.3.1 实体图

由于几乎每个实体类都有getter/setter方法，所以无需编写，直接写一个getter，setter方法即可

![1689066364881](assets/1689066364881.png)

#### 3.3.2 类图

![1689069041333](assets/1689069041333.png)

## 四. 时序图规范

### 4.1 概念

#### 4.1.1 什么是时序图

>时序图（Sequence Diagram）是一种UML（统一建模语言）图表，用于描述对象之间的交互行为和消息传递顺序。它展示了对象之间的交互过程，以时间的顺序表示对象之间的消息传递和方法调用。
>
>时序图可以描述以下内容：
>
>1. `对象之间的交互顺序`：时序图显示了消息传递和方法调用的顺序，帮助理解对象之间的交互顺序。
>2. `方法调用和返回`：时序图可以显示方法的调用和返回顺序，以及参数和返回值的传递
>3. `并发和并行`：时序图可以表示并发和并行执行的情况，通过显示多个对象的活动线或生命线。**未做**
>4. `循环和条件`：时序图可以表示循环和条件逻辑，通过循环框和分支箭头来表示。**未做**

#### 4.1.2 时序图的优势

>1. `易于理解和沟通`：时序图以直观的方式展示对象之间的交互和消息传递顺序，使得系统行为和交互过程更易于理解和沟通。这使得团队成员、利益相关者和其他利益相关方能够更好地理解系统的工作方式和交互细节。
>2. `揭示交互细节`：时序图可以捕捉对象之间精确的交互细节，包括消息传递的顺序、方法调用和返回的过程等。这有助于识别和解决系统中可能存在的问题和瓶颈，以提高系统的性能和可靠性。
>3. `设计验证和迭代`：时序图可以用于验证系统设计的正确性和合理性。通过仔细分析时序图，可以识别设计上的缺陷或不一致性，从而进行迭代和改进。这有助于确保系统在实现之前满足需求和预期的行为。
>4. `与其他UML图结合使用`：时序图与其他UML图（如类图、用例图等）结合使用，可以提供一个完整的系统描述和设计。时序图可以与类图一起展示系统的静态结构和动态交互，帮助开发人员全面理解和分析系统。



### 4.2 创建流程

#### 4.2.1 创建时序图流程

![1689069820662](assets/1689069820662.png)



![1689069893602](assets/1689069893602.png)



#### 4.2.2 时序图实例说明

>1. `Actor` : 是指与系统进行交互的外部实体或角色。Actor代表了系统的外部用户、其他系统、硬件设备或任何与系统进行交互的实体。
>
>
>
>2. `Object`： 在时序图中，Object（对象）表示系统中的实际或虚拟对象，用于描述参与交互的系统内部组件或实体。
>
>
>
>3. `Procedure Call Message`: （过程调用消息）在时序图中用于表示一个对象调用另一个对象的方法或函数。它表示一个对象发送一个消息给另一个对象，以请求执行特定的操作或方法。
>
>   
>
>4. `Self return Message `: （自身消息）在时序图中用于表示一个对象自身内部的方法调用。它表示对象在自身范围内触发一个方法或操作的执行。
>
>   
>
>5. `return Message`：（返回消息）用于表示一个方法执行完成并返回结果给调用者的过程。它表示一个对象发送消息给调用者，将方法执行的结果返回。
>
>

#### 4.2.3 时序图参数说明

一个Case至少有两张时序图

简称为：`功能时序图`，`业务时序图`



两者区别：

> 功能时序图：注重页面功能与用户的交互设计
>
> 业务时序图：注重服务端具体实现逻辑



一个功能时序图至少由三部分组成：

- Actor：用户
- Object：页面
- Controller 接口

如图所示：

![1689073842319](assets/1689073842319.png)

其中：

>admin管理员：代表 Use Case 中的角色
>
>
>
>业务字典页面：代表前端的页面（对应一个Case）
>
>
>
>业务字典Controller：代表对应类图中Controller类图
>
>
>
>蓝色延长线：代表页面生命周期
>
>
>
>蓝色柱子： 代表一次操作的生命周期
>
>
>
>打开业务字典页面：代表用户对于页面的一次操作，此次操作指用户点击业务字典菜单打开业务字典页面
>
>
>
>根据条件获取业务字典：
>
>代表页面在加载完成之后对Controller进行一次请求，请求的方法就是类图中定义的根据条件获取业务字典方法



**用户像页面发起Message中参数**

>Name：表示操作的名字
>
>Code：表示操作的英文名
>
>Comment: 表示对该行为的备注
>
>Sender：消息发起者 (页面连线，则该位置直接填充)
>
>Receiver: 消息接收者 (页面连线，则该位置直接填充)
>
>如图：
>
>![1689073082235](assets/1689073082235.png)
>
>

**页面像服务端发起Message中参数**

>调用后台关注两点即可：
>
>1. Comment： 表示页面调用服务端备注，其中必填项为：
>
>   - uri 代表服务端请求后台的URI地址
>   - 参数（请求示例）
>
>   ![1689073338736](assets/1689073338736.png)
>
>2. Detail中的Operation方法
>
>   ![1689073481775](assets/1689073481775.png)

**服务端返回页面说明**

>1. Name： 表示返回的操作名称中文
>2. Code：  表示返回操作名称
>3. Comment： 表示服务端返回页面备注，其中必填项为：
>   -  返回结构体
>
>![1689073741705](assets/1689073741705.png)

自关联说明：

>1. Name： 表示操作名称中文
>
>2. Code：  表示操作名称
>
>   ![1689073906333](assets/1689073906333.png)

## 五. 软件常见问题：

### 4.1 **右侧工具栏找不到怎么办**

点击工具---> 点击自定义菜单和工具栏

![1689067577638](assets/1689067577638.png)

勾选Palette 即可

![1689067638427](assets/1689067638427.png)

### 4.2 Name属性不显示怎么办

点击工具----> Model Options

![1689069116598](assets/1689069116598.png)

勾选Name即可

![1689069158200](assets/1689069158200.png)
