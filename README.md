# esi-profile

## Kernel info
```
CentOS Stream release 8
4.18.0-553.6.1.el8.x86_64 #1 SMP Thu May 30 04:13:58 UTC 2024 x86_64 x86_64 x86_64 GNU/Linux
```

### Setup 
```
sudo dnf install https://www.elrepo.org/elrepo-release-8.el8.elrepo.noarch.rpm
sudo dnf install --enablerepo=elrepo-kerne kernel-devel-$(uname -r) kernel-headers-$(uname -r)
sudo dnf -y install kernel-devel kernel-headers

sudo dnf install https://dl.fedoraproject.org/pub/epel/epel-release-latest-8.noarch.rpm
sudo dnf --enablerepo=epel -y install kernel-devel-$(uname -r) kernel-headers-$(uname -r)

wget https://developer.download.nvidia.com/compute/cuda/12.1.0/local_installers/cuda_12.1.0_530.30.02_linux.run
sudo sh cuda_12.1.0_530.30.02_linux.run

wget https://github.com/NVIDIA/cuda-samples/archive/refs/tags/v12.1.tar.gz
sudo yum install devtoolset-8-gcc
sudo dnf groupinstall "Development Tools"

sudo nvidia-smi -pm 1

wget https://developer.download.nvidia.com/compute/cudnn/redist/cudnn/linux-x86_64/cudnn-linux-x86_64-9.4.0.58_cuda12-archive.tar.xz
sudo cp include/cudnn.h /usr/local/cuda/include
sudo cp lib64/libcudnn* /usr/local/cuda/lib64

sudo yum install wget openssl-devel bzip2-devel libffi-devel xz-devel -y
sudo yum install gcc yum-utils zlib-devel python-tools cmake git pkgconfig -y --skip-broken
```