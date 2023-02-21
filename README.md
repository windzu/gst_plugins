# gst_plugins
rebuild some useful gstreamer plugin 

## gst-nvv4l2camera

- plugin: nvv4l2camerasrc
- description: 用于Jetson设备的摄像头采集插件，采用0拷贝方式，性能较好
- 缺点：只支持UYVY格式的输入，无法采集YUYV格式的数据
- 修改：修改了源码，使其同时支持UYVY、YUYV格式的输入

### Usage

```bash
# 覆盖原有的插件
make
make install

# 自行链接
## 注意备份原有的插件,地址为/usr/lib/aarch64-linux-gnu/gstreamer-1.0/libgstnvv4l2camerasrc.so

make
```
### 注意事项
- 原插件的源码中，缺少来自DeepStream SDK的头文件，需要自行添加(本工程已经添加)


## gst-nvvidconv

- plugin: nvvidconv
- description: 用于Jetson设备的视频格式转换插件，采用GPU加速，性能较好
- 缺点：不支持RGB格式的输出，不方便OpenCV后续的处理
- 修改：修改了源码，使其支持RGB格式的输出

### Usage

```bash
```
### 注意事项
