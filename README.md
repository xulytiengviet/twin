# Nam Ban Digital Twin

WebGIS giao diện tiếng Việt, thiết kế và phát triển bởi **Long Ngo**. Ứng dụng viết mới, lấy cảm hứng từ bố cục ảnh tham chiếu, không sử dụng mã nguồn hoặc tài sản độc quyền của Q9.

## Chạy

Không cần build hoặc API key. Chạy `python3 -m http.server 8080` trong thư mục dự án rồi mở http://localhost:8080. GitHub Actions triển khai nhánh `main` lên GitHub Pages. Nếu repository chưa cho phép Actions tự bật Pages, vào Settings → Pages → Source → GitHub Actions rồi chạy lại workflow.

## Chức năng

- Bản đồ MapLibre GL JS; nền ảnh Esri, OpenStreetMap hoặc nền sáng.
- Bảng lớp có tìm kiếm, bật/tắt và chỉnh độ rõ lớp minh họa.
- Góc nhìn 2D/3D, xoay, zoom, hướng Bắc, toàn màn hình.
- Nhập GeoJSON WGS84 (kinh độ, vĩ độ), tối đa 20 MB; tự phóng đến dữ liệu; đọc thuộc tính và xuất lại GeoJSON. Mỗi lần nhập thay thế lớp nhập trước đó.
- Đo khoảng cách mặt cầu; xuất ảnh bản đồ PNG có nguồn nền và nhãn dữ liệu minh họa.
- Giao diện responsive, điều khiển bàn phím và nhãn truy cập.

## Giới hạn dữ liệu

Phạm vi polygon, 54 khối công trình và điểm Nam Ban là **dữ liệu minh họa/định vị gần đúng**. Không phải ranh hành chính, bản đồ địa chính 1:5.000 hay công trình khảo sát thực. Chế độ 3D là khối công trình giả định trên mặt phẳng; chưa có DEM, IFC, 3D Tiles hoặc kết nối cảm biến. Để triển khai Digital Twin thực cần cung cấp bộ dữ liệu có quyền sử dụng, hệ tọa độ và metadata nguồn.

Thư viện JS/CSS được lưu tại `vendor/` để không phụ thuộc CDN lúc khởi động. Ảnh nền và glyph vẫn cần Internet. Chưa hỗ trợ offline hoàn toàn. Không có analytics, tài khoản, backend hoặc lưu dữ liệu nhập lên máy chủ; tệp GeoJSON xử lý cục bộ trên trình duyệt và mất khi tải lại trang.

## Giấy phép

- Mã ứng dụng: MIT © 2026 **Long Ngo**, xem LICENSE.
- MapLibre GL JS 4.7.1: BSD-3-Clause, xem vendor/MAPLIBRE-LICENSE.txt; giấy phép của phụ thuộc được giữ trong bản phân phối JS.
- Bản đồ nền và dữ liệu của nhà cung cấp không thuộc giấy phép MIT. Giữ attribution trên bản đồ và ảnh xuất. Dịch vụ công cộng có chính sách/hạn mức riêng; khi triển khai quy mô lớn cần chọn nhà cung cấp phù hợp.
