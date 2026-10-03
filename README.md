# Web quản lý lớp 12A6

Bản sao giao diện và chức năng từ dự án web-phhs-lop12a5, sử dụng URL Google Apps Script đã có trong dự án web-phhs-lop12A6.

## Các trang
- `index.html`: trang quản lý lớp và cổng phụ huynh (`?phhs=1`).
- `phhs/index.html`: đường dẫn tra cứu phụ huynh.
- `btvn.html`: bài tập về nhà; `?admin=1` dành cho giáo viên.
- `saas.html`: công cụ thiết lập bảng tính được giữ từ dự án nguồn.

## Đưa lên GitHub Pages
Đưa các tệp ở thư mục gốc này vào repository thanhngthien84-lab/web-phhs-lop12a6. Trang chủ phải mang tên `index.html`. Trong Settings → Pages, chọn nhánh main và thư mục / (root).

## Backend và dữ liệu lớp
URL Apps Script trong index.html và btvn.html là URL từ repository 12A6. Chưa xác minh URL này đang kết nối bảng tính nào. Trước khi sử dụng dữ liệu thật, kiểm tra nó kết nối Google Sheet riêng của 12A6.

Nếu backend 12A6 chưa đủ chức năng, thêm Code.gs và HomeworkPublisher.gs vào Apps Script gắn với Google Sheet 12A6, thiết lập Script Property ADMIN_SYNC_KEY, rồi cập nhật bản triển khai Web app. Nếu tạo URL triển khai mới, sửa URL ở cả index.html và btvn.html. Code.gs đã có nhánh xử lý hw-, không thêm nhánh trùng.

Tên lớp mặc định là LỚP 12A6; tên lớp được lưu trong Google Sheet sẽ được ưu tiên. Dùng Cài đặt để lưu tên lớp chính xác. Danh sách học sinh và thông tin giáo viên cần nhập từ dữ liệu riêng của 12A6.

Dữ liệu lưu trình duyệt, mã tra cứu và phiên đăng bài tập được đặt khóa riêng cho 12A6.

## Kiểm tra
Chạy `node test-homework-publisher.cjs`. Bộ kiểm tra dùng dữ liệu giả lập, không ghi vào Google Sheet thật.

Đăng nhập các vai trò quản lý sử dụng mã ADMIN_SYNC_KEY được kiểm tra qua Apps Script; không còn mật khẩu cố định trong HTML. Chưa có mã đăng nhập riêng cho từng vai trò.
