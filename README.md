# day01
## 0. 准备
    项目描述: 做什么/特点/功能模块/主要技术/开发方式
    技术选型: 分方向详细技术
    API接口: 理解/ 接口文档/对接口

## 1. 创建项目, 并运行
	create-react-app react-admin
	npm start

## 2. 对项目进行git版本控制
	创建本地仓库
	创建远程仓库
	将本地仓库推送到远程
	创建dev分支并推送到远程
	克隆远程分支, 并创建本地dev分支

## 3. 设计源码的基本目录, 实现App基本组件效果
	assets	
	api
	components
	pages
	App.js
	index.js

## 4. 引入antd, 实现按需打包和自定义主题
	下载antd和相关的工具包
	配置1: config-overrides.js
	配置2: package.json

## 5. 引入react-router-dom, 实现基本的一级路由
	<BrowserRouter>/<HashRouter>
	<Switch>
	<Route>
	login/admin

## 6. 登陆的基本静态界面
	<Form>
	<Form.Item>
	<Input>
	<Icon>
	<Button>

## 7. 登陆的表单验证和数据收集
	配置对象: 属性名是一些特定的名称的对象
	验证需求:
		用户名: 长度>=4的字符串
		密码: 长度在4-8位的字符串
	包装Form组件: Form.create()(LoginForm)
		操作表单项(Field)数据
		对表达项数据进行实时验证
	form对象:
		this.props.form: 得到form对象
		getFieldDecorator(fieldName, options)(<Input/>): 包装Input组件
		resetFields(): 重置所有输入框
	表单验证方式:
		纯声明式验证
		半编程式验证
		
# day02

## 1. server应用
    理解前后台分离
    启动应用
    使用postman测试接口
    
## 2. ajax请求函数模块
	内部封装axios
    函数的返回值为promise对象
    目标:
      1. 请求错误统一处理
      2. 异步返回的是data, 而不是response
    解决: 
      自定义promsie对象
      在catch回调中: 不调用reject(), 而是显示提示
      在then回调中:  resolve(response.data)
      
## 3. 封装接口请求函数模块
    对ajax模块进一步封装, 让发请求的调用代码更简洁
    函数返回的是promise对象
    根据接口文档定义接口请求函数
    
## 4. 代理
    1). 是什么?
       具有特定功能的程序
    2). 运行在哪?
       前台应用端
       只能在开发时使用
    3). 作用?
        解决开发时的ajax请求跨域问题
        监视并拦截请求(3000)
        转发请求(4000)
    4). 配置代理
       告诉代理服务器一些信息: 转发的目标地址
       
## 5. 实现登陆功能
    调用接口请求函数请求登陆
    使用store库保存user到local中
    将user保存到内存中
    实现用户登陆检查/自动登陆
    
## 6. 搭建管理界面的整体结构
    LeftNav
    Header
    Footer
    多个切换显示的路由组件
        Home
        Category
        Product
        User
        Role
        Bar
        Line
        Pie

## 7. 左侧导航
    导航相关数据的配置
    根据导航配置动态渲染导航界面
        Menu/SubMenu/Item/Icon
        函数递归调用/reduce()    

# day03

## 1. Header

1). 界面布局: Row / Col
	2). 时间动态显示: sysTime + setInterval()
	3). 天气: 天气接口 + jsonp
	4). 显示当前用户
	5). 退出登陆
	6). 显示当前导航页面的名称
