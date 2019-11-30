### Python 小例子

#### 关于此库

Python小例子、小Demo一网打尽。Python基础、Web开发、数据科学、机器学习、TensorFlow、Pytorch，你能想到的基于Python的小Demo都在这里。

#### 欢迎贡献

比如github账号为`lhxon`的小伙伴，fork此库后，按照如下步骤贡献：
```markdown
1. git clone https://github.com/lhxon/python-small-examples
2. git add . 
3. git commit -m "xiugai"
4. git push
5. 界面点击：pull requests，根据操作即可。如遇问题，欢迎联系我。
```

#### 小例子列表
1. 交换两个元素
```python
def swap(a, b):
    return b, a
print(swap(1, 0))  # (0,1)
```

2. 求斐波那契数列前n项
```python
def fibonacci(n):
    a, b = 1, 1
    for _ in range(n):
        yield a
        a, b = b, a + b
list(fibonacci(5))  # [1, 1, 2, 3, 5]
```

3. 返回更长列表
```python
def max_length(*lst):
    return max(*lst, key=lambda v: len(v))

max_length([1, 2, 3], [4, 5, 6, 7], [8]) # [4, 5, 6, 7]

```
4. 返回更短列表
```python
def min_length(*lst):
    return min(*lst, key=lambda v: len(v))

min_length([1, 2, 3], [4, 5, 6, 7], [8]) # [8]

```

5. 合并两个字典
```python
def merge_dict(dic1, dic2):
    return {**dic1, **dic2} 
    
merge_dict({'a': 1, 'b': 2}, {'c': 3})  # {'a': 1, 'b': 2, 'c': 3}
```

6. 列表反转
```python
def reverse(lst):
    return lst[::-1]
    
r = reverse([1, -2, 3, 4, 1, 2]) # [2, 1, 4, 3, -2, 1]
```

7. 等分list
```python
from math import ceil

def divide_iter(lst, n):
    if n <= 0:
        yield lst
        return
    i, div = 0, ceil(len(lst) / n)
    while i < n:
        yield lst[i * div: (i + 1) * div]
        i += 1

list(divide_iter([1, 2, 3, 4, 5], 0))  # [[1, 2, 3, 4, 5]]
list(divide_iter([1, 2, 3, 4, 5], 2))  # [[1, 2, 3], [4, 5]]
```

8. 查找指定后缀的文件
```python
import os

def find_file(work_dir,extension='jpg'):
    lst = []
    for filename in os.listdir(work_dir):
        print(filename)
        splits = os.path.splitext(filename)
        ext = splits[1] # 拿到扩展名
        if ext == '.'+extension:
            lst.append(filename)
    return lst

r = find_file('.','md')  # 返回所有目录下的md文件
```

9. 多列表最大值
```python 
def max_lists(*lst):
    return max(max(*lst, key=lambda v: max(v)))

max_lists([1, 2, 3], [6, 7, 8], [4, 5])# 8
```

10. 多列表最小值
```python
def min_lists(*lst):
    return min(min(*lst, key=lambda v: max(v)))

min_lists([1, 2, 3], [6, 7, 8], [4, 5])# 1 
```

11. 出现最多元素
```python
def max_frequency(lst):
    return max(lst, default='列表为空', key=lambda v: lst.count(v))


lst = [1, 3, 3, 2, 1, 1, 2]
r = max_frequency(lst)
print(f'{lst}中出现次数最多的元素为:{r}')  # [1, 3, 3, 2, 1, 1, 2]中出现次数最多的元素为:1
```
12. 打印99乘法表
```python
for i in range(1,10):
    for j in range(1,i+1):
        print('{0}*{1}={2}'.format(j,i,j*i),end="\t")
    print()
```
结果：
```markdown
1*1=1
1*2=2   2*2=4
1*3=3   2*3=6   3*3=9
1*4=4   2*4=8   3*4=12  4*4=16
1*5=5   2*5=10  3*5=15  4*5=20  5*5=25
1*6=6   2*6=12  3*6=18  4*6=24  5*6=30  6*6=36
1*7=7   2*7=14  3*7=21  4*7=28  5*7=35  6*7=42  7*7=49
1*8=8   2*8=16  3*8=24  4*8=32  5*8=40  6*8=48  7*8=56  8*8=64
1*9=9   2*9=18  3*9=27  4*9=36  5*9=45  6*9=54  7*9=63  8*9=72  9*9=81
```
13. 字符串的字节长
```python
def str_byte_len(mystr):
    return (len(mystr.encode('utf-8')))

str_byte_len('i love python')  # 13(个字节)
```





[更多小例子](./md/README.md)
















