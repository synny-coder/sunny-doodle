# sunny-doodle

Summarize some techniques, cases, interviews, architectures, etc. during development, and record them for future reference
### 项目结构
工程采用的maven的父子项目结构
#### 步骤如下：

![ee0bf28d0dc8877414d616d8c9a912df](https://github.com/user-attachments/assets/4cab6fc6-97da-4bbc-be94-413b60676026)
![6c0067435fad6641800e4f5269d0b3f2](https://github.com/user-attachments/assets/9164bfac-585a-40b9-8f75-b4a3a58e2dda)

### SQL执行顺序
1.FORM：选择from后面跟的表，产生虚拟表1。  
2.ON：ON是JOIN的连接条件，符合连接条件的行会被记录在虚拟表2中。  
3.JOIN：如果指定了LEFT JOIN，那么保留表中未匹配的行就会作为外部行添加到虚拟表2中，产生虚拟表3。如果有多个JOIN链接，会重复执行步骤1~3，直到处理完所有表。  
4.WHERE：对虚拟表3进行WHERE条件过滤，符合条件的记录会被插入到虚拟表4中。  
5.GROUP BY：根据GROUP BY子句中的列，对虚拟表2中的记录进行分组操作，产生虚拟表5。  
6.HAVING：对虚拟表5进行HAVING过滤，符合条件的记录会被插入到虚拟表6中。  
7.SELECT：SELECT到一步才执行，选择指定的列，插入到虚拟表7中。  
8.UNION：UNION连接的两个SELECT查询语句，会重复执行步骤1~7，产生两个虚拟表7，UNION会将这些记录合并到虚拟表8中。  
9.ORDER BY: 将虚拟表8中的记录进行排序，虚拟表9。  
10.LIMIT：取出指定行的记录，返回结果集。  




