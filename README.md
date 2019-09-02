########
## demo1: 
 一个简单的react  demo 
 react 必须引用react,react-dom和babel。
  react创建虚拟dom；
  react-dom 就是把数据渲染出来；
  babel编译成浏览器可以识别的插件，由于react是jsx方式，需要进行编译；
 
 ## demo2和demo3: 
 react 不支持if else 但支持三元函数；
 循环绑定的时候需要绑定一个key，和vue一样，作用于唯一；

## demo4:
react使用组件化，声明组件后，reactdom直接引用
创建组件需要继承React.Component声明,

## demo5:
react组件添加子节点的时候，用this.props.children来接收参数，但是需要用react自己内部封装的Reac.Children用法

## demo6:
react需要判断参数是否是是什么类型，可以引用prop-types这个js， 声明静态函数 propTypes 用法地址为： https://www.jianshu.com/p/8bd8a6e60e78

## demo7:
数据绑定有3种方法：
1.在创建组件的时 constructor里面就开始声明绑定方法名，并指定this;
 constructor(props) {
           super(props)
           this.handleClick=this.handleClick.bind(this);
       }
2.在点击的的按钮上就加上绑定方法名并且指定this;onClick={this.handleClicks.bind(this)}
3.用es6的箭头函数，因为箭头函数他连接上下文，可以获取到组件的this指向；
 handleClickhs=()=>{

    }
## 传值
按钮传值时的几种方法例如：
this.handleClicks.bind(this,'传值')
## es6传值
this.handleClickhs(传值参数)
handleClickhs=(参数)=>{

    }

## demo8:
react渲染的时候 当值改变的时候需要重新改变值
就用this.setState({
    改变值
})
this.state.获取state的值
setState是异步操作 那么他不会同步改变，
this.setState({
    改变值
},function(){
    改变得到的最新的值
})

## demo9:
用input方法都需要有个onchange方法来监听input框值；

## demo10:
react保留了js的关键字，所以样式class需要改变成className， for 变成htmlFor
style样式需要用对象的形式 style={{opacity:this.state.opacity}} ，


## demo11&demo12:
说明的是react的声明周期
# 初始化
就是constructor的时候
# 挂载阶段 （只执行一次）
挂载前 
#componentWillMount：只执行一次，并且执行的时候，react未渲染完成，
渲染
#render:根据组件的props和state，return 一个React元素
挂载后
#componentDidMount：渲染完成后调用该方法，一般为调用接口；

# 更新阶段

#componentWillReceiveProps 检测组件参数props的改变，改变就会触发这个方法，初始化render时不会被调用

#shouldComponentUpdate 在组件接收到新的props或者state时被调用

#componentWillUpdate  在组件接收到新的props或者state但还没有render时被调用

#render 渲染

#componentDidUpdate  在组件完成更新后立即调用。在初始化时不会被调用。

# 卸载阶段

#componentWillUnmount 在组件从 DOM 中移除之前立刻被调用


########################react最新声明周期###############
#初始化
        constructor
#挂载阶段
        getDerivedStateFromProps：每次渲染之前都会调用
        reader 渲染
        componentDidMount :只执行一次，并且执行的时候，react未渲染完成，
#更新阶段
        getDerivedStateFromProps：每次渲染之前都会调用
        shouldComponentUpdate :在组件接收到新的props或者state时被调用。在初始化时或者使用forceUpdate时不被调用。 
        reader :渲染
        getSnapshotBeforeUpdate:在最新的渲染数据提交给DOM前会立即调用
        componendDidCatch:错误处理函数
        componentDidUpdate:在组件完成更新后立即调用
#卸载阶段
        componentWillUnmount 在组件从 DOM 中移除之前立刻被调用