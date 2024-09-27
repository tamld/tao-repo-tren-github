<h1 align="center">📦 Hướng Dẫn Tạo Repository trên GitHub</h1>

<p align="center">
  <img src="https://img.shields.io/badge/status-active-brightgreen" alt="Status">
  <img src="https://img.shields.io/badge/license-MIT-blue" alt="License">
</p>

## 1. Giới Thiệu

Bài viết này sẽ hướng dẫn bạn cách sử dụng GitHub CLI (gh CLI) để tạo và quản lý repository trên GitHub. Sau khi hoàn tất, bạn sẽ có thể:
- Đăng nhập vào GitHub bằng gh CLI
- Tạo một repository mới trên GitHub
- Đẩy mã nguồn từ máy tính lên GitHub
- Sử dụng VSCode để tạo nội dung cho repository

## 2. Mục Lục

1. [Giới Thiệu](#1-giới-thiệu)
2. [Mục Lục](#2-mục-lục)
3. [Cài đặt và Đăng nhập GitHub CLI](#3-cài-đặt-và-đăng-nhập-github-cli)
   - [3.1. Trên Windows](#31-trên-windows)
   - [3.2. Trên Linux hoặc macOS](#32-trên-linux-hoặc-macos)
4. [Tạo Repository và Đẩy Nội Dung Lên GitHub](#4-tạo-repository-và-đẩy-nội-dung-lên-github)
5. [Đóng Góp và Phát Triển](#5-đóng-góp-và-phát-triển)
6. [Giải Thích Markdown và Tổng Kết](#6-giải-thích-markdown-và-tổng-kết)

## 3. Cài đặt và Đăng nhập GitHub CLI

### 3.1 Trên Windows

1. Cài đặt GitHub CLI từ [GitHub CLI Releases](https://github.com/cli/cli/releases).
2. Mở PowerShell hoặc Command Prompt và chạy lệnh: `gh auth login`
   - Chọn `GitHub.com`.
   - Chọn `HTTPS`.
   - Chọn trình duyệt để tiếp tục đăng nhập.
   - Làm theo hướng dẫn trên trình duyệt để hoàn tất đăng nhập.

### 3.2 Trên Linux hoặc macOS

Link tải về và hướng dẫn cài đặt chi tiết [GitHub CLI](https://github.com/cli/cli#installation).

- Mở Terminal và chạy lệnh: `gh auth login`
  - Chọn `GitHub.com`.
  - Chọn `HTTPS`.
  - Chọn trình duyệt để tiếp tục đăng nhập.
  - Hoàn tất quá trình đăng nhập trên trình duyệt.

## 4. Tạo Repository và Đẩy Nội Dung Lên GitHub

### 4.1 Tạo thư mục mới chứa repo
   ```bash
   mkdir tao-repo-tren-github & cd tao-repo-tren-github
   ```
### 4.2 Khởi tạo Git repository
   ```bash
   git init --initial-branch=main
   ```
### 4.3 Tạo nội dung file `README.md`
   ```bash
   echo "# Tao Repo Trên GitHub" > README.md
   echo "Hướng dẫn sử dụng GitHub CLI để tạo và quản lý repository trên GitHub." >> README.md
   ```
> [!NOTE]
> - Việc chỉnh sửa hoàn toàn có thể kết hợp bằng vscode GUI hoặc vscode terminal đều được. 
> - Trong bài viết này, chúng ta sẽ thử dùng cli để tạo ra các nội dung ban đầu. Nếu có thay đổi, làm từ bước [4.6. Đẩy thay đổi lên GitHub](#46-đẩy-thay-đổi-lên-github) để cập nhật nội dung mới.
> - Ngôn ngữ Markdown sẽ được dùng để format nội dung file README.md.
> - Bạn có thể xem nội dung đầy đủ file README.md này bằng file README.raw khi với ngôn ngữ Markdown khi chưa được github convert.

### 4.4 Sử dụng gh CLI để tạo repository mới trên GitHub
    ```bash
    gh repo create tao-repo-tren-github --public
    ```

### 4.5 Thêm remote repository
    ```bash
    git remote add origin https://github.com/<tên-user-github-của-bạn>/tao-repo-tren-github.git
    ```
### 4.6 Đẩy thay đổi lên GitHub
    ```bash
    git add .
    git commit -m 'Initial commit'
    git push -u origin main
    ```
### 4.7 Thêm mô tả và các chủ đề cho repository:
   ```bash
   gh repo edit --description "Hướng dẫn sử dụng GitHub CLI để tạo và quản lý repository trên GitHub"
   gh repo edit --add-topic github-cli --add-topic repository-management --add-topic markdown
   ```
> [!NOTE]   
> - Lệnh `edit --description`này mô tả (description) của repository. Mô tả này giúp người khác hiểu rõ hơn về mục đích và nội dung của repository
> - Lệnh `edit --add-topic` gán các chủ đề cho repository. Các chủ đề này giúp phân loại và tạo ra các chủ đề liên quan cho repository của bạn trên GitHub, giúp người dùng dễ dàng tìm kiếm và khám phá các dự án có liên quan

## 5. Đóng Góp và Phát Triển

Chúng tôi chào đón mọi đóng góp dưới dạng báo lỗi, đề xuất hoặc thảo luận trong repository.

---

## 6. Giải Thích Markdown và Tổng Kết

### Giải Thích Markdown

Markdown là ngôn ngữ đánh dấu nhẹ giúp định dạng văn bản dễ dàng bằng cách sử dụng ký tự đơn giản. Một số tính năng chính được sử dụng trong tài liệu này bao gồm:
- **Tiêu đề (Heading):** Sử dụng ký hiệu `#` để tạo các cấp độ tiêu đề khác nhau.
- **Danh sách:** Sử dụng dấu `-` hoặc số thứ tự để tạo danh sách không thứ tự và có thứ tự.
- **Liên kết:** Tạo liên kết bằng cách đặt văn bản liên kết trong ngoặc vuông `[ ]` và địa chỉ URL trong ngoặc đơn `( )`.
- **Đánh dấu mã lệnh:** Sử dụng dấu ` để đánh dấu mã lệnh trong dòng.

Để tìm hiểu thêm về Markdown, bạn có thể tham khảo [Markdown Guide](https://www.markdownguide.org/).

### Tổng Kết

Bài viết này đã hướng dẫn bạn cách sử dụng GitHub CLI để quản lý repository trên GitHub, từ cài đặt và đăng nhập đến tạo repository và đẩy mã nguồn. Bạn cũng đã làm quen với cách sử dụng Markdown để định dạng tài liệu. Với những kiến thức này, bạn đã sẵn sàng phát triển và quản lý repository của mình trên GitHub một cách hiệu quả.

✨ **Hãy bình chọn ⭐️ nếu bạn thấy dự án này hữu ích!**
