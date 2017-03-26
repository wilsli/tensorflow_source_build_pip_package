# TensorFlow 1.0.1 pip package for macOS 10.12.3  

Hardware platform: _Mac mini (Mid 2011)_   ___no OpenCL support___  
- _Model Identifier: Macmini5,1_  
- _Processor Name: Intel Core i5_  
- _Processor Speed:  2.3 GHz_  
- _Number of Processors: 1_  
- _Total Number of Cores: 2_  
- _Memory: 8 GB_  

Software platform: _macOS Sierra version 10.12.3_  
Python version: _3.6_  

I 'pip installed' tensorflow with Anaconda and turned out getting the warnings like "The TensorFlow library wasn't compiled to use SSE4.2(SSE4.1, AVX) instructions, but these are available on your machine and could speed up CPU computations", searched through GitHub and StackOverflow found the only way is building from source with '--copt=-march=native' parameter, so that it could use SSE and AVX instructions to speed up CPU computations.  
So I spent a whole night to setup the building environment(Java8 & bazel) and compile it. After hours of work(mainly waiting), I got this pip package, it works fine on my machine.

Hope it works with other Mac mini machine, and save your time.


**INSTALLATION**
1. clone/download the .whl file to local directory;
2. install the package:  
    `pip install /(your local directory here)/tensorflow-1.0.1-cp3-cp36m-macosx_10_7_x86_64.whl`
3. done!

Then you can test the installation by opening your python console and do the following:  
     `import tensorflow as tf`  
     `hello = tf.constant('Hello, TensorFlow!')`  
     `sess = tf.Session()`  
     `print(sess.run(hello))`  

if everything is fine, there will be not warning but the result of:  
     `b'Hello, TensorFlow!'`  

___ENJOY!___