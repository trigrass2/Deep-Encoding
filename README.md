# Deep Encoding
Created by [Hang Zhang](http://hangzh.com/)

## Introduction
This repo is a Torch implementation of Deep Encoding as described in the ArXiv [paper](https://arxiv.org/pdf/1612.02844.pdf)
```
@article{zhang2016deep,
  title={Deep TEN: Texture Encoding Network},
  author={Zhang, Hang and Xue, Jia and Dana, Kristin},
  journal={arXiv preprint arXiv:1612.02844},
  year={2016}
}
```

## Install
```bash
git clone https://github.com/zhanghang1989/Deep-Encoding
cd Deep-Encoding && luarocks make
```

## Experiments
0. The Joint Encoding experiment in Sec4.2 will execute by default:

  ```bash
  cd experiments
  th main.lua
  ```
0. Training Deep-TEN on MINC-2500 in Sec4.1. Please download the pre-trained
[ResNet-50](https://d2j0dndfm35trm.cloudfront.net/resnet-50.t7) Torch model 
and the [MINC-2500](http://opensurfaces.cs.cornell.edu/static/minc/minc-2500.tar.gz) dataset to ``minc`` folder before executing the program:

  ```bash
  th main.lua -retrain resnet-50.t7 -ft true \
  -netType encoding -nCodes 32 -dataset minc \
  -data minc/ -nClasses 23 -batchSize 64 \
  -nGPU 4 -multisize true
  ```
