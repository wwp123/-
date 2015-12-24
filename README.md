#日历插件(响应式版)

####官方地址:http://www.bootcss.com/p/bootstrap-datetimepicker/

##兼容性
* IE9+


##样例：

###1、使用步骤
* 引入样式文件

```javascript
<link href="style/datepicker.less" rel="stylesheet" type="text/less" />
```
* 引入js

```javascript
<script src="javascript/jquery-2.1.3.js" type="text/javascript" charset="utf8"></script>
<script src="javascript/date-timepicker.js" type="text/javascript" charset="utf8"></script>
```
 
* 在页面上配置使用参数：

```javascript
    //单个日历选择
    $('.form_datetime').datetimepicker({
        format: 'yyyy-mm-dd hh:ii',
        weekStart: 1,
        todayBtn:  1,
        autoclose: 1,
        todayHighlight: 1,
        startView: 2,
        forceParse: 0,
        showMeridian: 1,
        pickerPosition:'bottom-left'
    });

    //起始时间与结束时间日历
    var enddatetime;
    var startdatetime;
    $('.form_datetime_range1 input').hover(function(){
        $('.form_datetime_range1').datetimepicker({
            format:'yyyy-mm-dd hh:ii',
            weekStart: 1,
            todayBtn:  1,
            autoclose: 1,
            todayHighlight: 1,
            startView: 2,
            forceParse: 0,
            showMeridian: 1,
//                        endDate: enddatetime,
            pickerPosition:'bottom-left',
//                            linkField:'dtp_input5',
//                            linkFormat: "yyyy-mm-dd hh:ii",
            endDate: enddatetime,
        }).on('changeDate', function(ev){
            $('.form_datetime_range2').datetimepicker('remove');
            startdatetime=$('.form_datetime_range1 input').val();
        });
    });
```

* 在页面上添加代码

```javascript

<div class="input-group date form_datetime "  data-date-format="dd MM yyyy - HH:ii p" data-link-field="dtp_input1">
    <input class="form-control" type="text" value="" placeholder="发布时间" />
    <span class="input-group-addon"><span class="fa fa-calendar"></span></span>
</div>
<input type="hidden" id="dtp_input1" value="" />
    
```
###2、demo
* http://192.168.14.97:8080/acc/Ehome/dyzx/plugin-datetimepicker.html

##方法和API
###1、方法
     datetimepicker(options)
     
###2、参数说明
     format:日期格式
     weekStart:一周从哪一天开始。0（星期日）到6（星期六）
     startDate：开始时间
     endDate：结束时间
     autoclose:当选择一个日期之后是否立即关闭此日期时间选择器
     startView:日期时间选择器打开之后首先显示的视图。 可接受的值
     minView:日期时间选择器所能够提供的最精确的时间选择视图
     maxView:日期时间选择器最高能展示的选择范围视图
     todayBtn:如果此值为true 或 "linked"，则在日期时间选择器组件的底部显示一个 "Today" 按钮用以选择当前日期。如果是true的话，"Today" 按钮仅仅将视图转到当天的日期，如果是"linked"，当天日期将会被选。
     todayHighlight:如果为true, 高亮当前日期
     keyboardNavigation:是否允许通过方向键改变日期
     language:当选择器关闭的时候，是否强制解析输入框中的值。也就是说，当用户在输入框中输入了不正确的日期，选择器将会尽量解析输入的值，并将解析后的正确值按照给定的格式format设置到输入框中
     minuteStep:此数值被当做步进值用于构建小时视图。对于每个 minuteStep 都会生成一组预设时间（分钟）用于选择
     pickerPosition:此选项当前只在组件实现中提供支持。通过设置选项可以讲选择器放倒输入框下方


