### setup
conda create --name simfin-env
source activate simfin-env
pip install -r requirements.txt

####  have to use new version of pandas, my base env's pandas is old version, doesn't work

source activate simfin-env
jupyter notebook

####  
source deactivate
conda deactivate

#### Error:
#####  A problem: Could not load dynamic library 'libcudart.so.11.0'
* https://github.com/tensorflow/tensorflow/issues/45930
* solution:
conda install cudatoolkit
##### get the path to libcudart.so.11.0
sudo find / -name 'libcudart.so.11.0'
#####  add this path to LD_LIBRARY_PATH in .bashrc as in previous posts
export LD_LIBRARY_PATH=$LD_LIBRARY_PATH:/home/upsman/anaconda3/envs/simfin-env/lib
#####  then:
source ~/.bashrc




#### Error:
failed call to cuInit: CUDA_ERROR_UNKNOWN: unknown error

* solution:
sudo apt-get install nvidia-modprobe  

https://victorwyee.com/engineering/failed-call-to-cuinit-cuda-error-unknown/


#### Error:
AttributeError: partially initialized module 'pandas' has no attribute 'core' (most likely due to a circular import)
* solution:
conda deactivate
conda activate simfin-env
jupyter notebook








#####  output of sudo find / -name 'libcudart.so*'
/home/upsman/anaconda3/envs/simfin-env/lib/libcudart.so
/home/upsman/anaconda3/envs/simfin-env/lib/libcudart.so.11.2.152
/home/upsman/anaconda3/envs/simfin-env/lib/libcudart.so.11.0
/home/upsman/anaconda3/lib/libcudart.so.10.2.89
/home/upsman/anaconda3/lib/libcudart.so
/home/upsman/anaconda3/lib/libcudart.so.10.2
/home/upsman/anaconda3/pkgs/cudatoolkit-11.2.2-he111cf0_8/lib/libcudart.so
/home/upsman/anaconda3/pkgs/cudatoolkit-11.2.2-he111cf0_8/lib/libcudart.so.11.2.152
/home/upsman/anaconda3/pkgs/cudatoolkit-11.2.2-he111cf0_8/lib/libcudart.so.11.0
/home/upsman/anaconda3/pkgs/cudatoolkit-10.2.89-hfd86e86_1/lib/libcudart.so.10.2.89
/home/upsman/anaconda3/pkgs/cudatoolkit-10.2.89-hfd86e86_1/lib/libcudart.so
/home/upsman/anaconda3/pkgs/cudatoolkit-10.2.89-hfd86e86_1/lib/libcudart.so.10.2
find: ‘/run/user/1000/doc’: Permission denied
find: ‘/run/user/1000/gvfs’: Permission denied
find: ‘/run/user/121/gvfs’: Permission denied
/usr/share/man/man7/libcudart.so.7
/usr/share/man/man7/libcudart.so.7.gz
/usr/lib/x86_64-linux-gnu/libcudart.so.10.1.243
/usr/lib/x86_64-linux-gnu/libcudart.so
/usr/lib/x86_64-linux-gnu/libcudart.so.10.1
/usr/local/cuda-10.0/lib64/libcudart.so.10.0
/usr/local/cuda-10.0/lib64/libcudart.so
/usr/local/cuda-10.0/lib64/libcudart.so.10.0.130
/usr/local/cuda-10.0/doc/man/man7/libcudart.so.7
