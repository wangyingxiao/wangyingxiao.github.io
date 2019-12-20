# 大屏可视化项目(vue)
> An awesome project.
访问路径：https://wangyingxiao.github.io/docs/#/
本地 在docs目录下 运行 docsify serve
## markdown使用

    <font size=5>**标题**</font>
        # 一级标题
        ## 二级标题
        ...
        ###### 六级标题  
    <font size=5>**设置字体样式**</font>  
        `*倾斜*`   
        `**加粗**` 
        `***倾斜加粗***`    
        `<font color=red> 我的颜色是红色的</font>`   
        `<font face="黑体">我是黑体字</font>` 
        `<font size=4>我是尺寸</font>` 

    <font size=5>**段落样式**</font>  

    **换行**  编辑好一行文字后瞧两个空格，再按回车键编辑另一行文字  

    <font size=5>**代码片段**</font>  



## 依赖的插件
### dayjs
 **简介**  
    封装完整的格式化时间，方便使用
    简化我们的开始过程
#### 快速开始
    可以使用npm install dayjs
----
#### api接口以及使用
### vue-countup-v2
### vue-echarts
> 引用内容
`console.log("这是一个代码块")`

这是一个普通段落：

    这是一个代码区块。

-   Red
-   Green
-   Blue
## 自己封装的组件
使用之前需要先进行引入 import *** from "xxx"  
例如：import tab from '../components/common/tab'

### tab标签页
    分隔内容上有关联但属于不同类别的数据集合。
    
     
        <template>
            <tab :btnList="btnList" @btnClick="btnClick"></tab>
        </template>
        <script>
        export default {
            data () {
                return {
                btnList: [
                        { name: '全部', type: 'all', checked: true },
                        { name: '大珠山', type: 'dazhushan', checked: false },
                        { name: '小珠山', type: 'xiaozhushan', checked: false, disabled: true },
                        { name: '金沙滩', type: 'jinshatan', checked: false },
                        { name: '银沙滩', type: 'yinshatan', checked: false, disabled: true }	        
                    ],	
                };
            },
            methods:{
                btnClick(data){
                    console.log(data);
                },               
            }
        }
     </script>
效果图如下：
![avatar](/images/tab.jpg)

<font size=6>Attributes</font>

 | 参数 | 说明 | 类型 | 可选值 | 默认值 | 是否必填 
 | - | :- | :-: | :-: | :-:| :-: |
 | btnList | 传入的btnList值<br> name:按钮名称，<br>type:类型，<br>checked:是否选中，<br>disabled：是否可用 | Array | 无 | [] | 是 
 
 <font size=6>Events</font>
 <table>
    <tr bgColor="#eee">
    <td>事件名称</td><td>说明</td><td>回调函数</td>
    </tr>
    <tr bgColor="#fff"><td>btnClick</td><td>点击tab切换单个按钮时触发的事件</td><td>可获取当前点击的按钮信息</td></tr>
 </table>


### mainBox带标题容器框
包括标题、副标题、内容区域
    
   
    <template>
        <main-box>
            <template slot="title">西海岸新区概况</template>
            <template slot="subtitle">环形占比</template>
            <template slot="main">
               <!--内容区-->
            </template> 
        </main-box>
    </template>
![avatar](/images/mainBox1.jpg) ![avatar](/images/mainBox2.jpg)

<font size=6>Attributes</font>

 | 参数 | 说明 | 类型 | 可选值 | 默认值 | 是否必填 
 | - | :- | :-: | :-: | :-:| :-: |
 | titleBgColor | 标题背景图颜色 | String | --         | #18346D | 否
 | titleBgType  | 标题背景样式   | String | arrow/line | arrow   | 否

### insideBox内容框
带边框的内容区域，带阴影和不带阴影

    <template>
        <inside-box>
           <!--内容区--> 
        </inside-box>
    </template>
效果图如下：
![avatar](/images/insideBox.jpg) ![avatar](/images/insideBox2.jpg)
### layout整体布局
分为左中右布局方式，左右可收缩

    <template>
        <layout>
		  <template slot="left">
			 <!--左侧内容区-->
		  </template>
		  <template slot="center">
			  <!--中间内容区-->
		  </template>
		  <template slot="right">
			  <!--右侧内容区-->
		  </template>
	  </layout>
    </template>
### classify分类
样式单一，适合展示天气等数据

    <template>
		<classify :value="data"></classify>
	</template>
    <script>
        export default {
            data () {
                return {
                    data:[
                        {"name":"温度","value":"--"},
                        {"name":"湿度","value":"--"},
                        {"name":"风向","value":"--"},
                        {"name":"风速","value":"--"}
                        ]
                };
            }           
        }
    </script>

效果图如下：
![avatar](/images/classify.png)

<font size=6>Attributes</font>

 | 参数 | 说明 | 类型 | 可选值 | 默认值 | 是否必填 
 | - | :- | :-: | :-: | :-:| :-: |
 | value        | 显示的数据          | Array  | -- | -- | 是
 | bigFontSize  | 字体大小(ex:'20')   | String | -- | ""(自适应字体大小) | 否
 | smallFontSize| 字体大小(ex:'14')   | String | -- | "" | 否
 
### message消息

    <template>	
		<message :messageList="messageList"></message>	
    </template>
    <script>
        export default {
            data () {
                return {
                    messageList: [
				  {
				    content: "初小朋提了一个紧急问题111"
				  },
				  {
				    content: "大珠山2号闸机出现故障，待修复222 ;"
				  },
				  {
				    content: "我们的小程序要不能上线啦"
				  }
				]	
                };
            }           
        }
    </script>
效果图如下：
![avatar](/images/message.jpg)

<font size=6>Attributes</font>

 | 参数 | 说明 | 类型 | 可选值 | 默认值 | 是否必填 
 | - | :- | :-: | :-: | :-:| :-: |
 | title        | 消息标题      | String  | -- | 消息动态  | 否
 | messageList  | 消息内容      | Array   | -- | []       | 是
 | titleFontSize| 标题字体大小  | String  | --  | 23px    | 否

### guageBox数据展示

     <template>
        <gauge-box
            :value="value"
            :max="600"
            :title="labelName"
            :lineColors="['#28FF4C', '#74FFDF']"
          ></gauge-box>
     </template>
     <script>
        export default {
            data () {
                return {
                  value: 400,
                  labelName: "一级子公司",	
                };
            }           
        }
    </script>
效果图如下：![avatar](/images/guageBox.jpg)

<font size=6>Attributes</font>

| 参数 | 说明 | 类型 | 可选值 | 默认值 | 是否必填 
 | - | :- | :-: | :-: | :-:| :-: |
 | lineWidth    | 线条宽度      | Number  | --  | 0(值为0时会自适应)         | 否
 | lineColors   | 进度条颜色    | Array   | --  | ['#0a5BFF', '#0d71f9']    | 否
 | lineBGColor  | 背景颜色      | String  | --  | #1C1482                   | 否
 | value        | 值            | Number  | --  | 0                         | 是
 | max          | 最大值        | Number  | --  | 100                       | 否
 | title        | 标题          | String  | --  | ''                        | 是
 | titleFontSize| 标题字体大小   | Number  | --  | 0   |                      否

### ring数据展示

     <template>
        <ring :value="value" :title="labelName"></ring>
     </template>
     <script>
        export default {
            data () {
                return {
                  value: 400,
                  labelName: "一级子公司",	
                };
            }           
        }
    </script>
效果图如下：
![avatar](/images/ring.jpg)


<font size=6>Attributes</font>

| 参数 | 说明 | 类型 | 可选值 | 默认值 | 是否必填 
 | - | :- | :-: | :-: | :-:| :-: |
 | lineWidth    | 线条宽度      | Number  | --  | 10        | 否
 | lineColors   | 进度条颜色    | Array   | --  | #0a5BFF   | 否
 | lineBGColor  | 背景颜色      | String  | --  | #1C1482   | 否
 | value        | 值            | Number  | --  | 0        | 是
 | valueFontSize| 值字体大小     | Number  | --  | 24       | 否
 | title        | 标题          | String  | --  | ''        | 是
 | titleFontSize| 标题字体大小   | Number  | --  | 13        |否

### iconList列表

    <template>
        <icon-list
            :value1="labelName" 
            :value2="value" 
            :value3="after"  										 
            iconColor="#ff5f11"	
            :value1Style="{color:'#00aeff'}"           
            ></icon-list>
    </template>
    <script>
        export default {
            data () {
                return {
                  value: 400,
                  labelName: "一级子公司",	
                  after:'亿元'
                };
            }           
        }
    </script>
效果图如下：
![avatar](/images/iconList1.jpg) ![avatar](/images/iconList2.jpg)

<font size=6>Attributes</font>

| 参数 | 说明 | 类型 | 可选值 | 默认值 | 是否必填 
 | - | :- | :-: | :-: | :-:| :-: |
 | width         | 列表宽度           | String  | --         | 100%        | 否
 | height        | 列表高度           | String  | --         | 20          | 否
 | iconStyle     | 图标样式           | String  | circle/rect|circle       | 否
 | iconWidth     | 图表宽度           | String  | --          | 10         | 是
 | iconHeight    | 图标高度           | String  | --          | 10         | 否
 | iconColor     | 图标颜色           | String  | --          | '#ff5f11'   | 否
 | imgSrc        | 图标也可为图片      | String  | --          |require('./icon1.png') |否
 | value1        | 列表中第一个值      | String  | --          | ''        | 否
 | value2        | 列表中第二个值      | String  | --          | ''        | 否
 | value3        | 列表中第三个值      | String  | --          | ''        | 否
 | value1Style   | 列表中第一个值样式  | Object  | --          | {}       | 否
 | value2Style   | 列表中第二个值样式  | Object  | --          | {}       | 否
 | value3Style   | 列表中第三个值样式  | Object  | --          | {}       | 否

 ### numShow数字滚动效果
 需安装 vue-countup-v2

    <template>
        <num-show :data="show1"></num-show>
    </template>
    <script>
        export default {
            data () {
                return {
                 show1:[{ title: "今日浏览量", num1: 100 ,num2:200}]
                };
            }           
        }
    </script>
效果图如下：
![avatar](/images/numShow.jpg)

### 3D柱状图
基于echarts进行封装的图表

    <template>
        <echartPlus type="3Dbar"/>
    </template>
  效果图如下：
![avatar](/images/3DBar.jpg)
  
<font size=6>Attributes</font>

| 参数 | 说明 | 类型 | 可选值 | 默认值 | 是否必填 
 | - | :- | :-: | :-: | :-:| :-: |
 | config       | 图表配置项        | Object  | --     | {}        | 否
 | type         |图表类型           | String  | 3DBar  | 3DBar     | 是
 | data         | 图表数据          | Array   | --     | []        |是
 | symbolSize   | 柱状图大小(宽，高) | Array   | --     | [40, 16]  | 否
 | symbolColor  | 柱状图颜色         | String  | --     | '#3cefff' | 否
 | circleColor  | 底部圆颜色         | String  | --     | '#14b1eb' | 否
 
