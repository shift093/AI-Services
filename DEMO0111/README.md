# github clone 

## Task1: LeaderGPU
```
git clone https://github.com/reedwm/benchmarks
cd benchmarks
git checkout num_steps_issue_1.10
```

### gpu:1 batch:32
```
python tf_cnn_benchmarks.py --num_gpus=1 --batch_size=32 --model=resnet50 --variable_update=parameter_server
```

### gpu:2 batch:128
```
python tf_cnn_benchmarks.py --num_gpus=2 --batch_size=128 --model=resnet50 --variable_update=parameter_server
```

## Task2: Tensorflow official
```
git clone https://github.com/uber/horovod
cd horovod/examples/
```

try 
```
python tensorflow_synthetic_benchmark.py
```

* NOTE: hvd.Compression.fp16 not work in this source code, just skip!

### run w/ mpi
```
mpirun -np 8 -H localhost:8 python tensorflow_synthetic_benchmark.py
```