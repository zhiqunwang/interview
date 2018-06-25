# Java 面试题总结

### JVM
    1.Java 内存空间结构
      *栈：线程私有，每进入一个方法会创建一个栈帧（栈帧存放方法的局部变量，常量池指针，操作数栈,  

      在没有逃逸的情况下，小对象可直接栈上分配）通过-Xss128k参数来分配每个线程的堆栈空间大小  

      * 堆：存放数组，对象，分eden区，old区，通过-Xmx2G -Xms 分配堆内存大小,-Xmn eden区大小
      * 方法区（永久区） 保存装载的类信息（字段、方法信息，方法字节码)  

      * 本地方法区           

    2.Java 对象的创建过程（JVM角度）
      要初始化一个对象，首先要加载该对象所对应的class文件，该文件的数据会被加载到永久代，并创建个底层的instanceClass对象代表改该class，再为将要初始化的对象分配内存空间，优先在线程私有空间上分配（栈上分配），如果分配空间不足或者存在逃逸情况，再到eden区分配。


