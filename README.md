# AmazonOrderPrediction
# AMAZON ORDER CANCELLATION AND RETURN RISK PREDICTION

## 1. Giới thiệu đề tài

Đề tài **Xây dựng mô hình Machine Learning dự đoán rủi ro hủy và hoàn trả đơn hàng trên nền tảng Amazon** nhằm phân tích dữ liệu bán hàng và xây dựng mô hình dự đoán khả năng đơn hàng bị hủy hoặc hoàn trả.

Dự án sử dụng bộ dữ liệu Amazon Sale Report, áp dụng các thuật toán học máy để phân loại đơn hàng, đánh giá hiệu quả mô hình và xác định mức độ rủi ro của các đơn hàng mới.

## 2. Mục tiêu dự án

- Phân tích và khám phá dữ liệu bán hàng Amazon.
- Tiền xử lý và làm sạch dữ liệu.
- Xây dựng nhãn phân loại đơn hàng bị hủy hoặc hoàn trả.
- Huấn luyện và so sánh các mô hình Machine Learning.
- Đánh giá hiệu quả mô hình bằng các chỉ số phân loại.
- Dự đoán xác suất rủi ro cho 1.000 đơn hàng mới nhất.

## 3. Công nghệ sử dụng

| Công nghệ | Chức năng |
|---|---|
| Python | Ngôn ngữ lập trình |
| Pandas | Xử lý dữ liệu |
| NumPy | Tính toán số học |
| Matplotlib | Trực quan hóa dữ liệu |
| Seaborn | Vẽ biểu đồ thống kê |
| Scikit-learn | Xây dựng và đánh giá mô hình |
| Jupyter Notebook | Môi trường thực hiện dự án |

## 4. Các thuật toán Machine Learning

Dự án sử dụng hai thuật toán chính:

**Decision Tree (Cây quyết định)**
- Xây dựng mô hình phân loại dựa trên các điều kiện và đặc trưng dữ liệu.
- Thực hiện so sánh giữa mô hình mặc định và mô hình cân bằng lớp.

**Random Forest (Rừng ngẫu nhiên)**
- Kết hợp nhiều cây quyết định để đưa ra kết quả phân loại.
- Sử dụng `class_weight='balanced'` để xử lý tình trạng mất cân bằng dữ liệu.
- Được sử dụng để xây dựng mô hình dự đoán cuối cùng.

## 5. Quy trình thực hiện

Dự án gồm 6 giai đoạn:

**Giai đoạn 1: Import thư viện và cấu hình**
- Import các thư viện cần thiết.
- Cấu hình môi trường và hiển thị biểu đồ.

**Giai đoạn 2: Làm sạch dữ liệu và tạo đặc trưng**
- Loại bỏ các đơn hàng chưa có kết quả.
- Tạo nhãn hủy/hoàn trả.
- Trích xuất đặc trưng thời gian, khuyến mãi và khu vực.
- Chọn 11 đặc trưng đầu vào.
- Tách 1.000 đơn hàng mới nhất thành tập dự đoán.

**Giai đoạn 3: Chia dữ liệu và tiền xử lý**
- Chia dữ liệu Train/Validation/Test theo tỷ lệ 70/15/15.
- Xử lý dữ liệu thiếu.
- Mã hóa dữ liệu phân loại bằng One-Hot Encoding.
- Chuẩn hóa dữ liệu số bằng StandardScaler.

**Giai đoạn 4: Huấn luyện và so sánh mô hình**
- Huấn luyện Decision Tree.
- Huấn luyện Random Forest.
- So sánh các cấu hình mặc định và Balanced.
- Thực hiện kiểm định chéo 5-Fold.

**Giai đoạn 5: Trực quan hóa và phân tích**
- Ma trận nhầm lẫn (Confusion Matrix).
- Phân tích Overfitting.
- Biểu đồ mức độ quan trọng của đặc trưng (Feature Importance).

**Giai đoạn 6: Đánh giá và dự đoán**
- Đánh giá mô hình bằng Validation và Test.
- Dự đoán xác suất hủy/hoàn trả.
- Phân loại mức độ rủi ro.
- Xuất kết quả thành file CSV.

## 6. Phân loại mức độ rủi ro

Dựa trên xác suất dự đoán của mô hình:

| Mức độ | Điều kiện | Ý nghĩa |
|---|---|---|
| Rủi ro CAO | >= 70% | Khả năng hủy/hoàn trả cao |
| Rủi ro TRUNG BÌNH | 40% đến dưới 70% | Có mức độ rủi ro trung bình |
| An toàn | Dưới 40% | Có mức độ rủi ro thấp |

## 7. Đánh giá mô hình

Các chỉ số được sử dụng để đánh giá:

- Accuracy: Độ chính xác tổng thể.
- Precision: Độ chính xác của dự đoán lớp hủy/hoàn trả.
- Recall: Khả năng phát hiện đơn hàng hủy/hoàn trả.
- F1-score: Sự cân bằng giữa Precision và Recall.
- ROC-AUC: Khả năng phân biệt giữa hai lớp.

## 8. Kết quả đầu ra

Sau khi chạy Notebook, chương trình tạo ra:

- `bieu_do_bao_cao_btl.png`: Hình ảnh trực quan hóa kết quả.
- `ket_qua_du_doan_tap_member.csv`: Kết quả dự đoán cho 1.000 đơn hàng mới nhất.

File kết quả bao gồm:
- Order ID.
- Date.
- Fulfilment.
- Category.
- Amount.
- Xac_suat_huy (%).
- Phan_loai_rui_ro.

## 9. Cài đặt và chạy chương trình

**Bước 1: Clone Repository**

```bash
git clone https://github.com/YOUR_USERNAME/Amazon-Order-Prediction.git
```

**Bước 2: Cài đặt thư viện**

```bash
pip install numpy pandas matplotlib seaborn scikit-learn jupyter ipykernel
```

**Bước 3: Chuẩn bị dữ liệu**

Đặt file `Amazon Sale Report.csv` cùng thư mục với Notebook `main_model.ipynb`.

Nếu lưu dữ liệu ở vị trí khác, cập nhật đường dẫn CSV trong Notebook.

**Bước 4: Chạy chương trình**

```bash
jupyter notebook
```

Mở file `main_model.ipynb` và chạy lần lượt các ô lệnh từ trên xuống dưới.

## 10. Cấu trúc dự án

```text
Amazon-Order-Prediction/
│
├── main_model.ipynb
├── README.md
├── requirements.txt
│
├── dataset/
│   └── Amazon Sale Report.csv
│
└── outputs/
    ├── bieu_do_bao_cao_btl.png
    └── ket_qua_du_doan_tap_member.csv
```

## 11. Kết luận

Dự án ứng dụng các thuật toán Machine Learning vào bài toán dự đoán rủi ro hủy và hoàn trả đơn hàng trên nền tảng Amazon.

Thông qua việc phân tích dữ liệu, huấn luyện và đánh giá các mô hình Decision Tree và Random Forest, dự án hướng đến việc hỗ trợ nhận diện những đơn hàng có nguy cơ cao, góp phần cải thiện hoạt động quản lý và xử lý đơn hàng.

---

**Project:** Amazon Order Cancellation and Return Risk Prediction  
**Programming Language:** Python  
**Machine Learning:** Decision Tree, Random Forest
