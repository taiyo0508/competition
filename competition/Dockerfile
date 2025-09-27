# ベースとなるPythonの公式イメージを指定
FROM python:3.10-slim

# ----------------------------------------------------
# 必要なシステムパッケージをインストールするコマンドを追加
RUN apt-get update && apt-get install -y --no-install-recommends \
    git
# ----------------------------------------------------

# 作業ディレクトリを作成し、移動
WORKDIR /work

# 必要なライブラリリストをコンテナにコピー
COPY requirements.txt .

# requirements.txt を使ってライブラリをインストール
RUN pip install --no-cache-dir -r requirements.txt

# コンテナの8888番ポートを開放（Jupyter用）
EXPOSE 8888

# コンテナ起動時にJupyter Labを起動するコマンド
CMD ["jupyter", "lab", "--ip=0.0.0.0", "--allow-root", "--no-browser", "--NotebookApp.token=''"]