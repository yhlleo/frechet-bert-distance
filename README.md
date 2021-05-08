# Assessing Dialogue Systems with Distribution Distances

 [[arXiv]](https://arxiv.org/pdf/2105.02573.pdf)[[code]](https://github.com/yhlleo/frechet-bert-distance)

> We propose to measure the performance of a dialogue system by computing the distributionwise distance between its generated conversations and real-world conversations.
 
To appear in Findings of [ACL 2021](https://2021.aclweb.org/). 

**UNote that this is not an officially supported Tencent product.**
 
## 1. Configuratin 

This repository requires the packages:
 - pytorch
 - [huggingface/transformers](https://github.com/huggingface/transformers).


## 2. Usage

To evaluate the system-level human correlations of metrics, use:

```
python eval_metric.py \
  --data_path ./datasets/convai2_annotation.json \
  --metric fbd \
  --sample_num 10 \
  --model_type roberta-base \
  --batch_size 32
```

Here are some details of the six corpura compared in the main paper:

|File Name|Dataset Name|Num. of Samples|Reference|
|:-----:|:-----:|:-----:|:----:|
|[`personam_annotation.json`](./datasets/personam_annotation.json)|Persona(M)|60|[Shikib/usr](http://shikib.com/usr)|
|[`dailyh_annotation.json`](./datasets/dailyh_annotation.json)|Daily(H)|150|[li3cmz/GRADE](https://github.com/li3cmz/GRADE/tree/main/evaluation)|
|[`convai2_annotation.json`](./datasets/convai2_annotation.json)|Convai2|150|[li3cmz/GRADE](https://github.com/li3cmz/GRADE/tree/main/evaluation)|
|[`empathetic_annotation.json`](./datasets/empathetic_annotation.json)|Empathetic|150|[li3cmz/GRADE](https://github.com/li3cmz/GRADE/tree/main/evaluation)|
|[`dailyz_annotation.json`](./datasets/dailyz_annotation.json)|Daily(Z)|100|[ZHAOTING/dialog-processing](https://github.com/ZHAOTING/dialog-processing/tree/master/src/tasks/response_eval)|
|[`personaz_annotation.json`](./datasets/personaz_annotation.json)|Persona(Z)|150|[ZHAOTING/dialog-processing](https://github.com/ZHAOTING/dialog-processing/tree/master/src/tasks/response_eval)|


## Citation
If you use this research/codebase/dataset, please cite our paper.
```
@article{xiang2021assessing,
  title={Assessing Dialogue Systems with Distribution Distances},
  author={Xiang, Jiannan and Liu, Yahui and Cai, Deng and Li, Huayang and Lian, Defu and Liu, Lemao},
  journal={arXiv preprint arXiv:2105.02573},
  year={2021}
}
```

Other related papers:

 - [1] FID, [GANs Trained by a Two Time-Scale Update Rule Converge to a Local Nash Equilibrium](https://arxiv.org/abs/1706.08500), NIPS 2017
 - [2] PRD, [Assessing Generative Models via Precision and Recall](https://arxiv.org/abs/1806.00035), NIPS 2018
 - [3] BERTScore, [BERTScore: Evaluating Text Generation with BERT](https://arxiv.org/abs/1904.09675), ICLR 2020