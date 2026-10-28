# 第 06 课：多个输入张量与交叉熵损失

本文件夹只包含本说明和三个作业 Notebook，下载整个文件夹即可使用。

按顺序完成三个 Notebook：

1. `01_multiple_x_y.ipynb`：先观察同一个预测函数接收两个标量输入，再把同一个样本的两个值打包成一个 shape 为 `(2,)` 的 x，比较预测、损失与 shape。本题不要求补写训练循环。
2. `02_train_multiple_inputs.ipynb`：使用 x1、x2 两个输入张量和多个样本，把多输入预测接入上周的训练模板，补全参数、损失、梯度与更新。
3. `03_cross_entropy.ipynb`：通过“是否有行人”的两个预测概率，练习调用 `F.cross_entropy`，并观察预测正确、错误以及概率为 0 或 1 时的具体损失。本题不需要下载数据。

注意：第三份作业中，一个样本的 one-hot 标签和预测概率都是 `(2,)`，表示两个类别。调用交叉熵时，将真实标签转成整数类别编号，并传入原始分数；本题另演示如何把指定概率转换成等价分数。

## 环境与打开方式

沿用上周的课程环境。在终端中运行（不要写进 Notebook 单元格）：

```bash
conda activate cv_class
python -m notebook
```

本次使用 `cv_class` 环境；如果自己的课程环境叫 `torch-class` 或 `cv-learning`，且已安装所需包，也可以激活该环境。打开 Notebook 后选择对应环境的 Python 内核。三份作业只需要 PyTorch，不需要 torchvision。如果尚未安装，在已激活的课程环境中运行 `python -m pip install torch notebook ipykernel`；已有安装可跳过。

若使用 PyTorch 2.2.2 且遇到 NumPy 2 兼容性错误，在已激活的环境中运行 `python -m pip install "numpy<2"`，然后重启 Notebook 内核。

在本文件夹启动 Notebook，三份必做作业均使用 CPU，不需要图片、辅助文件或数据下载。

## 提交

保留题目、补全代码、填写文字观察。第二份的 NotImplementedError 是待完成提示，补完后删除。完成后重启内核并运行全部单元格，保存代码、输出和文字回答，按上周流程提交到自己的 GitHub 仓库。保存并提交修改后的三个 Notebook；保留 README.md，不提交本地环境或缓存文件。第三份示例输出中的 `inf` 是概率为 0 时的预期结果。
