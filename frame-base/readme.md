# 视频情感分析

包括图像与音频的分析，目前只有图像的输入，而且测试部分还未完成。
使用 Mediaeval 2018 数据集。

## model 文件夹

model_util.py:    
是一些关于模型操作方法的定义，例如 restore,save 等。  
  
model_old.py:  
因为老策略还没有训练完，等老策略的两个目标 Valence, Arousal 训练完毕，更换新策略之后则此文件作废。  
  
model_2D.py:
主要定义的是网络结构，目前有的网络结构是: VGG16, stacked-VGG16, Resnet-50, Densenet  
>stacked-VGG16 是共享权重的哦。
>其实这里是 RNN 也好, LSTM 也好, GRU 也好, 本质的东西是不变的，即使用 RNN 来捕捉时间上前后的语义信息。

model_2D_block.py:
主要定义的是网络中的模块，例如卷积模块，卷积加批正则加激活函数模块，残差模块，瓶颈残差模块，  
瓶颈模块,Densenet 中的 transition block, dense block.

model_3D.py:
定义中...

model_3D_block.py
定义中...

> dynamic_rnn 与 static_rnn 的区别在于，一个是只生成一个 rnn cell，然后通过这个 rnn cell 不断迭代，  
> static_rnn 则是直接构建出很多个 rnn cell，让数据在多个 rnn cell 之间流动。 