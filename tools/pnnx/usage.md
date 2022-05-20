


## build and usage
ref: https://github.com/pnnx/pnnx#build-from-source

i use my virtual env python lib and set the pnnx CMakeList.txt variable Torch_INSTALL_DIR, but not found torchvision.
or  download the libTorch from https://download.pytorch.org/libtorch/cu102/libtorch-shared-with-deps-1.11.0%2Bcu102.zip
set(Torch_INSTALL_DIR "/opt/conda/envs/trainEnvs/lib/python3.8/site-packages/torch" CACHE STRING "")

```bash
mkdir ncnn/tools/pnnx/build
cd ncnn/tools/pnnx/build
cmake -DCMAKE_INSTALL_PREFIX=install -DTorch_INSTALL_DIR=<your libtorch dir> ..
cmake -DCMAKE_INSTALL_PREFIX=install -DTorch_INSTALL_DIR=/opt/conda/envs/trainEnvs/lib/python3.8/site-packages/torch ..
cmake -DCMAKE_INSTALL_PREFIX=install -DTorch_INSTALL_DIR=/data/data1/yzh/projects/ncnnlib/libtorch ..
cmake --build . --config Release -j 2
cmake --build . --config Release --target install

```
usage:
export LD_LIBRARY_PATH=$LD_LIBRARY_PATH:/opt/conda/envs/trainEnvs/lib/python3.8/site-packages/torch/lib
./install/bin/pnnx
