# 실행방법

```
export DATA_DIR=/home/n0/yujin/dataset/wmt14bpe/    # you need to change here
export SOURCE_DIR=/home/n0/yujin/repo/pipedream/    # you need to change here
cd runtime/
python driver.py --name $USER --config_file translation/driver_configs/gnmt_4pipedream.yml --mount_directories $DATA_DIR $SOURCE_DIR
```

현재 [gnmt_4pipedream.yml](./runtime/translation/driver_configs/gnmt_4pipedream.yml) 파일만 서버 스펙에 맞게 수정했으며, 아래 3가지 값을 수정해줘야 함
- log_directory
- data_dir
- without_stashing

위 명령 실행 시 `logs/{DATE}` 경로 아래에 csv 파일이 stage/epoch 별로 떨어지며, 저장되는 내용은 print된 metric이 순서대로 찍히는 것으로 보면 됨
