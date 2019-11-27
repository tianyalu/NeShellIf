# NeShellIf Shell之if语句

## 一、If语句
### 1.1 语法
注意：  
> if()后面不需要{},只需要；  
> 语句一定要有tab键输入，不能是空格。空格在shell语法中不能随便写，是一种特殊的语义，代表分割。  

```bash
#!/bin/bash
if(表达式);then
	语句1
else
	语句2
fi
```
示例：  
```bash
#!/bin/bash
NUM1=100
NUM2=200
if(($NUM1>$NUM2));
	echo "NUM1 > NUM2"
fi
```
实操：  
![image](https://github.com/tianyalu/NeShellLoopAndFileOpt/blob/master/show/if_compare.png)

### 1.2 逻辑运算符
运算符 | 说明
--    | --
-f    | 判断文件是否存在
-d    | 判断目录是否存在
-eq   | 等于（整型比较）
-ne   | 不等于比较
-lt   | 小于比较
-le   | 小于等于比较
-gt   | 大于比较
-ge   | 大于等于比较
-a    | 双方都成立
-o    | 单方成立


## 二、目录文件操作
### 2.1 目录操作
```bash
#!/bin/bash
if [ ！ -d ./testdir ];then  #目录是否存在
	mkdir -p testdir
else
	echo "目录已经存在"
fi
```
实操：  
![image](https://github.com/tianyalu/NeShellLoopAndFileOpt/blob/master/show/if_dir_exist.png)


### 2.2 文件操作
```bash
#!/bin/bash
NDK=./text.txt
if [ ! -f $NDK ]; then  #文件是否存在
        touch $NDK
        echo "这是一个测试用的文本文件，\n迎娶白富美，走上人生巅峰" > $NDK
        echo "文件创建完成"
else
        echo "文件已存在"
        cat $NDK
fi
```
实操：  
![image](https://github.com/tianyalu/NeShellLoopAndFileOpt/blob/master/show/if_file_exist.png)