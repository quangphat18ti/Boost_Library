# Thư viện Boost và cách cài đặt

## Boost là gì?

- Boost là một thư viện mở rộng của C++.
- Thư viện Boost nhằm mục đích trở nên hữu ích rộng rãi và có thể sử dụng được trên nhiều ứng dụng. Ví dụ, chúng rất hữu ích để xử lý các số lớn có phạm vi vượt quá kiểu dữ liệu double long, long long (264) trong C++.
- Thư viện Boost cũng cung cấp các cấu trúc dữ liệu và thuật toán tiên tiến, các cấu trúc dữ liệu này có thể được sử dụng để xây dựng các ứng dụng phức tạp.

## Cài đặt thư viện Boost

### Cài đặt và sử dụng nhanh với Visual Studio

- Bước 1: [Vào link này](https://vcpkg.io/en/getting-started.html) để cài đặt vcpkg.
- Bước 2: Vào thư mục C:\src\vcpkg (Hoặc 1 thư mục bạn muốn)
- Bước 3: Clone the vcpkg repo (
  `git clone https://github.com/Microsoft/vcpkg.git`)
- Bước 4: Mở cmd tại thư mục vcpkg
- Bước 5: Chạy lệnh (`.\vcpkg\bootstrap-vcpkg.bat`)
- Bước 6: Chạy lệnh (`.\vcpkg\vcpkg integrate install`)
- Bước 7: Mở VS ra và code thôi.

### Tải và cài đặt bài bản

- Bước 1: [Vào link này](https://www.boost.org/doc/libs/1_62_0/more/getting_started/unix-variants.html#errors-and-warnings) để tải bản boost mới nhất.

- Bước 2: Đọc hướng dẫn sử dụng bên dưới và cách cài đặt.

- Lưu ý: [Có thể sử dụng Respo Git của tui để tránh phải làm lại nhiều.](https://github.com/quangphat18ti/Boost-Libraries)

## Tổng quan về Boost

### Cách sử dụng thư viện

**(Nếu sử dụng trong Visual Studio thì không cần phải làm bước này)**

- Cài đặt thư viện Boost vào trong Project.
- Khi build file thì phải dẫn link thư viện Boost trong câu lệnh compile.  
   ` g++ -I path/to/boostLibrary   
main.cpp -o main 
path/to/boostLibrary/lib/libUse`

- Trong đó:
  - path/to/boostLibrary là đường dẫn đến thư viện Boost.
  - libUse là thư viện cần sử dụng (Sẽ được trình bày bên dưới).

### Các thư viện Boost: Thư viện trong Boost được chia làm 2 loại

1. **Thư viện Header-Only**: Thư viện này chỉ cần include vào là có thể sử dụng được. (Các thư viện này được đặt trong thư mục boost)
2. Thư viện không phải Header-Only: Thư viện này cần phải được build trước khi sử dụng. (**Các thư viện này được đặt trong thư mục lib**)
   - Để tìm hiểu thêm về các thư viện này thì có thể vào [link này](https://www.boost.org/doc/libs/1_62_0/more/getting_started/unix-variants.html#build-a-boost-library)

### **Lưu ý về cách sử dụng thư viện loại 2**

1. Trong file .cpp ta vẫn include file .hpp như bình thường.
2. Tuy nhiên khi compile thì phải dẫn đường dẫn đến thư viện đã Compile Boost trong câu lệnh compile.
   - Các thư viện thường có đuôi là **.a** hoặc **.so** và đặt trong folder **/lib** của thư viện Boost.
   - Tuy nhiên, ta cần xác định đúng file thư viện cần sử dụng.
     - Ví dụ: **libboost_serialization-mgw63-mt-1_62.a** là thư viện **serialization** của Boost.

Ví dụ: `g++ -I . main.cpp -o main .\lib\libboost_serialization-mgw63-mt-1_62.a`

Là câu lệnh dùng để Serialize Object.