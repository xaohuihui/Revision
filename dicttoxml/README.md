# Revision dicttoxml

> 本次对dicttoxml库更改的功能有两个
> > 1. 将美化xml过程融合到转化过程中
> > 2. 加入支持最大层级配置，超出该层级的dict将被转化为string用一个标签封装起来

[dicttoxml包修改后源码](./dicttoxml.py)

使用方式

```python
# 假设dicttoxml.py放入项目下utils包中
from utils.dicttoxml import dicttoxml
# query_info()获取dict数据方法，替换为自己的获取数据方法
data = query_info()
# 传入dicttoxml方法中，max_lev配置为7则说明dict最大层级支持到7级，若需要全部转化，max_lev参数不要传递即可
xml = dicttoxml(data, max_lev=7)
# 写入xml文件
with open(os.path.join(filepath, filename), "wb") as fp:
    fp.write(xml)
```

