# Bài thực hành 3: Phân tích và giải quyết tình huống khách hàng khiếu nại

## 1. Hiểu đề

Khách mua laptop 10 ngày, máy nóng, quạt kêu to, pin dùng khoảng 2 tiếng. Cửa hàng đã vệ sinh máy nhưng sau 2 ngày lỗi vẫn còn. Khách muốn đổi máy hoặc hoàn tiền.

Mình cần viết **một prompt** bắt AI dùng CoT để: tìm vấn đề, đánh giá mức nghiêm trọng, nêu thông tin còn thiếu, đề xuất 2 phương án, soạn thư phản hồi. AI **không được tự bịa chính sách đổi trả**.

## 2. Prompt hoàn chỉnh

```
Bạn là chuyên viên chăm sóc khách hàng của một cửa hàng bán laptop.
Dưới đây là khiếu nại của khách hàng:
"Tôi mua laptop cách đây 10 ngày. Máy thường xuyên bị nóng, quạt kêu to và pin
chỉ sử dụng được khoảng 2 tiếng. Tôi đã mang đến cửa hàng kiểm tra nhưng nhân
viên chỉ vệ sinh máy và trả lại. Sau 2 ngày, tình trạng vẫn tiếp diễn.
Tôi muốn đổi máy hoặc hoàn tiền."

Hãy suy nghĩ và phân tích từng bước một theo đúng thứ tự sau, không nhảy cóc:

Bước 1 - Dữ kiện: liệt kê các thông tin khách đã nêu rõ trong khiếu nại.
Bước 2 - Vấn đề: xác định các vấn đề khách đang gặp phải (kỹ thuật và dịch vụ).
Bước 3 - Mức độ: phân tích mức độ nghiêm trọng của từng vấn đề (thấp, trung bình,
         cao) và giải thích lý do dựa trên dữ kiện ở Bước 1.
Bước 4 - Thông tin còn thiếu: liệt kê các thông tin cần xác minh trước khi kết luận.
Bước 5 - Hai phương án: đề xuất 2 phương án giải quyết phù hợp, mỗi phương án
         nêu ưu điểm và hạn chế.
Bước 6 - Phản hồi: soạn thư phản hồi chuyên nghiệp gửi khách hàng.

Quy tắc bắt buộc:
- Tuyệt đối KHÔNG tự giả định chính sách đổi trả, bảo hành của cửa hàng. Nếu cần
  dùng chính sách, ghi rõ "cần đối chiếu chính sách của cửa hàng".
- Luôn phân biệt rõ 3 loại: [DỮ KIỆN] khách đã nêu, [GIẢ THUYẾT] suy đoán có thể
  đúng, [CHƯA XÁC ĐỊNH] chưa đủ thông tin.
- Không đưa ra kết luận thiếu căn cứ (ví dụ không khẳng định nguyên nhân hỏng
  hóc khi chưa kiểm tra).
- Thư phản hồi không hứa đổi máy hoặc hoàn tiền khi chưa xác minh.
```

## 3. Kết quả mong đợi (để đối chiếu khi chạy thử)

**Bước 1 - Dữ kiện:** mua cách đây 10 ngày; máy nóng thường xuyên; quạt kêu to; pin khoảng 2 tiếng; đã mang đến cửa hàng, nhân viên chỉ vệ sinh máy; sau 2 ngày lỗi vẫn còn; khách muốn đổi máy hoặc hoàn tiền.

**Bước 2 - Vấn đề:**
1. Máy nóng (kỹ thuật).
2. Quạt kêu to (kỹ thuật).
3. Pin dùng khoảng 2 tiếng (kỹ thuật).
4. Lần xử lý đầu (vệ sinh máy) chưa khắc phục được lỗi (dịch vụ).

**Bước 3 - Mức độ:**

| Vấn đề | Mức độ | Lý do (dựa trên dữ kiện) |
| --- | --- | --- |
| Máy nóng, quạt kêu to | Cao | Xảy ra thường xuyên, đã xử lý một lần mà không hết |
| Pin khoảng 2 tiếng | Trung bình | Cần so với thông số của máy mới biết có bất thường không |
| Xử lý lần đầu chưa hiệu quả | Cao | Khách đã quay lại cửa hàng, có thể mất niềm tin |

**Bước 4 - Thông tin còn thiếu (cần xác minh):**
- Tên máy, cấu hình và thời lượng pin theo thông số hãng.
- Máy nóng khi làm việc gì (nhẹ hay nặng), mức nhiệt cụ thể.
- Tình trạng máy: có rơi, vào nước hay tự cài đặt thêm không.
- Hóa đơn, ngày mua, phiếu tiếp nhận lần sửa đầu (nhân viên đã làm gì).
- Chính sách đổi trả và bảo hành của cửa hàng cho trường hợp này.

**Bước 5 - Hai phương án:**

| | Phương án 1: Kiểm tra kỹ thuật chuyên sâu, sửa hoặc thay linh kiện | Phương án 2: Đổi máy hoặc hoàn tiền nếu đủ điều kiện |
| --- | --- | --- |
| Ưu điểm | Tìm đúng nguyên nhân, khách giữ máy | Đáp ứng đúng mong muốn của khách |
| Hạn chế | Khách đã chờ lâu, có thể chưa hài lòng; chưa chắc hết lỗi | Chỉ làm được khi chính sách cho phép và lỗi được xác nhận; tốn chi phí cho cửa hàng |

**Bước 6 - Phản hồi mẫu:** thư xin lỗi vì khách phải quay lại, nhắc lại 3 lỗi, nói cửa hàng sẽ kiểm tra chuyên sâu, xin các thông tin ở Bước 4 và hóa đơn, hẹn thời gian phản hồi, nêu sẽ đối chiếu chính sách để tư vấn đổi máy hoặc hoàn tiền, **không hứa trước**.

## 4. Kết quả chạy thử

*(Bạn tự chạy prompt trên AI, dán báo cáo từng bước, danh sách thông tin cần xác minh, 2 phương án và thư phản hồi vào đây.)*

Mô hình dùng: *(điền)*

| Tiêu chí kiểm tra | Kết quả thật |
| --- | --- |
| AI có phân tích đủ 6 bước theo thứ tự? | *(điền)* |
| Có tự bịa chính sách đổi trả không? | *(điền)* |
| Có phân biệt dữ kiện, giả thuyết, chưa xác định? | *(điền)* |
| Thư phản hồi có hứa đổi máy hoặc hoàn tiền không? | *(điền)* |

## 5. Nhận xét

- CoT giúp AI đi từng bước nên không kết luận vội và dễ kiểm tra.
- Luật "không tự giả định chính sách" và nhãn [DỮ KIỆN], [GIẢ THUYẾT], [CHƯA XÁC ĐỊNH] giúp tránh AI bịa.
