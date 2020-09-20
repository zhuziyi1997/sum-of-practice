## Python Day16

1.
```Python
  prices = {
     'AAPL': 191.88,
     'GOOG': 1186.96,
     'IBM': 149.24,
     'ORCL': 48.44,
     'ACN': 166.89,
     'FB': 208.09,
     'SYMC': 21.29
  }
  # 用股票价格大于100元的股票构造一个新的字典
 prices2 = {key: value for key, value in prices.items() if value >100}
 print(prices2)

```

2.
```Python
"""
从列表中找出最大的或最小的N个元素
堆结构(大根堆/小根堆)
"""

  list1 = [34, 25, 12, 99, 87, 63, 58, 78, 88, 92]
  list2 = [
     {'name': 'IBM', 'shares': 100, 'price': 91.1},
     {'name': 'AAPL', 'shares': 50, 'price': 543.22},
     {'name': 'FB', 'shares': 200, 'price': 21.09},
     {'name': 'HPQ', 'shares': 35, 'price': 31.75},
     {'name': 'YHOO', 'shares': 45, 'price': 16.35},
     {'name': 'ACME', 'shares': 75, 'price': 115.65}
  ]
  import heapq
  print(heapq.nlargest(3,list1))
  print(heapq.nsmallest(3,list1))

  
 ```

3.
```Python
"""
找出序列中出现次数最多的元素
"""

  words = [
     'look', 'into', 'my', 'eyes', 'look', 'into', 'my', 'eyes',
     'the', 'eyes', 'the', 'eyes', 'the', 'eyes', 'not', 'around',
     'the', 'eyes', "don't", 'look', 'around', 'the', 'eyes',
     'look', 'into', 'my', 'eyes', "you're", 'under'
  ]

import Counter from collections
counter = Counter(words)
print(couter.most_common(3))

 ```
 
 4.数据结构和算法
- 评价算法的好坏：渐近时间复杂度和渐近空间复杂度。

- 渐近时间复杂度的大O标记：
  - <img src="http://latex.codecogs.com/gif.latex?O(c)" /> - 常量时间复杂度 - 布隆过滤器 / 哈希存储
  - <img src="http://latex.codecogs.com/gif.latex?O(log_2n)" /> - 对数时间复杂度 - 折半查找（二分查找）
  - <img src="http://latex.codecogs.com/gif.latex?O(n)" /> - 线性时间复杂度 - 顺序查找 / 计数排序
  - <img src="http://latex.codecogs.com/gif.latex?O(n*log_2n)" /> - 对数线性时间复杂度 - 高级排序算法（归并排序、快速排序）
  - <img src="http://latex.codecogs.com/gif.latex?O(n^2)" /> - 平方时间复杂度 - 简单排序算法（选择排序、插入排序、冒泡排序）
  - <img src="http://latex.codecogs.com/gif.latex?O(n^3)" /> - 立方时间复杂度 - Floyd算法 / 矩阵乘法运算
  - <img src="http://latex.codecogs.com/gif.latex?O(2^n)" /> - 几何级数时间复杂度 - 汉诺塔
  - <img src="http://latex.codecogs.com/gif.latex?O(n!)" /> - 阶乘时间复杂度 - 旅行经销商问题 - NPC
  
  5.简单选择排序
  像排队一样，从队伍第一个人开始，有比他矮的就让那个人代替他的位置去到队伍最前面。一共需要比较n(n-1)/2次。
  ```Python
  def select_sort(items, comp = lambda x, y: x<y):
    items = items[:]
    for i in range(len(items)-1):
       min_index = i
       for j in range(i+1,len(items)):
         if comp(items[j], items[min_index]):
           min_index = j
       items[min_index], items[i] = items[i], items[min_index]
    return(items)

  ```
  
  6.冒泡排序
  左右交换，把大的放在右边，然后把大的再和新的比较，所以第一轮左右交换结束就可以得到第一大的归位（共有n-1次比较）；第二轮交换结束得到第二大的归位（共有n-2次比较）。
  以此类推直至得到第n-1个大的结束。一共需要比较n(n-1)/2次。
   ```Python


  ```
  
  7.搅拌排序
  在冒泡排序的基础上升级，先一轮左右排序把最大的放在最右边，再回过头右左排序，把最小的放在最左边。
  ```Python


  ```

  8.合并有序列
  ```Python


  ```
  
  9.查找某个东西
  ```Python


  ```
  
  10.折半查找
  ```Python


  ```
  
  11.百钱百鸡
  ```Python


  ```
  
  12.贪婪法
  ```Python


  ```
  
  13.动态规划
  子列表中元素和的最大值
  ```Python
  def main():
    items = list(map(input().split()))
    overall = partitial = items[0]
    for i in range(1,len(items)):
      partitial = max(partitial, partitial+items[i])
      overall = max(overall, partitial)
    print(overall)

  if __name__ == '__main__':
    main()
  ```
