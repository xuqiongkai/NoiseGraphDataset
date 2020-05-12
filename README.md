# Noise Graph Dataset

Graph datasets for vertext classification task, including modified version with synthetic noise edges.

### Dataset format

Several datasets collected from different sources are included in this project. Each dataset is assigned with a `prefix`. Then the folder structure and file names are determined by following rules:

    .
    ├── prefix
    │   ├── prefix.content
    │   ├── prefix.feature
    │   ├── prefix.cites
    │   ├── prefix.label
    │   ├── prefix.meta
    │   
    │   ├── prefix.cites.add10
    │   ├── prefix.cites.add5
    │   ├── prefix.cites.reduce10
    │   ├── prefix.cites.reduce5
    │   
    │   ├── README
    │   
    └── ...

#### Components

* **prefix.content**: original data content in tab-separated format with each row describing one document, containing the one-hot encoded word vector indicating the absence/presence of corresponding word in a certain document, while the first and last element indicates the ID and class label of this document
* **prefix.cites**: links in tab-separated format with each row denoting a single edge; the two elements separated by the tab are the two vertices connected by this link
* **prefix.meta**: dictionary of all possible class labels in this dataset

* **prefix.label (optional)**: parsed labels from content file, each row contains the tab separated entry ID and class label
* **prefix.feature (optional)**: serialized feature matrix in `torch.Tensor`

#### Noisy variants

* **prefix.cites.add5**: links data with additional 5% random links
* **prefix.cites.add10**: links data with additional 10% random links
* **prefix.cites.reduce5**: links data by randomly removing 5% links from the original
* **prefix.cites.reduce10**: links data by randomly removing 10% links from the original

### Datasets

#### Cora

**Cora** is a citation dataset consisting of 2708 vertices (scientific publications), and 5429 edges (citations). All publications are classified into 7 classes (research topics):

    * Rule Learning
    * Genetic Algorithms
    * Reinforcement Learning
    * Neural Networks
    * Probabilistic Methods
    * Case Based
    * Theory

#### Citeseer

**Citeseer** is a citation dataset consisting of 3312 vertices (scientific publications) and 4723 edges (citations). All publications are classified into 6 classes:

    * Agents
    * AI
    * DB
    * IR
    * ML
    * HCI

#### WebKB

**WebKB** is a website dataset collected from four computer science departments in different universities which contains 877 vertices (web pages) and 1608 edges (hyper-links). All websites are classified 5 classes:

    * faculty
    * students
    * project
    * course
    * other
    
### Acknowledgement

It would be appreciated to cite the related publications if you decide to use these datasets in your work.

#### Noisy and synthetic settings

@inproceedings{xu2017attentive,
&nbsp;&nbsp;&nbsp;&nbsp;title={Attentive graph-based recursive neural network for collective vertex classification},
&nbsp;&nbsp;&nbsp;&nbsp;author={Xu, Qiongkai and Wang, Qing and Xu, Chenchen and Qu, Lizhen},
&nbsp;&nbsp;&nbsp;&nbsp;booktitle={Proceedings of the 2017 ACM on Conference on Information and Knowledge Management},
&nbsp;&nbsp;&nbsp;&nbsp;pages={2403--2406},
&nbsp;&nbsp;&nbsp;&nbsp;year={2017}
}

#### Cora

@article{mccallum2000automating,  
&nbsp;&nbsp;&nbsp;&nbsp;title={Automating the construction of internet portals with machine learning},  
&nbsp;&nbsp;&nbsp;&nbsp;author={McCallum, Andrew Kachites and Nigam, Kamal and Rennie, Jason and Seymore, Kristie},  
&nbsp;&nbsp;&nbsp;&nbsp;journal={Information Retrieval},  
&nbsp;&nbsp;&nbsp;&nbsp;volume={3},  
&nbsp;&nbsp;&nbsp;&nbsp;number={2},  
&nbsp;&nbsp;&nbsp;&nbsp;pages={127--163},  
&nbsp;&nbsp;&nbsp;&nbsp;year={2000},  
&nbsp;&nbsp;&nbsp;&nbsp;publisher={Springer}  
}


#### Citeseer

@inproceedings{giles1998citeseer,  
&nbsp;&nbsp;&nbsp;&nbsp;title={CiteSeer: An automatic citation indexing system},  
&nbsp;&nbsp;&nbsp;&nbsp;author={Giles, C Lee and Bollacker, Kurt D and Lawrence, Steve},  
&nbsp;&nbsp;&nbsp;&nbsp;booktitle={Proceedings of the third ACM conference on Digital libraries},  
&nbsp;&nbsp;&nbsp;&nbsp;pages={89--98},  
&nbsp;&nbsp;&nbsp;&nbsp;year={1998},  
&nbsp;&nbsp;&nbsp;&nbsp;organization={ACM}  
}  

#### WebKB

@inproceedings{Craven:1998:LES:295240.295725,  
&nbsp;&nbsp;&nbsp;&nbsp;author = {Craven, Mark and DiPasquo, Dan and Freitag, Dayne and McCallum, Andrew and Mitchell, Tom and Nigam, Kamal and Slattery, Se\'{a}n},  
&nbsp;&nbsp;&nbsp;&nbsp;title = {Learning to Extract Symbolic Knowledge from the World Wide Web},  
&nbsp;&nbsp;&nbsp;&nbsp;booktitle = {Proceedings of the Fifteenth National/Tenth Conference on Artificial Intelligence/Innovative Applications of Artificial Intelligence},  
&nbsp;&nbsp;&nbsp;&nbsp;series = {AAAI '98/IAAI '98},  
&nbsp;&nbsp;&nbsp;&nbsp;year = {1998},  
&nbsp;&nbsp;&nbsp;&nbsp;location = {Madison, Wisconsin, USA},  
&nbsp;&nbsp;&nbsp;&nbsp;pages = {509--516},  
&nbsp;&nbsp;&nbsp;&nbsp;numpages = {8},  
&nbsp;&nbsp;&nbsp;&nbsp;publisher = {American Association for Artificial Intelligence},  
&nbsp;&nbsp;&nbsp;&nbsp;address = {Menlo Park, CA, USA},  
}   

