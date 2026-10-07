# 🏎️ Engine Sound MVP

> **⚠️ CẢNH BÁO AN TOÀN: TÀI XẾ CHỈ THAO TÁC KHI XE ĐÃ DỪNG HẲN.**

Ứng dụng web giả lập tiếng động cơ theo thời gian thực dựa trên chuyển động của xe (GPS). Tiếng động cơ tăng giảm theo tốc độ và gia tốc, như một chiếc xe xăng thật, để:

1. **Hỗ trợ hành khách dễ say xe khi ngồi xe điện:** âm thanh giúp não nhận ra chuyển động của xe.
2. **Tăng cảm giác lái cho tài xế:** xe điện êm được "thêm" tiếng động cơ để lái thú vị hơn.

> Đây là sản phẩm thử nghiệm (MVP), **không phải thiết bị y tế** và không cam kết giảm hoặc chữa say xe. Xem mục [Miễn trừ trách nhiệm](#miễn-trừ-trách-nhiệm).

---

## Vì sao âm thanh có thể giúp giảm say xe trên xe điện?

Say xe được cho là xuất phát từ **sự lệch pha giữa các tín hiệu** mà não nhận được từ mắt, tai trong và cơ thể. Khi lên xe xăng, não quen suy ra chuyển động của xe nhờ tiếng máy rồ lên khi tăng tốc, rung động của động cơ và tiếng sang số. Xe điện vận hành rất êm nên những "manh mối" quen thuộc này gần như biến mất.

Một số nghiên cứu gần đây gợi ý rằng bổ sung tín hiệu âm thanh về chuyển động có thể giúp:

- Một nghiên cứu tại Forum Acusticum 2025 thử **tiếng động cơ nhân tạo** trên xe điện và ghi nhận mức say xe giảm đáng kể khi có âm thanh.
- Một nghiên cứu trên đường thực tế (Xie và cộng sự, 2025) cho thấy **tín hiệu âm thanh về chuyển động** có thể giảm say xe khi xe dùng phanh tái sinh mức cao. Tuy nhiên, lợi ích không rõ ràng ở các điều kiện còn lại.
- Một nghiên cứu năm 2020 cho thấy **tín hiệu âm thanh báo trước** (đúng lúc, chính xác) cho kết quả tốt nhất.

**Lưu ý quan trọng:** các nghiên cứu này còn ở giai đoạn sớm, nhiều nghiên cứu có mẫu nhỏ, kết quả chưa thống nhất, và mỗi người phản ứng khác nhau. Âm thanh thiết kế kém hoặc quá lớn còn có thể gây khó chịu. App này **chưa được kiểm chứng lâm sàng**; nó chỉ áp dụng ý tưởng chung "trả lại tín hiệu âm thanh về chuyển động" ở dạng đơn giản.

---

## Ứng dụng làm gì?

- Đọc **tốc độ từ GPS** của điện thoại, suy ra gia tốc.
- Tạo **tiếng động cơ giả lập** theo tốc độ, số, vòng tua (RPM) và tải, có cả hộp số ảo, quán tính vòng tua, tiếng hút gió, tiếng rít turbo và tiếng xì xả (tùy hồ sơ).
- Chạy ngay trên **trình duyệt (khuyên dùng Safari trên iPhone)**, không cần cài app.

### Hai chế độ

| Chế độ | Hành vi | Dùng khi |
|---|---|---|
| **GIẢ LẬP TĂNG TỐC** | Chỉ phát tiếng khi xe đang tăng tốc; chạy đều hoặc giảm tốc thì tắt tiếng. | Hỗ trợ cho người thường bị say xe điện, nhấn mạnh các lúc tăng tốc. |
| **GIẢ LẬP TOÀN PHẦN** | Giữ tiếng động cơ liên tục khi xe đang di chuyển (kể cả chạy đều); chỉ tắt khi xe dừng. | Trải nghiệm như xe có động cơ, hợp cảm giác lái. |

### Các hồ sơ âm thanh

Porsche 911 (boxer 6), BMW M3 (thẳng 6), VW Golf GTI (4 xi-lanh tăng áp), Mercedes-AMG V8 và Xe điện (tiếng mô tơ).

> Đây là các hồ sơ **tổng hợp mô phỏng "phong cách"**, không phải bản thu âm chính hãng và không liên kết với các hãng xe nêu trên. Tên hãng chỉ dùng để mô tả kiểu âm thanh.

---

## Cách sử dụng

1. Mở ứng dụng bằng **Safari qua HTTPS** (GPS yêu cầu HTTPS).
2. Chọn chế độ ở trên cùng và chọn loại động cơ.
3. Bấm **📡 Dùng GPS** và cho phép quyền vị trí. Tăng âm lượng và tắt chế độ im lặng nếu cần.
4. Đặt điện thoại cố định, màn hình sáng. Ứng dụng giữ màn hình sáng (nếu Safari hỗ trợ).
5. Muốn thử nhanh khi chưa lái xe, bấm **🎮 Mô phỏng** và dùng nút tăng tốc ảo.

Dòng nhỏ dưới thanh RPM cho biết độ chính xác GPS và trạng thái âm thanh (`running` là tốt).

> **Chỉ thao tác khi xe đã dừng hẳn.** Người lái không được vừa lái vừa chỉnh ứng dụng. Nên để hành khách thao tác nếu xe đang chạy.

---

## Triển khai

Ứng dụng chỉ gồm **một file `index.html`** (HTML, CSS, JavaScript thuần), không cần máy chủ riêng.

- **GitHub Pages:** tải `index.html` lên kho công khai, vào *Settings > Pages*, chọn nhánh `main` và thư mục `/ (root)`.
- **Netlify / Cloudflare Pages:** kéo thả file lên và đặt ở chế độ công khai.
- **Nhúng vào Wix:** dùng *Settings > Custom Code* để tạo iframe có quyền `geolocation` (xem `wix-custom-code.html`). Embed HTML thông thường của Wix không cho GPS chạy bên trong khung nhúng; khi đó dùng nút mở sang tab mới (`wix-embed-html.html`).

---

## Cách hoạt động (tóm tắt kỹ thuật)

```
GPS (~1 Hz) → ước lượng gia tốc → mô hình động cơ (số, RPM, tải) → bộ tổng hợp Web Audio → loa
```

- **Nhận biết tăng tốc:** làm mượt gia tốc từ chênh lệch tốc độ GPS, có ngưỡng và thời gian giữ để tránh nhảy bật tắt.
- **Mô hình động cơ:** RPM suy ra từ tốc độ, tỉ số truyền và hộp số ảo; RPM có quán tính, sang số có khoảng ngắt tiếng.
- **Tổng hợp âm thanh:** nhiều bộ dao động theo tần số nổ (số xi-lanh), qua méo, lọc thông thấp theo RPM và tải, cộng tiếng hút gió, rít turbo, rung nhịp.
- **Công nghệ:** Web Audio API, Geolocation API, Screen Wake Lock API.

---

## Quyền riêng tư

Ứng dụng xử lý vị trí **ngay trên thiết bị** và không gửi dữ liệu vị trí lên máy chủ nào. Nơi bạn lưu trữ trang web (GitHub, Netlify, Wix…) vẫn có thể ghi nhật ký truy cập thông thường theo chính sách riêng của họ.

---

## Hạn chế hiện tại

- **GPS cập nhật khoảng 1 lần/giây**, nên âm thanh có độ trễ khoảng 1 giây và **phản ánh chuyển động chứ chưa báo trước**. Các nghiên cứu cho thấy tín hiệu báo trước hiệu quả hơn.
- Trang web **không chạy ngầm đáng tin cậy** trên iPhone: cần giữ Safari ở nền trước và màn hình sáng. Muốn chạy ngầm thật cần app native (iOS).
- Âm thanh là **tổng hợp**, chưa chân thực bằng mẫu thu thật; có thể hơi gắt ở vòng tua cao.
- GPS yếu trong nhà, hầm hoặc khu nhiều nhà cao tầng.
- Hiệu quả giảm say xe **chưa được kiểm chứng** cho app này và khác nhau giữa từng người.

## Hướng phát triển

- Dùng cảm biến gia tốc (`DeviceMotion`) để phản hồi tức thì và báo trước chuyển động.
- Bản **iOS native** (Swift) chạy nền, dùng `AVAudioEngine` và `CoreLocation`.
- Dùng mẫu âm thanh thu thật có bản quyền rõ ràng, phát theo RPM.
- Khóa các nút điều khiển khi xe đang chạy.
- Thử nghiệm với người dùng thực tế để đánh giá hiệu quả.

---

## Tài liệu tham khảo

- *Mitigating Motion Sickness in Electric Vehicles*, Forum Acusticum 2025: https://dael.euracoustics.org/confs/fa2025/data/articles/000569.pdf
- Xie và cộng sự (2025), *Exploring the Effects of Regenerative Braking and the Auditory Cues for Alleviating Motion Sickness in Electric Vehicles*, International Journal of Human–Computer Interaction: https://personal.hkust-gz.edu.cn/hedengbo/assets/publicationPDFs/Xie-IJHCI_2025a.pdf
- *Knowing What's Coming: Anticipatory Audio Cues Can Mitigate Motion Sickness* (2020) và *Investigative Examination of Motion Sickness Indicators for Electric Vehicles* (2024), được tóm tắt trong: https://simanaitissays.com/2025/07/06/ev-carsickness/
- Tổng quan báo chí: https://techspot.com/news/108757-evs-triggering-wave-motion-sickness-claims-scientists-investigating.html

---

## Miễn trừ trách nhiệm

- Ứng dụng chỉ nhằm **giải trí và hỗ trợ trải nghiệm**, không phải thiết bị hay phương pháp điều trị y tế. Nếu bạn bị say xe nặng hoặc có vấn đề sức khỏe, hãy hỏi ý kiến nhân viên y tế.
- **Tài xế tuyệt đối không thao tác ứng dụng khi xe đang chạy.** Người dùng tự chịu trách nhiệm tuân thủ luật giao thông địa phương.
- Âm thanh động cơ giả lập **không thay thế** các âm thanh cảnh báo an toàn của xe và không dùng để cảnh báo người đi bộ.
- Tên hãng xe chỉ để mô tả phong cách âm thanh; dự án không liên kết hay được tài trợ bởi các hãng này.

## Giấy phép

Chưa chọn giấy phép. Hãy thêm file `LICENSE` (ví dụ MIT) trước khi công bố rộng rãi.
