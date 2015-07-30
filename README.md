second_bigdata
==============
比赛背景

    随着近年来互联网的飞速发展，个性化推荐已成为各大主流网站的一项必不可少服务。提供各类新闻的门户网站是互联网上的传统服务，但是与当今蓬勃发展的电子商务网站相比，新闻的个性化推荐服务水平仍存在较大差距。一个互联网用户可能不会在线购物，但是绝大部分的互联网用户都会在线阅读新闻。因此资讯类网站的用户覆盖面更广，如果能够更好的挖掘用户的潜在兴趣并进行相应的新闻推荐，就能够产生更大的社会和经济价值。初步研究发现，同一个用户浏览的不同新闻的内容之间会存在一定的相似性和关联，物理世界完全不相关的用户也有可能拥有类似的新闻浏览兴趣。此外，用户浏览新闻的兴趣也会随着时间变化，这给推荐系统带来了新的机会和挑战。因此，希望通过对带有时间标记的用户浏览行为和新闻文本内容进行分析，挖掘用户的新闻浏览模式和变化规律，设计及时准确的推荐系统预测用户未来可能感兴趣的新闻

任务

    参赛选手需要根据训练集中的浏览记录以及新闻的详细内容，尽可能多的预测出测试集中的数据，即预测每一个用户最后一次浏览的新闻编号。

数据集描述

    在本次竞赛中，我们从国内某著名财经新闻网站—财新网随机选取了10000名用户，并抽取了这10000名用户在2014年3月的所有新闻
浏览记录，每条记录包括用户编号、新闻编号、浏览时间（精确到秒）以及新闻文本内容，其中用户编号已做匿名化处理，防止暴露用户隐私。

我的解决方案

    首先是根据基于用户的相似度来计算用户u的TopN最近邻的用户，然后基于TopN用户计算总的新闻的并集U,在新闻并集的基础上，
采用核密度估计的方法，对每一篇新闻进行兴趣度计算，最后在兴趣度的基础上结合新闻时效性（流行度）的值，综合加权，
最终得到对于每一个项目的评分值，根据评分值以及该用户u的新闻阅读能力来推荐TopK用户。

评价标准

    F1值大小

程序组成部分：

    factor.py:计算老化系数
    
    latest_new.py:记录每个用户的最后浏览的时间，以及每个新闻的发布时间
    
    read_file.py:建立新闻、用户、时间映射矩阵
    
    read_file1.py:读取用户集合，用户
    
    recommend.py:程序主函数，根据解决方案，实现功能
    
详细阐述在pdf文档中
