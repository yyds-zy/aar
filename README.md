# aar的解压与重打包
在工程中有时候会遇到不同的aar包中包含了相同的so，导致so文件冲突的问题。解决方法除了在build.gradle中添加 pickFirst xxx.so之外，还可以修改aar包。

## 1. 解压aar
将aar解压至tmpDir文件夹
在aar所在路径下打开窗口，输入如下命令：
```
unzip ×××.aar -d tmpDir
```

## 2. 重打包
将tmpDir重新打包成一个新的aar
```
jar cvf ×××NewLib.aar -C tmpDir/ .
```

**注意：不要漏了末尾的 “.”，“tmpDir/” 与 “.” 之间用空格分隔。×××NewLib.aar表示新aar名称。**
