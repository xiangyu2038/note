##awk基本结构
   awk 'BEGIN{} pattern {} END {}'
   例如 awk 'BEGIN {print "start"}  {print} END{print "end"} '   
   
## 内置变量 
   NR 行号   行号打印出来是每一行都打印出来    可以对行号进行判断只显示当前行号的内容   awk 'NR==1298 { print NR}'  cc.log 
   NF 字段数   打印字段数只会出现最大字段数的值
   FS 字段分隔符
   $0 整行 
   $1 第一个字段
   
## print 
   print 可以这样使用 print "aa","bb"  打印出来的aa和bb用空格分隔 不适用逗号表示不分隔
   
##定义变量
   awk 'var1=="heihei";var2=="hehe" print var1;print var2'   定义了变量并打印出来 
## 累加操作
  awk 'BEGIN {sum = 0 ;  } {sum++;print sum} END {print sum}'  cc.log   进行简单的累加操作示例
##搜索操作
  搜索其中的字符串 awk '/aa/' cc.log  在cc.log中搜索cc
## 指定分隔符
  awk -F :  指定":" 为分隔符
##使用for循环 
  awk 'BEGIN {for(i=0;i<5;i++) print i }'   
 ##操作数组 
 awk 'BEGIN{a[0]=2}' 给数组赋值  基本操作
## for循环取出数组里面的值 
 awk '{lifo[NR]=$0}END{for(lino=NR;lino>0;lino--){print lifo[lino];}}'   //这里取出数组的值并打印  
 
 #基本操作到此结束
      