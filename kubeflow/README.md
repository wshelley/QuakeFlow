## QuakeFlow Demo Install


## Pre-Setup Stages

```
wget -O Miniforge3.sh "https://github.com/conda-forge/miniforge/releases/latest/download/Miniforge3-$(uname)-$(uname -m).sh"
bash Miniforge3.sh -b -p "${HOME}/miniforge3/"
export PATH="~/miniforge3/condabin:~/miniforge3/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin"
mamba init
bash
conda info
```

```
git clone https://github.com/wshelley/QuakeFlow
cd QuakeFlow
git checkout bgs-data
git clone https://github.com/wayneweiqiang/PhaseNet.git
git clone https://github.com/wayneweiqiang/GaMMA.git

cd kubeflow
mamba create -n quakeflow -y
source activate quakeflow
mamba env list
mamba env update -f=env.yml

python -m ipykernel install --user --name=quakeflow-kernel
```

## Usage:

Open workflow-simple.ipynb

Change the kernel (top right corner - currently Python3), to quakeflow-kernel. It sometimes take a coupel of mins to appear.

Choose "run_local" True or False.

Enter Kubeflow creds at bottom if running local = false.

When running locally, it currently fails at HypoDD stage. This works fine when running on KFP backend ("run_local=False")

