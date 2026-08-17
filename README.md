# 23631191_TranQuocKhanh_CABsystem

# CAB System

# Vấn đề hiện tại là gì
Hiện tại, hệ thống đặt xe của công ty ABC còn tồn tại nhiều hạn chế trong quá trình vận hành. Việc phân công tài xế chủ yếu được thực hiện thủ công, dẫn đến mất nhiều thời gian, dễ xảy ra sai sót và khó đáp ứng khi số lượng khách hàng và tài xế tăng cao. Khách hàng cũng chưa có khả năng theo dõi đầy đủ trạng thái chuyến đi, chẳng hạn như hệ thống đang tìm tài xế, tài xế nào đã nhận chuyến hoặc thời gian dự kiến tài xế đến. Bên cạnh đó, thông tin thanh toán chưa được quản lý tập trung, gây khó khăn trong việc tra cứu, đối soát và xử lý các giao dịch thất bại.

Về phía vận hành, nhân viên gặp khó khăn trong việc theo dõi các chuyến đang diễn ra, quản lý trạng thái tài xế và xử lý các trường hợp chuyến bị lỗi. Hệ thống hiện tại cũng chưa có cơ chế tự động và tối ưu để tìm tài xế phù hợp khi tài xế từ chối hoặc không phản hồi. Ngoài ra, khả năng mở rộng hệ thống còn hạn chế, có nguy cơ ảnh hưởng đến toàn bộ hoạt động khi một thành phần như thanh toán hoặc thông báo gặp sự cố. Doanh nghiệp cũng chưa có đầy đủ cơ chế phân quyền, lưu vết thao tác và báo cáo để phục vụ quản lý và kiểm soát hoạt động.

Bên cạnh các vấn đề trên, một số quy tắc nghiệp vụ quan trọng như cách tính cước, tiêu chí lựa chọn tài xế, thời gian phản hồi, chính sách hủy chuyến, xử lý mất kết nối và thời gian lưu trữ dữ liệu vẫn chưa được thống nhất. Điều này có thể gây khó khăn cho quá trình phát triển và làm phát sinh thay đổi yêu cầu trong quá trình triển khai. Vì vậy, doanh nghiệp cần xây dựng một nền tảng CAB mới có khả năng tự động hóa quy trình đặt và phân công xe, minh bạch trạng thái chuyến, quản lý thanh toán tập trung, hỗ trợ vận hành hiệu quả và có kiến trúc linh hoạt để mở rộng trong tương lai.

## Stakeholder

| Tên Stakeholder | Vai trò trong hệ thống |
|---|---|
| Khách hàng (Customer) | Đăng ký, đăng nhập, đặt xe, theo dõi chuyến đi, thanh toán, xem lịch sử và đánh giá tài xế. |
| Tài xế (Driver) | Quản lý hồ sơ và phương tiện, cập nhật trạng thái hoạt động, nhận/từ chối chuyến, cập nhật trạng thái và vị trí chuyến đi. |
| Nhân viên vận hành (Operation Staff) | Theo dõi các chuyến đang diễn ra, quản lý trạng thái tài xế và xử lý các trường hợp chuyến bị lỗi hoặc bất thường. |
| Quản trị viên (System Admin) | Quản lý tài khoản, người dùng, phân quyền và các cấu hình quản trị của hệ thống. |
| Ban lãnh đạo (Business Owner/Management) | Theo dõi báo cáo, doanh thu, số lượng chuyến và hiệu quả hoạt động để đưa ra quyết định kinh doanh. |
| Bộ phận chăm sóc khách hàng (Customer Support) | Tiếp nhận và xử lý các yêu cầu, khiếu nại liên quan đến khách hàng, chuyến đi và thanh toán. |
| Bộ phận Tài chính/Kế toán | Theo dõi giao dịch, doanh thu và thực hiện đối soát các khoản thanh toán. |
| Bộ phận quản lý đội xe (Fleet Management) | Quản lý thông tin tài xế, phương tiện và tình trạng hoạt động của đội xe. |
| Bộ phận IT/DevOps | Phát triển, triển khai, giám sát, bảo trì và đảm bảo hệ thống hoạt động ổn định. |
| Bộ phận An toàn thông tin (Security/Compliance) | Kiểm soát bảo mật, phân quyền, bảo vệ dữ liệu và theo dõi các hoạt động quan trọng của hệ thống. |
| Nhà cung cấp thanh toán (Payment Provider) | Xử lý các giao dịch thanh toán điện tử và trả kết quả giao dịch cho hệ thống CAB. |
| Nhà cung cấp bản đồ/định vị (Map/GPS Provider) | Cung cấp dữ liệu vị trí, khoảng cách, tuyến đường và hỗ trợ tính thời gian dự kiến đến (ETA). |
| Nhà cung cấp thông báo (Notification Provider) | Gửi thông báo đến khách hàng và tài xế thông qua Push Notification, SMS, Email hoặc các kênh khác. |

## Stakeholder Matrix

Stakeholder Matrix được sử dụng để đánh giá các bên liên quan dựa trên hai tiêu chí chính: **Power (mức độ ảnh hưởng/quyền quyết định)** và **Interest (mức độ quan tâm đến dự án)**. Từ đó xác định chiến lược làm việc phù hợp với từng nhóm stakeholder.

| Stakeholder | Power | Interest | Chiến lược quản lý |
|---|---|---|---|
| Business Owner / Ban lãnh đạo | Cao | Cao | Manage Closely – Tham gia các quyết định quan trọng, phê duyệt phạm vi, mục tiêu, business rules và KPI. |
| Operation Manager / Nhân viên vận hành | Cao | Cao | Manage Closely – Tham gia phân tích quy trình vận hành, điều phối tài xế và xử lý các trường hợp ngoại lệ. |
| Finance / Accounting | Trung bình | Cao | Manage Closely – Xác định yêu cầu về thanh toán, doanh thu, giao dịch và đối soát. |
| Customer | Thấp | Cao | Keep Informed / Engage – Thu thập nhu cầu và phản hồi để đảm bảo trải nghiệm đặt xe tốt. |
| Driver | Trung bình | Cao | Keep Informed / Engage – Tham gia xác định quy trình nhận chuyến, matching, cập nhật trạng thái và vị trí. |
| Customer Support | Trung bình | Cao | Keep Informed / Engage – Xác định nhu cầu tra cứu và xử lý khiếu nại, hỗ trợ khách hàng. |
| Fleet Management | Trung bình | Cao | Keep Informed / Engage – Xác định yêu cầu quản lý tài xế, phương tiện và tình trạng hoạt động. |
| System Admin | Cao | Trung bình | Keep Satisfied – Đảm bảo yêu cầu quản trị, phân quyền và cấu hình hệ thống. |
| IT / DevOps | Cao | Trung bình | Keep Satisfied – Tham gia các vấn đề về kiến trúc, hiệu năng, triển khai, monitoring và vận hành. |
| Security / Compliance | Cao | Trung bình | Keep Satisfied – Kiểm soát authentication, authorization, bảo vệ dữ liệu và audit log. |
| Payment Provider | Trung bình | Trung bình | Keep Satisfied – Đảm bảo tích hợp thanh toán, xử lý giao dịch và nhận kết quả thanh toán ổn định. |
| Map / GPS Provider | Trung bình | Trung bình | Keep Satisfied – Cung cấp dữ liệu vị trí, khoảng cách, tuyến đường và ETA. |
| Notification Provider | Thấp | Trung bình | Monitor – Theo dõi khả năng gửi notification và xử lý retry khi có lỗi. |

## Ma trận các bên liên quan

Ma trận các bên liên quan được phân loại dựa trên hai tiêu chí:

- **Power:** Mức độ quyền lực/ảnh hưởng của stakeholder đối với dự án.
- **Interest:** Mức độ quan tâm của stakeholder đối với hệ thống CAB.

|  | **Interest thấp** | **Interest cao** |
|---|---|---|
| **Power cao** | **KEEP SATISFIED**<br><br>- System Admin<br>- IT / DevOps<br>- Security / Compliance | **MANAGE CLOSELY**<br><br>- Business Owner / Ban lãnh đạo<br>- Operation Manager<br>- Finance / Accounting |
| **Power thấp** | **MONITOR**<br><br>- Notification Provider | **KEEP INFORMED / ENGAGE**<br><br>- Customer<br>- Driver<br>- Customer Support<br>- Fleet Management<br>- Payment Provider<br>- Map / GPS Provider |

### Chiến lược quản lý

| Nhóm | Chiến lược |
|---|---|
| **Manage Closely** | Làm việc thường xuyên, tham gia phân tích, review và phê duyệt các yêu cầu quan trọng. |
| **Keep Satisfied** | Đảm bảo stakeholder được cung cấp đầy đủ thông tin và được tham gia khi có vấn đề liên quan đến phạm vi của họ. |
| **Keep Informed / Engage** | Thường xuyên thu thập nhu cầu, phản hồi và cập nhật thông tin liên quan đến hệ thống. |
| **Monitor** | Theo dõi ở mức phù hợp và chủ động trao đổi khi có thay đổi ảnh hưởng đến stakeholder. |    

## Xác định Business Unit

Business Unit là các đơn vị/bộ phận trong doanh nghiệp tham gia vào quá trình cung cấp, vận hành, quản lý và hỗ trợ dịch vụ CAB.

| Business Unit | Vai trò trong hệ thống |
|---|---|
| **Ban lãnh đạo (Management)** | Xác định mục tiêu kinh doanh, định hướng phát triển sản phẩm, phê duyệt chính sách và theo dõi các chỉ số kinh doanh như doanh thu, số lượng chuyến, tỷ lệ hoàn thành và tỷ lệ hủy. |
| **Bộ phận Vận hành (Operations)** | Điều phối và giám sát hoạt động đặt xe, theo dõi chuyến đang diễn ra, quản lý trạng thái tài xế và xử lý các trường hợp bất thường trong quá trình vận hành. |
| **Bộ phận Quản lý tài xế/Đội xe (Fleet Management)** | Quản lý hồ sơ tài xế, phương tiện, trạng thái hoạt động và hiệu quả làm việc của tài xế. |
| **Bộ phận Chăm sóc khách hàng (Customer Service)** | Tiếp nhận và xử lý yêu cầu hỗ trợ, khiếu nại của khách hàng liên quan đến tài khoản, chuyến đi, tài xế và thanh toán. |
| **Bộ phận Tài chính/Kế toán (Finance & Accounting)** | Quản lý doanh thu, giao dịch thanh toán, đối soát với các nhà cung cấp thanh toán và hỗ trợ xử lý các vấn đề liên quan đến giao dịch. |
| **Bộ phận Công nghệ thông tin (IT)** | Phát triển, duy trì và đảm bảo hệ thống CAB hoạt động ổn định, an toàn và có khả năng mở rộng. |
| **Bộ phận DevOps/Infrastructure** | Quản lý môi trường triển khai, monitoring, logging, deployment và khả năng mở rộng hạ tầng hệ thống. |
| **Bộ phận An toàn thông tin (Security/Compliance)** | Đảm bảo hệ thống tuân thủ các yêu cầu về xác thực, phân quyền, bảo vệ dữ liệu cá nhân, dữ liệu vị trí, dữ liệu giao dịch và audit log. |
| **Khách hàng (Customer)** | Sử dụng dịch vụ CAB để đặt xe, theo dõi chuyến, thanh toán và đánh giá chất lượng dịch vụ. |
| **Tài xế (Driver)** | Cung cấp dịch vụ vận chuyển, nhận chuyến, thực hiện chuyến, cập nhật trạng thái và vị trí trong quá trình phục vụ khách hàng. |

## Phạm vi dự án trong 7 tuần

### 1. Mục tiêu phạm vi

Trong thời gian triển khai 7 tuần, dự án tập trung xây dựng **MVP (Minimum Viable Product)** của CAB System, đáp ứng đầy đủ quy trình đặt xe trực tuyến cơ bản từ khi khách hàng tạo yêu cầu đến khi chuyến xe hoàn thành và thanh toán.

Mục tiêu của MVP là tạo ra một hệ thống có thể vận hành được quy trình:

**Customer → Booking → Driver Matching → Driver Acceptance → Trip → Fare → Payment → Completion**

Các tính năng nâng cao và các yêu cầu chưa có business rule rõ ràng sẽ được xem xét cho các giai đoạn phát triển tiếp theo.

---

### 2. Phạm vi chức năng chính

| Nhóm chức năng | Phạm vi thực hiện trong MVP | Mức độ |
|---|---|---|
| **Authentication** | Đăng ký, đăng nhập, đăng xuất cho Customer và Driver | Must Have |
| **Customer Profile** | Xem và cập nhật thông tin cá nhân | Must Have |
| **Driver Profile** | Xem và cập nhật thông tin tài xế | Must Have |
| **Vehicle Management** | Quản lý thông tin phương tiện của tài xế | Must Have |
| **Driver Availability** | Driver bật/tắt trạng thái sẵn sàng nhận chuyến | Must Have |
| **Booking** | Customer nhập điểm đón, điểm đến và chọn loại xe | Must Have |
| **Driver Matching** | Hệ thống tìm tài xế phù hợp dựa trên trạng thái và khoảng cách cơ bản | Must Have |
| **Driver Acceptance** | Driver nhận thông báo và Accept/Reject chuyến | Must Have |
| **Trip Management** | Quản lý trạng thái chuyến từ nhận chuyến đến hoàn thành | Must Have |
| **Driver Location** | Cập nhật vị trí tài xế ở mức cơ bản để hỗ trợ theo dõi chuyến | Should Have |
| **Fare Calculation** | Tính cước dựa trên loại xe và thông tin chuyến đi theo công thức cơ bản | Must Have |
| **Payment** | Thanh toán tiền mặt và tích hợp một phương thức thanh toán điện tử | Must Have |
| **Payment Status** | Theo dõi trạng thái thanh toán Success/Failed/Pending | Must Have |
| **Notification** | Thông báo các sự kiện chính của booking/trip/payment | Must Have |
| **Trip History** | Customer và Driver xem lịch sử chuyến | Should Have |
| **Rating** | Customer đánh giá Driver sau khi hoàn thành chuyến | Should Have |
| **Operation Dashboard** | Nhân viên vận hành xem danh sách và trạng thái các chuyến | Must Have |
| **Driver Management** | Operation quản lý danh sách tài xế | Must Have |
| **Customer Management** | Operation xem và quản lý khách hàng | Should Have |
| **Basic Reporting** | Báo cáo cơ bản về số chuyến, doanh thu, hoàn thành và hủy | Should Have |
| **RBAC** | Phân quyền cơ bản giữa Customer, Driver, Operation và Admin | Must Have |
| **Audit Log** | Lưu vết một số thao tác quản trị quan trọng | Should Have |

---

### 3. Quy trình nghiệp vụ nằm trong MVP

#### 3.1. Quy trình đặt xe

```text
Customer Login
      ↓
Nhập Pickup & Destination
      ↓
Chọn loại xe
      ↓
Tạo Booking
      ↓
Booking được tiếp nhận
      ↓
Tìm Driver
      ↓
Driver nhận chuyến
      ↓
Driver đến điểm đón
      ↓
Đón khách
      ↓
Đang thực hiện chuyến
      ↓
Hoàn thành chuyến
      ↓
Tính cước
      ↓
Thanh toán
      ↓
Đánh giá Driver
```text
Booking
   ↓
Find Available Drivers
   ↓
Filter Vehicle Type
   ↓
Sort by Distance
   ↓
Select Driver
   ↓
Send Trip Request
   ↓
 ┌───────────────┐
 │               │
Accept         Reject/Timeout
 │               │
 ↓               ↓
Assign       Next Driver
Driver           │
                 ↓
            No Driver
                 ↓
          Notify Customer

REQUESTED
    ↓
SEARCHING_DRIVER
    ↓
DRIVER_ASSIGNED
    ↓
DRIVER_ARRIVING
    ↓
DRIVER_ARRIVED
    ↓
PASSENGER_PICKED_UP
    ↓
IN_PROGRESS
    ↓
COMPLETED
