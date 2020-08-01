# Sat2Graph 
Sat2Graph: Road Graph Extraction through Graph-Tensor Encoding

Paper: [arxiv.org/pdf/2007.09547.pdf](https://arxiv.org/pdf/2007.09547.pdf)

### Abstract

Inferring road graphs from satellite imagery is a challenging computer vision task. Prior solutions fall into two categories: (1) pixel-wise segmentation-based approaches, which predict whether each pixel is on a road, and (2) graph-based approaches, which predict the road graph iteratively. We find that these two approaches have complementary strengths while suffering from their own inherent limitations. 
 
In this paper, we propose a new method, Sat2Graph, which combines the advantages of the two prior categories into a unified framework. The key idea in Sat2Graph is a novel encoding scheme, graph-tensor encoding (GTE), which encodes the road graph into a tensor representation. GTE makes it possible to train a simple, non-recurrent, supervised model to predict a rich set of features that capture the graph structure directly from an image. We evaluate Sat2Graph using two large datasets. We find that Sat2Graph surpasses prior methods on two widely used metrics, TOPO and APLS. Furthermore, whereas prior work only infers planar road graphs, our approach is capable of inferring stacked roads (e.g., overpasses), and does so robustly.

![Overview](figures/Sat2Graph2.png)

# Usage
### Download the Dataset

```bash
./download.sh
```
This script will download the full 20-city dataset we used in the paper as well as the pre-trained model. It will also download the dataset partition (which tiles are used for training/validating/testing) we used in the paper for SpaceNet Road dataset. 

### Generate outputs from the pre-trained model
**20-city dataset**
```bash
cd model
python train.py -model_save tmp -instance_id test -image_size 352 -model_recover ../data/20citiesModel/model -mode test
```
This command will generate the output graphs for the testing dataset. You can check out the graphs and visualizations in the 'output' folder. 

**SpaceNet TODO**

### Training 
**20-city dataset**

To train the model, use the following command. 
```
python train.py -model_save tmp -instance_id test -image_size 352
```   

**SpaceNet TODO**



