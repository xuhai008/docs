# 机器人客服

企业需要快速回复客服问题，当前市场上，存在很多厂商能提供全渠道智能客服系统，相对来说，渠道对接已经非常成熟，集成起来容易。但是在机器人客服上，用户体验参差不齐。在
Chatopera，我们主要关注智能机器人，追求最好的机器人客服体验：快速实现符合业务需求的聊天机器人，效果稳定。

<table class="image">
    <caption align="bottom">用户服务环节</caption>
    <tr>
        <td><img width="800" src="../../images/products/user-cycle-service.png" alt="用户服务环节" /></td>
    </tr>
</table>

在 Chatopera，客服机器人将加入到聊天室中，它有两种参与客户服务的方式：

1. 辅助客服人员

2. 接管聊天室，直接和消费者沟通

<table class="image">
    <caption align="bottom">机器人客服</caption>
    <tr>
        <td><img width="800" src="../../images/products/user-service-flow-2.png" alt="机器人客服" /></td>
    </tr>
</table>

具体地说，在排队阶段，引导消费者问问题，借助<a href="https://docs.chatopera.com/chatbot-engine.html"
    target="_blank">智能问答引擎</a>服务，进行意图识别，如果意图匹配到了智能问答引擎中的多轮对话，就启动多轮对话，完成服务；未匹配到多轮对话则继续排队，在客服人员接入会话时，机器人客服针对消费者的问题，给客服人员建议回复。

**针对不同企业客户的需求，机器人客服的服务方式也可以调整，最主要的是，机器人客服可以利用多轮对话和知识库，提高用户满意度，提高效率，人工坐席专注于更加棘手的问题。**

## 创建网站渠道

以管理员身份*春松客服坐席工作台*，导航【系统-客服接入-网站列表-创建新网站】，按照如下内容设置网站渠道。

| 项目     | 值        | 描述            |
| -------- | --------- | --------------- |
| 网站名称 | localhost | 任意字符串      |
| 网站地址 | localhost | 网站的域名或 IP |

<table class="image">
    <caption align="bottom">创建网站渠道</caption>
    <tr>
        <td><img width="800" src="../../images/products/cosin/47127371-6fbc5480-d2bf-11e8-9983-b6f79e97cbf1.png"
                alt="" />
        </td>
    </tr>
</table>

点击【立即提交】保存。

## 创建聊天机器人

登录[Chatopera 云服务](https://bot.chatopera.com/)，注册并在【控制台】中创建聊天机器人。

<table class="image">
    <caption align="bottom">创建聊天机器人</caption>
    <tr>
        <td><img width="800" src="../../images/products/cc-bot-1.png" alt="" /></td>
    </tr>
</table>

| 项目       | 值         | 描述                         |
| ---------- | ---------- | ---------------------------- |
| 机器人名称 | 小 C       | 机器人的名字，创建后不能变更 |
| 描述       | 机器人客服 | 机器人的描述                 |
| 语言       | zh_CN      | 机器人的语言为中文           |

机器人具有多轮对话和知识库两个管理对话能力的组件，在创建好机器人后，创建一个问答对作为测试示例。点击【知识库】图标，点击【新建问题】。

<table class="image">
    <caption align="bottom">新建问答对</caption>
    <tr>
        <td><img width="800" src="../../images/products/cc-bot-2.png" alt="" /></td>
    </tr>
</table>

| 项目 | 值                                                       | 描述       |
| ---- | -------------------------------------------------------- | ---------- |
| 问题 | 缴费年期变更后，佣金如何计算？                           | 问题的文本 |
| 答案 | 变更后仍有佣金的，按照变更后的年期对应的提佣率计算佣金。 | 问题的答案 |

点击【确定】。

集成机器人的方式是通过 SDK 创建机器人实例，使用机器人接口进行对话和查询等。机器人实例的认证和授权是通过*ClientId*和*Secret*完成，点击【设置】查看*ClientId*和*Secret*。

<table class="image">
    <caption align="bottom">查看ClientId和Secret</caption>
    <tr>
        <td><img width="800" src="../../images/products/cc-bot-4.png" alt="" /></td>
    </tr>
</table>

## 集成机器人客服

以管理员身份*春松客服坐席工作台*，导航【智能机器人-新建机器人】，按照如下内容填入创建表单。

| 项目     | 值             | 描述                                                    |
| -------- | -------------- | ------------------------------------------------------- |
| 网站渠道 | localhost      | 根据网站地址选择网站渠道                                |
| ClientId | xxx            | [Chatopera 云服务 ClientId](https://bot.chatopera.com/) |
| Secret   | xxx            | [Chatopera 云服务 Secret](https://bot.chatopera.com/)   |
| 工作模式 | 机器人客服优先 | 目前支持【机器人客服优先】或【人工客服优先】两种类型    |
| 描述     | 机器人客服     | 对机器人的简要介绍                                      |

<table class="image">
    <caption align="bottom">集成机器人客服</caption>
    <tr>
        <td><img width="600" src="../../images/products/cc-bot-3.png" alt="" /></td>
    </tr>
</table>

点击【保存】创建机器人，返回机器人列表页面，可以找到刚刚创建的机器人客服，创建后，默认状态，机器人是不开启的，在列表页通过【是否开启】设置该机器人为*开启*，如下图所示。

<table class="image">
    <caption align="bottom">开启机器人客服</caption>
    <tr>
        <td><img width="800" src="../../images/products/cc-bot-5.png" alt="" /></td>
    </tr>
</table>

## 测试机器人客服

> 提示：春松客服访客测试端地址

```
http[s]://春松客服IP[:PORT]/testclient.html
```

使用浏览器打开*春松客服访客测试端*，并点击【在线客服】。在知识库设置好后，当访客在客户端问问题，匹配了知识库的问题后，机器人就自动回复。

比如输入：_缴费年期变更后，佣金如何计算？_，能得到在知识库中设置的答案。

<table class="image">
    <caption align="bottom">访客端和机器人对话</caption>
    <tr>
        <td><img width="800" src="../../images/products/cc-bot-6.png" alt="" /></td>
    </tr>
</table>

如果想使机器人变得更加智能，需要参考关于[Chatopera 云服务](https://docs.chatopera.com/chatbot-platform.html)的更多介绍。

## 问候语

在默认情况下，机器人的问候语是在 Chatopera 云服务的机器人属性页面进行设置，该设置只支持简单的文本。

<table class="image">
    <caption align="bottom">设置机器人问候语</caption>
    <tr>
        <td><img width="800" src="../../images/products/cosin/cards/image-11.png" alt="" /></td>
    </tr>
</table>

<table class="image">
    <caption align="bottom">春松客服访客端</caption>
    <tr>
        <td><img width="800" src="../../images/products/cosin/cards/image-1.png" alt="" /></td>
    </tr>
</table>

访客登录进入客服聊天窗口往往是有一些问题要咨询的，所以更为合理的用户体验是将一些常见问题作为导航用途显示在问候语下面，比如这样：

<table class="image">
    <caption align="bottom">常见问题列表</caption>
    <tr>
        <td><img width="800" src="../../images/products/cosin/cards/image-8.png" alt="" /></td>
    </tr>
</table>

在春松客服里，为了支持各种丰富的对话场景，这些功能都是使用多轮对话配置。接下来的介绍假设您已经学习了[多轮对话设计器](https://docs.chatopera.com/products/chatbot-platform/conversation.html#%E5%A4%9A%E8%BD%AE%E5%AF%B9%E8%AF%9D%E8%AE%BE%E8%AE%A1%E5%99%A8)的内容，**如果您还没有学习这部分内容，建议先完成，大约需要
30 分钟时间**。

下面是支持在问候语中关联热门问题，进行导航的方法：

- 下载安装多轮对话设计器

<table class="image">
    <caption align="bottom">下载多轮对话设计器</caption>
    <tr>
        <td><img width="800" src="../../images/products/cosin/cards/image-2.png" alt="" /></td>
    </tr>
</table>

下载连接也可以通过[多轮对话设计器使用教程](https://docs.chatopera.com/products/chatbot-platform/conversation.html#%E4%B8%8B%E8%BD%BD%E5%9C%B0%E5%9D%80)获得。

- 新建聊天机器人

<table class="image">
    <caption align="bottom">新建聊天机器人</caption>
    <tr>
        <td><img width="800" src="../../images/products/cosin/cards/image-3.png" alt="" /></td>
    </tr>
</table>

- 新建对话技能

<table class="image">
    <caption align="bottom">新建对话技能</caption>
    <tr>
        <td><img width="800" src="../../images/products/cosin/cards/image-4.png" alt="" /></td>
    </tr>
</table>

此处，对话名称可以使用字母、数字和下划线组成的字符串填写。

- 粘贴技能脚本

在该机器人的技能列表中，点击刚刚创建的技能的“编辑”按钮，并在新打开的编辑窗口中，选择“脚本”，将下面的几行内容粘贴到编辑窗口中。

<pre class="prettyprint">
// FAQ Hotlist
+ __faq_hot_list
- ^get_greetings()
</pre>

点击【保存】，在编辑窗口中，如图。

<table class="image">
    <caption align="bottom">粘贴技能脚本</caption>
    <tr>
        <td><img width="800" src="../../images/products/cosin/cards/image-12.png" alt="" /></td>
    </tr>
</table>

该规则`__faq_hot_list`将保证在访客和机器人连接成功后，
机器人发送函数`get_greetings`返回的内容。此处`__faq_hot_list`是固定的，`get_greetings`函数名和下面的技能函数名保持一致便可。

- 粘贴技能函数

<pre class="prettyprint">
// 问候语中关联常见问题
exports.get_greetings = async function() {
    return {
        text: "请问有什么可以帮到您？",
        params: [{
            label: "1. 产品列表",
            type: "qlist",
            text: "产品列表"
        }, {
            label: "2. 当季热销产品",
            type: "qlist",
            text: "当季热销产品"
        }, {
            label: "3. 退换货咨询",
            type: "qlist",
            text: "退换货咨询"
        }]
    };
}  
</pre>

点击【保存】，在编辑窗口中，如图。

<table class="image">
    <caption align="bottom">粘贴技能函数</caption>
    <tr>
        <td><img width="800" src="../../images/products/cosin/cards/image-13.png" alt="" /></td>
    </tr>
</table>

在函数中，可以自定义热门问题的文字，顺序。文字即访客看到的文本内容，通过`label`设定，当访客点击一个问题时，聊天机器人将收到 `text`设定的文本。您可以在知识库或多轮对话中，设置该文本的回复内容。

访客对于热门问题列表，可以点击多次。

- 导出聊天机器人

多轮对话设计器是企业聊天机器人的设计环境，[Chatopera 云服务](https://docs.chatopera.com/chatbot-platform.html)或[智能问答引擎](https://docs.chatopera.com/chatbot-engine.html)是机器人的运行时环境。

<table class="image">
    <caption align="bottom">发布并导出对话应用</caption>
    <tr>
        <td><img width="800" src="../../images/products/cosin/cards/image-6.png" alt="" /></td>
    </tr>
</table>

导出后，多轮对话设计将该机器人多轮对话保存为一个`.c66` 后缀的文件。

- 发布聊天机器人

登录 Chatopera 云服务，在目标机器人的多轮对话管理面板中，导入对话应用(`.c66`)文件。

<table class="image">
    <caption align="bottom">导入Chatopera云服务</caption>
    <tr>
        <td><img width="800" src="../../images/products/cosin/cards/image-7.png" alt="" /></td>
    </tr>
</table>

- 上线后使用

在导入成功后，在春松客服中，访客再次登录聊天窗口，就会收到带有热门问题的问候语。

## 按钮消息

另外一种情况是机器人客服回答一个选择列表，访客点选按钮进行选择。

<table class="image">
    <caption align="bottom">按钮消息</caption>
    <tr>
        <td><img width="800" src="../../images/products/cosin/cards/image-9.png" alt="" /></td>
    </tr>
</table>

- 粘贴技能脚本

可以在上面步骤中建立的技能中，添加新的规则：

<pre class="prettyprint">
+ (*) 产品列表 (*)
- ^get_products()
</pre>

该规则将保证在访客的问题中有 `产品列表`时，发送函数`get_products`返回的内容。

- 粘贴技能函数

<pre class="prettyprint">
// 按钮选择消息
exports.get_products = async function() {
    return {
        text: "您对下面哪个产品感兴趣",
        params: [{
                label: "上衣",
                type: "button",
                text: "介绍一下上衣"
            },
            {
                label: "服装",
                type: "button",
                text: "介绍一下鞋帽"
            }
        ]
    }
}
</pre>

在脚本中，只需要设定`params`中的内容作为选型，其他保持默认。

## 图文消息

春松客服还支持的一类消息是图文消息，通过是分享一个链接，展示链接的图片和简介。

<table class="image">
    <caption align="bottom">按钮消息</caption>
    <tr>
        <td><img width="800" src="../../images/products/cosin/cards/image-10.png" alt="" /></td>
    </tr>
</table>

- 粘贴技能脚本

可以在上面步骤中建立的技能中，添加新的规则：

<pre class="prettyprint">
+ 介绍一下上衣
- ^get_shangyi()
</pre>

该规则将保证在访客的问题中有 `介绍一下上衣`时，发送函数`get_shangyi`返回的内容。

- 粘贴技能函数

<pre class="prettyprint">
// 图文消息
exports.get_shangyi = async function() {
    return {
        text: "{CLEAR} 图文消息",
        params: [{
            type: 'card',
            title: "秋冬上衣优选",
            thumbnail: "https://ss0.bdstatic.com/70cFuHSh_Q1YnxGkpoWK1HF6hhy/it/u=277597165,2202071991&fm=15&gp=0.jpg",
            summary: "秋冬上衣优选秋冬上衣优选秋冬上衣优选秋冬上衣优选秋冬上衣优选秋冬上衣优选秋冬上衣优选秋冬上衣优选",
            hyperlink: "https://www.1688.com/huo/B6F9CDAFD7B0C5AEBAA2CDE2CCD7BCD3BAF1C9CFD2C2C7EFB6AC.html"
        }]
    }
}
</pre>

其中，`title`代表大标题，`thumbnail`是图片，`summary`是简介，`hyperlink`是点击图文消息后，跳转的链接，这几项是用户可以自定义的，其它项就使用默认值，比如`type`的值必须是`card`。

文本消息、热门问题、按钮消息和图文消息是春松客服支持的在线机器人客服消息类型。在掌握了知识库、脚本语法和函数后，用户可以支持各种客服场景。

## 快速开始

在上面的介绍中，Chatopera 的多轮对话机器人通过`c66`文件进行分发，Chatopera
提供了在问候语中关联热门问题的多轮对话应用示例文件(`小松.1.0.7.c66`)，您可以点击[下载链接](https://github.com/chatopera/chatopera.samples/raw/master/%E5%8D%A1%E7%89%87%E6%B6%88%E6%81%AF/%E5%B0%8F%E6%9D%BE.1.0.7.c66)获得这个应用。

该对话可以导入到多轮对话设计器中，进行浏览脚本和函数；也可以直接导入到 Chatopera 云服务，然后在春松客服中进行体验。

## 评论

<script src="https://utteranc.es/client.js"
        repo="chatopera/docs"
        issue-term="pathname"
        label="Comment"
        theme="github-light"
        crossorigin="anonymous"
        async>
</script>
