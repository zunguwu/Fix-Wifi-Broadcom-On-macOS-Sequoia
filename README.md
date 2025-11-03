### [Hướng dẫn] Fix Wifi Broadcom trên macOS 15 Sequoia
<img src="img/Wi-Fi icon.png">
</p>

#### I. Thông tin về card wifi hỗ trợ :
* Modern cards 1 : BCM94360, BCM943602 ( mấy dòng card mà không phải sử dụng thêm AirportBrcmFixup )
* Modern cards 2 : BCM94350, BCM94352, BCM94331, BCM943224 ( mấy dòng card mà phải sử dụng thêm AirportBrcmFixup )
#### II.Cách fix Wifi đối với nhóm Card Modern 1
**Chuẩn bị**
* Tải những kext sau: IOSkywalkFamily, IO80211FamilyLegacy và AMFIPass.kext:
> https://byvn.net/KvTc
* Tải Config.plist mẫu ( để làm ví dụ ):
> https://byvn.net/DkZ0
* Opencore Legacy Patcher ( cứ mới nhất mà tải ):
> https://github.com/dortania/OpenCore-Legacy-Patcher/releases

**Cách thực hiện** 
> Vui lòng sử dụng Propertree mở config.plist.
* Bước 1 : Sau khi tải những kext ở bên trên, giải nén và copy kext vào folder EFI/OC/kexts
* Bước 2 : Mở Config.plist bằng Propertree. Bấm Ctrl + R ➝ Chọn thư mục EFI/OC ➝ Select Folder
* Bước 3 : Tiếp theo, sắp xếp những kext đã được thêm vào config.plist theo thứ tự như trong Config.plist mẫu đã tải bên trên
* Bước 4 : Copy Key 0 ở Kernel / Block trong Config.plist mẫu vào Kernel / Block ở trong Config.plist của các bác.
* Bước 5 : Thêm vào boot-args: ipc_control_port_options=0
* Bước 6 : Sửa value của csr-active-config = 03080000
* Bước 7 : Trong config.plist Đi đến NVRAM / Delete / 7C436110-AB2A-4BBB-A880-FE41995C9F82 và thêm một key bên dưới nó với type là String và Value là csr-active-config ( như trong Config.plist mẫu )
* Bước 8 : Ctrl + S để save config và Restart vào lại macOS
* Bước 9 : Tải Opencore Legacy Patcher theo Link bên trên rồi thì các bác Giải nén nó ra nhé. Tiếp đó, mở file Opencore Patcher.pkg ra và Install như App bình thường.
* Bước 10 : Sau khi Install xong thì vào Finder/Applications và mở Opencore Legacy Patcher ra rồi Chọn vào Post-Install Root   Patch. Chọn tiếp Start Root Patching và làm theo những gì App yêu cầu.
* Bước 11: Restart và tận hưởng
---
### Cách fix Wifi đối với nhóm Card Modern 2
**Chuẩn bị**
* Tải những kext sau: IOSkywalkFamily, IO80211FamilyLegacy, AirportBrcmFixup và AMFIPass.kext:
> https://drive.google.com/drive/folders/1r76QGY8RuJD1WMQavvSQTAywvXqN_Yfw?usp=drive_link
* Tải Config.plist mẫu ( để làm ví dụ ):
> https://drive.google.com/file/d/1FKBEYIwnPdnd0DTwOPsxQlV950b2uHMW/view?usp=drive_link
* Opencore Legacy Patcher ( cứ mới nhất mà tải ):
> https://github.com/dortania/OpenCore-Legacy-Patcher/releases

**Cách thực hiện**
> Vui lòng sử dụng Propertree mở config.plist.
* Bước 1 : Sau khi tải những kext ở bên trên, giải nén và copy kext vào folder EFI/OC/kexts
* Bước 2 : Mở Config.plist bằng Propertree. Bấm Ctrl + R ➝ Chọn thư mục EFI/OC ➝ Select Folder
* Bước 3 : Tiếp theo, sắp xếp những kext đã được thêm vào config.plist theo thứ tự như trong Config.plist mẫu đã tải bên trên
* Bước 4 : Copy Key 0 ở Kernel / Block trong Config.plist mẫu vào Kernel / Block ở trong Config.plist của các bác.
* Bước 5 : Thêm vào boot-args: ipc_control_port_options=0
* Bước 6 : Sửa value của csr-active-config = 03080000
* Bước 7 : Trong config.plist Đi đến NVRAM / Delete / 7C436110-AB2A-4BBB-A880-FE41995C9F82 và thêm một key bên dưới nó với type là String và Value là csr-active-config ( như trong Config.plist mẫu )
* Bước 8 : Ctrl + S để save config và Restart vào lại macOS
* Bước 9 : Tải Opencore Legacy Patcher theo Link bên trên rồi thì các bác Giải nén nó ra nhé. Tiếp đó, mở file Opencore Patcher.pkg ra và Install như App bình thường.
* Bước 10 : Sau khi Install xong thì vào Finder/Applications và mở Opencore Legacy Patcher ra rồi Chọn vào Post-Install Root   Patch. Chọn tiếp Start Root Patching và làm theo những gì App yêu cầu.
* Bước 11: Restart và tận hưởng
<br>
<p align="center">
<img width="640" src="img/Wifi active again.png">
</p>
<br>

---

  Bài hướng dẫn đến đây là kết thúc, chúc các bác thành công 
