# Weekly Report

### 2021-7-14

#### meeting log

- paper explanation
    - ①Visual Compositional Learning for Human-Object Interaction Detection
        - extract human features, verb features and object features from different image (Faster RCNN)
        - combine the verb and object feature to compose a new HOI sample
    - ②Discovering Human Interactions with Novel Objects via Zero-Shot Learning
        - novel human center object region proposal network -> only detect the object interacting with human
        - estimate the possibility of unseen object by the possibility of seen object and their similarity
    - ③Zero-Shot Human-Object Interaction Recognition via Affordance Graphs
        - use external affordance graph to get the class representation
        - estimated labels of the unseen verb to weakly-supervised
        - extract the visual feature and turn it to representation A(action) and O(verb)
        - calculate the similarity and use the labels to train
- ①中直接将 verb 和 object拼接得到的feature，仍然包含提取verb的image的背景，使得这种组合在实际中可能根本不会存在



### 2021-7-22

#### meeting log

- paper explanation
    - ①Detecting Human-Object Interaction via Fabricated Compositional Learning
        - extract human features, verb features and object features(Faster RCNN)
        - use (verb feature) and (word embedding) to generate fake object feature
        - combine the verb and object feature to compose a new HOI sample
    - ②DGIG-Net: Dynamic Graph-in-Graph Networks for Few-Shot Human–Object Interaction
        - meta learning
        - support set { five categories one shot / five categories five shots}
        - use GCN to regularize the image representation and get the visual representation of HOI(use image visual representation and word embedding to visual representation)
- ①中用于生成Fake Object的Fabricator仍有改进余地，目前针对确定的verb feature，Fabricator 应用（verb,$v_{obj}$,noise）-> 确定的object feature，考虑应该得到一个与 verb相关 的 feature 分布
- ②中用到了将 semantic information 转换到 visual representation 并与 image visual representation 融合
- ②中loss函数的cross entropy 有 $\sum_{N_c}$ 的符号，目前$N_c$意义还未弄清​

#### to do

- [ ] 重读已经读过的几篇paper，将其进行分类整理
    - 分类主要依据 method的思路、dataset performance
- [ ] 对于Zero-shot HOI的几篇文章，对应的各个模型在基本数据集上的表现做成表
- [ ] 针对有code的paper进行精读，同时选出感兴趣且code质量比较高的模型
- [ ] 考虑①中fake object生成过程的改进
- [ ] 考虑（affordance graph）文章中利用其它信息推测 unseen action 和 unseen object 交互的 possibility 的方法
- [ ] 准备讲paper

