# 常见的时序特征工程技术

## 时间序列特征组织格式  


## 常见技术

时间序列数据的特征工程是一种技术[<sup>[1]</sup>](#refer-anchor-1)，用于从时间序列数据中提取信息或构造特征，常见的技术如下：  
1.滚动统计量  
计算时间窗口内的统计量，如平均值、中位数、标准偏差、最小值和最大值。这些统计量可以捕捉到时间序列在不同时间段的行为变化。

2.滞后特征  
创建时间序列的过去值作为新的特征，以揭示序列的自相关性质。例如，可以使用前一天（滞后1）或前一周（滞后7）的数据作为预测当前值的特征。

3.差分和季节特征  
计算时间序列的一阶差分（即当前值与前一个值的差）或季节性差分（如当前值与前一年同一天的值的差）来帮助去除趋势和季节性影响。

4.变换  
应用变换如对数变换、平方根变换等，可以帮助稳定时间序列的方差，使其更适合某些统计模型。

5.时间戳信息  
提取时间戳的特定部分，如小时、周天、月份等，用于捕捉周期性模式。

6.傅立叶变化  
通过傅里叶变换将时间序列转换为频域表示，提取周期性特征。

7.波动性度量  
对于金融时间序列，可以计算历史波动性或返回序列的标准偏差等度量。

8.窗口函数  
使用滑动窗口操作，如滑动平均或指数平滑，以平滑时间序列并减少噪声。

## kaggle时序特征工程[<sup>[2]</sup>](#refer-anchor-2)

## scikit-kearn时序特征工程[<sup>[3]</sup>](#refer-anchor-3)

## 处理技术

### 小规模数据处理
[feature-engine](https://pypi.org/project/feature-engine/)是一个python库，为机器学习模型提供多种转换器用于特征设计和选择，参考scikit-learn的功能设计，使用fit和tansform方法学习和转换特征。  
**缺失数据处理**  
提供了多种填充缺失值的策略，如使用均值、中位数、众数或指定的常数来填充。  
提供添加缺失数据指示器的功能，这可以帮助模型识别数据缺失的模式。  
**分类变量编码**  
支持多种编码策略，如独热编码、序数编码、计数编码、目标编码（Mean encoding）、权重风险比编码等。  
**连续变量变换**  
提供了对数变换、倒数变换、平方根变换等多种数学变换，帮助处理偏态数据。  
包括离散化连续变量的功能，如等距离散化、等频离散化或使用决策树分箱等。  
**特征缩放**  
包括最常见的缩放方法，如最大最小缩放（Min-Max Scaling）、标准缩放（Standard Scaling）和均值正规化。  
**特征选择**  
提供基于各种统计检验和模型性能的特征选择方法，例如基于相关系数、卡方检验、递归特征消除等。  
**特征组合**  
支持创建特征的交互项，如两个变量的乘积或其他复合关系。  

### 大规模数据处理
pyspark处理时间序列特征[<sup>[4]</sup>](#refer-anchor-4)  
**特征预处理**  
二值化和分桶  
最小最大标准化  
绝对值归一化  
特征标准化  
Normalizer  
多项式特征（PolynomiaExpansion）  
独热编码（OnehotEncoder）  
降维PCA  

**日期特征**  
日期拆解类[^5]  
日期判断类  
节假日处理  

**统计特征**  
滞后特征  
滑窗统计特征  



## 参考
<div id="refer-anchor-1"></div>

[1] [deephub时序特征工程介绍](https://cloud.tencent.com/developer/article/2412859)  

<div id="refer-anchor-2"></div>

[2] [kaggle时序特征](https://www.kaggle.com/code/patrickurbanke/feature-engineering-for-time-series) 

<div id="refer-anchor-3"></div>

[3] [scikit-learning时序特征工程](https://scikit-learn.org/stable/auto_examples/applications/plot_cyclical_feature_engineering.html)

<div id="refer-anchor-4"></div>

[4] [pyspark时序特征工程](https://blog.csdn.net/fitzgerald0/article/details/116453472)

[^5] [pyspark时序特征工程](https://blog.csdn.net/fitzgerald0/article/details/116453472)