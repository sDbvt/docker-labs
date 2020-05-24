# Cài đặt

## Hướng dẫn cài đặt Docker trên Ubuntu 18.04

Mọi thao tác cài đặt đều dùng quyền cao nhất (super user). Dùng lệnh
```
sudo -s
```

Để xóa phiên bản cũ hoặc docker đã cài lỗi trước đó
```
apt-get remove docker docker-engine docker.io containerd runc
```

Cập nhật
```
apt-get update
```

Cài một vài thứ chứng chỉ yêu cầu cần thiết, có trình tải curl
```    
apt-get install \
    apt-transport-https \
    ca-certificates \
    curl \
    gnupg-agent \
    software-properties-common
```

Chứng thực SSL
```
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
```

Thêm repo của Docker vào máy
```
add-apt-repository \
   "deb [arch=amd64] https://download.docker.com/linux/ubuntu \
   $(lsb_release -cs) \
   stable"
```

Cập nhật lần nữa
```
apt-get update
```

Bước cài docker ở đây
```
apt-get install docker-ce docker-ce-cli containerd.io
```

Kiểm tra thử docker bằng hello-world
```
docker run hello-world
```

Để dùng docker trên user, bạn phải thêm lệnh này vào
```
sudo usermod -aG docker your-user
```

> Lưu ý sau khi thêm, log out hoặc reboot lại máy

Xóa docker khỏi máy
```
sudo apt-get purge docker-ce docker-ce-cli containerd.io
```

Cho chắc thì xóa luôn thư mục
```
sudo rm -rf /var/lib/dockers
```

*Tham khảo*: [tại đây](https://docs.docker.com/engine/install/ubuntu/)