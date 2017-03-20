项目目录结构
scrapy.cfg: 项目的配置文件
tutorial/: 该项目的python模块。之后您将在此加入代码。
tutorial/items.py: 项目中的item文件.
tutorial/pipelines.py: 项目中的pipelines文件.
tutorial/settings.py: 项目的设置文件.
tutorial/spiders/: 放置spider代码的目录.

为了创建一个Spider，您必须继承 scrapy.Spider 类， 且定义以下三个属性:
1. name: 用于区别Spider。 该名字必须是唯一的，您不可以为不同的Spider设定相同的名字。
2. start_urls: 包含了Spider在启动时进行爬取的url列表。 因此，第一个被获取到的页面将是其中之一。 后续的URL则从初始的URL获取到的数据中提取。
3. parse() 是spider的一个方法。 被调用时，每个初始URL完成下载后生成的 Response 对象将会作为唯一的参数传递给该函数。 该方法负责解析返回的数据(response data)，提取数据(生成item)以及生成需要进一步处理的URL的 Request 对象。

进入项目的根目录，执行下列命令启动spider:scrapy crawl dmoz


初窥Scrapy
Scrapy是一个为了爬取网站数据，提取结构性数据而编写的应用框架。可以应用在包括数据挖掘，信息处理或存储历史数据等一系列的程序中.
其最初是为了爬取网站数据，更确切地说，网络抓取所设计的，也应该应用在获取API所返回的数据，或者通用的网络爬虫。

简单的一次爬虫流程：
*选择一个网站:当您需要从某个网站中获得信息，但是该网站未提供API或通过程序获取信息的机制时，Scrapy可以助你一臂之力。
*定义您想抓取的数据：第一步是定义我们需要爬取的数据。在Scrapy中， 这是通过 Scrapy Items 来完成的。
*编写提取数据的Spider：其定义了初始URL、 针对后续链接的规则以及从页面中提取数据的规则。
*执行spider，获取数据，并以JSON格式存入到json文件中

Scrapy特性：
1. HTML,XML数据源 选择及提取的 内置支持
2. 提供了一系列在spider之间共享的可复用的过滤器（Item Loaders），对智能处理爬取数据提供了内置支持。
3. 通过feed导出 提供了多格式(json csv xml），多存储后端（ftp，s3，本地文件系统)的内置支持
4. 提供了media pipeline，可以自动下载 怕渠道的数据中的图片(或者其他资源)。
5. 高扩展性，宁可以通过使用signals。设计好的API（中间件，extensions，pipelines)来定制实现您的功能。
6. 内置的中间件及扩展为下列功能提供了支持：cookies and session 处理 | HTTP压缩 认证 缓存 | user-agent模拟 | robots.txt | 爬取深度限制
7. 针对非英语豫西中不标准或者错误的编码声明，提供了自动检测已经健壮的编码支持。
8. 支持根据模板生成爬虫，在加速爬虫的创建的同时，保持在大型项目中的代码更为一致。
9. 针对多爬虫下性能评估、失败检测；提供了可扩展的 状态手机工具。
10. 提供 交互式shell终端 , 为您测试XPath表达式，编写和调试爬虫提供了极大的方便
11. 提供 System service, 简化在生产环境的部署及运行
12. 内置 Web service, 使您可以监视及控制您的机器
13. 内置 Telnet终端 ，通过在Scrapy进程中钩入Python终端，使您可以查看并且调试爬虫
14. Logging 为您在爬取过程中捕捉错误提供了方便
15. 具有缓存的DNS解析器







