## Preprocess the Raw Dataaset
***Since the original repository does not provide the complete raw data preprocessing code, this fork attempts to fill in the missing puzzle pieces and fix some bugs in the original code.***
```
pip install drain3
export ROOT_PATH=path/to/the/downloaded/eadro/dataset
cd codes/preprocess/
python parse_raw_records.py
python parse_raw_metrics.py 
python parse_raw_traces.py
python parse_raw_logs.py
python align.py --name TT
python align.py --name SN
```
## Running Logs (with default hyper parameters)
Because the codebase dependency version is a bit out of date, I have to run the model on CPU for now.
### SN-Dataset
``` 
......
2024-12-05 09:35:47,343 P630747 INFO Epoch 48/50, training loss: 0.06338 [0.88s]
2024-12-05 09:35:48,225 P630747 INFO Epoch 49/50, training loss: 0.04751 [0.88s]
2024-12-05 09:35:49,704 P630747 INFO Test -- F1: 0.9819, Rec: 0.9713, Pre: 0.9927, HR@1: 0.7887, ndcg@1: 0.7887, HR@3: 0.8013, ndcg@3: 0.7966, HR@5: 0.8025, ndcg@5: 0.7971
2024-12-05 09:35:50,605 P630747 INFO Epoch 50/50, training loss: 0.04545 [0.90s]
2024-12-05 09:35:50,605 P630747 INFO * Best result got at epoch 29 with HR@1: 0.8179
2024-12-05 09:35:50,605 P630747 INFO Current hash_id 78e573d7
```

### TT-Dataset
```
......
2024-12-05 09:57:55,381 P640433 INFO Epoch 48/50, training loss: 0.07209 [25.28s]
2024-12-05 09:58:20,640 P640433 INFO Epoch 49/50, training loss: 0.07251 [25.26s]
2024-12-05 09:58:37,872 P640433 INFO Test -- F1: 0.9664, Rec: 0.9867, Pre: 0.9470, HR@1: 0.8822, ndcg@1: 0.8822, HR@3: 0.8838, ndcg@3: 0.8832, HR@5: 0.8839, ndcg@5: 0.8832
2024-12-05 09:59:03,220 P640433 INFO Epoch 50/50, training loss: 0.06844 [25.35s]
2024-12-05 09:59:03,221 P640433 INFO * Best result got at epoch 9 with HR@1: 0.9518
2024-12-05 09:59:03,228 P640433 INFO Current hash_id 0aba95d5
```

<img width="200" alt="截屏2022-09-19 下午9 50 34" src="https://user-images.githubusercontent.com/112700133/191033061-ea4a1671-26c7-4d52-b3ed-3495a2ae0292.png">

![](https://img.shields.io/badge/version-0.1-green.svg) 

****
Artifacts accompanying the paper *Eadro: An End-to-End Troubleshooting Framework for Microservices on Multi-source Data* published at ICSE 2023. 
This tool try to model the intra- and inter-dependencies between microservices for troubleshooting, enabling end-to-end anomaly detection and root cause localization.

<img width="400" alt="dependency_00" src="https://user-images.githubusercontent.com/112700133/191036446-d4cf8d07-bd4e-4452-a3e2-f7d4e9da0624.png">

## Data
Our data are at https://doi.org/10.5281/zenodo.7615393.


## Dependencies
`pip install -r requirements.txt`

## Run
`cd codes & python main.py --data <dataset>`


## Architecture
![Eadro](https://user-images.githubusercontent.com/49298462/217256928-f0d61857-678b-4456-a024-359326a2c45d.png)

## Folder Structure
```
.
├── README.md
├── codes                                             
│   ├── base.py                                         traing and test
│   ├── main.py                                         lanuch the framework
│   ├── model.py                                        the main body (model) of the work
│   ├── preprocess                                      data preprocess                
│   │   ├── align.py                                    align different data sources according to the time
│   │   ├── single_process.py                           handle each data source individually
│   │   └── util.py
│   └── utils.py
├── requirements.txt
└── structure.txt
```

## UI
The final visualized page should be like:
<img width="1919" alt="截屏2023-02-07 下午9 28 22" src="https://user-images.githubusercontent.com/49298462/217257747-e53afafe-ea3f-4024-8760-34d0963a863d.png">

## Concact us
🍺 Feel free to leave messages in "Issues"! 
