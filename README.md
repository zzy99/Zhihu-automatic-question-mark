## 知乎问题自动标注 第二名代码

#### 环境(库)

- pandas
- numpy
- pytorch
- transformers (3.0.2)
- tqdm

#### 模型

- bert-wwm-ext（加载方式见<https://github.com/ymcui/Chinese-BERT-wwm>）

- 对于此次多标签分类任务，可以视作25551类分类，也就是在BERT后加上25551的全连接层，只是输出要加上sigmoid，并且使用BCELoss

#### 参数

- batch_size、max_length根据机器显存适当调整（在不溢出的情况下越大越好，比如32+256）
- epoch越多越好，想得到50分大致要50个epoch以上（我的机器用了四五天。而且我是训一天就提交一下看看的，所以没有精确的最优epoch）
- 后处理时，可以微调分类阈值，略大于0.5会更好

#### 感想

- 任务很简单，但是数据量实在太大，对于一般人的机器不友好
- 上限不止如此，如果换成roberta/模型融合/交叉验证/更多训练轮数，还能提升很多



