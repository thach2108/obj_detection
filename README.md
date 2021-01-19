# install cuda and cudnn

# create virtual environment

python -m venv my_env
source my_env/bin/activate
python -m pip install --upgrade pip

# obj_detection

cd models/research
# Compile protos.
protoc object_detection/protos/*.proto --python_out=.

# Install TensorFlow Object Detection API.
cp object_detection/packages/tf2/setup.py .
python -m pip install --use-feature=2020-resolver .