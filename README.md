# Image-to-braille-ascii
เปลี่ยนรูปภาพเป็นตัวอักษรเบล สำหรับเอาไปคอมเม้นต์ใน Platform Steam

1. อัปเดตระบบและขอสิทธิ์เข้าถึงไฟล์
ใครเคยทำแบ้วข้ามไปตรงนี้ไปเลย
pkg update && pkg upgrade
termux-setup-storage 
(ป๊อปอัพเด้งขึ้นมาให้กด อนุญาต)

2. ติดตั้งภาษา Go และตัวโปรแกรม
ติดตั้งภาษา Go: pkg install golang
ติดตั้งตัวแปลงภาพ: go install github.com/TheZoraiz/ascii-image-converter@latest
ตั้งค่าเส้นทางคำสั่ง: export PATH=$PATH:$(go env GOPATH)/bin

3. เแปลงรูปภาพเป็นจุด (Braille Art)
สมมติว่ามีรูปชื่อ olo.jpg อยู่ในโฟลเดอร์ Downloads ของมือถือ ให้ใช้คำสั่ง:
ascii-image-converter ~/storage/downloads/olo.jpg -b -d 40,20

คำอธิบายคำสั่ง:
-b: สั่งให้แสดงผลเป็นจุดเบรลล์
-d 40,20: คือการกำหนดความกว้างและสูง (ปรับตัวเลขได้ตามใจชอบเพื่อให้ภาพพอดีกับหน้าจอ)
ถ้าอยากให้ภาพออกมามีสีให้เติม -c ต่อท้ายคำสั่ง
