# Bài 4: Phân tích & Lựa chọn (Kỹ thuật Prompt lặp và tối ưu - Iterative Prompting)

## Yêu cầu đầu ra:

### 1. Đáp án lựa chọn
**Đáp án: Phương án C**

### 2. Phân tích chi tiết phương án C (Iterative Prompting)
Phương án C thể hiện xuất sắc và đúng chuẩn tư duy "Iterative Prompting" (Quy trình: Đánh giá -> Nhận diện lỗi -> Tinh chỉnh):
*   **Giữ nguyên phiên chat cũ:** Giúp AI duy trì được bộ nhớ ngữ cảnh (context) về đoạn code cũ và yêu cầu thuật toán ban đầu. Nếu mở phiên chat mới, AI sẽ quên mất mục tiêu hiện tại.
*   **Đánh giá & Nhận diện lỗi (Feedback):** Việc phản hồi trực tiếp cho AI bằng cách chỉ rõ "vòng lặp chạy đến n-1 quá chậm đối với số lớn" giúp AI hiểu rõ nguyên nhân tại sao đoạn code trước đó chưa đạt yêu cầu. 
*   **Tinh chỉnh bằng chỉ dẫn bổ sung (Refine):** Đưa ra yêu cầu kỹ thuật cụ thể "sửa vòng lặp chỉ chạy đến căn bậc hai của n để giảm độ phức tạp thuật toán từ O(n) xuống O(sqrt(n))" giúp định hướng AI viết lại một thuật toán tối ưu hơn một cách chính xác thay vì để AI tự đoán mò.
*   Đây chính là bản chất cốt lõi của "Iterative Prompting": Không nên kỳ vọng AI làm đúng hoàn hảo ở lần đầu, mà cần coi AI như một cộng sự để liên tục cấp feedback (phản hồi) và định hướng để tinh chỉnh dần tới kết quả cuối cùng tối ưu nhất.

### 3. Giải thích tại sao hai phương án kia không mang lại hiệu quả thực tế
*   **Phương án A (Bỏ cuộc và tự viết lại):** Phủ nhận hoàn toàn lợi ích của việc sử dụng AI (tư duy Augmented Developer). Nếu gặp khó một chút đã bỏ cuộc thì lập trình viên sẽ đánh mất cơ hội tận dụng công cụ để tăng tốc hiệu suất công việc.
*   **Phương án B (Mở phiên chat mới và lặp lại prompt cũ đổi sang in hoa):** 
    *   Mở phiên chat mới làm mất toàn bộ ngữ cảnh (context window) của vấn đề đang được giải quyết dở dang.
    *   Lặp lại một prompt thô cũ chỉ bằng cách viết hoa toàn bộ chữ không giải quyết được nguyên nhân gốc rễ. Máy móc (AI) không "hiểu" cảm xúc hay sự bực tức của con người. Theo nguyên lý "Garbage in, Garbage out", nếu prompt không chứa thông tin điều chỉnh thuật toán (căn bậc hai), AI vẫn sẽ sinh ra kết quả tương tự hoặc lan man không đúng trọng tâm.
