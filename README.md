1. Lựa chọn một API thực tế để kiểm thử

Tôi chọn API của PokeAPI, một dịch vụ phổ biến cung cấp thông tin về Pokémon.

### 2. Phân tích tài liệu API

PokeAPI là một RESTful API cung cấp dữ liệu liên quan đến Pokémon. Dưới đây là một số endpoint chính:

- Base URL: `https://pokeapi.co/api/v2`
- Các endpoint chính:
  - Get Pokémon by Name/ID: `/pokemon/{name_or_id}`
  - Get Pokémon Type by Name/ID: `/type/{name_or_id}`
  - Get Pokémon Ability by Name/ID: `/ability/{name_or_id}`

3. Viết các trường hợp kiểm thử

3.1. Kiểm thử thành công

1. Kiểm thử lấy thông tin Pokémon bằng tên
   - Mô tả: Kiểm thử API với tên Pokémon hợp lệ.
   - **Phương thức: GET
   - Endpoint: `/pokemon/pikachu`
   - Mong đợi: HTTP Status 200, thông tin về Pikachu.
   - ![image](https://github.com/shiro1351/API/assets/151829009/c3043eee-c8b5-470e-a173-8d6c210f85ab)


2. **Kiểm thử lấy thông tin Pokémon bằng ID**
   - Mô tả: Kiểm thử API với ID Pokémon hợp lệ.
   - Phương thức: GET
   - Endpoint: `/pokemon/25`
   - Mong đợi: HTTP Status 200, thông tin về Pikachu (vì ID của Pikachu là 25).
   - ![image](https://github.com/shiro1351/API/assets/151829009/d1c551c2-7a77-4c34-ad85-c21367e6137d)


3.2. Kiểm thử thất bại

3. Kiểm thử với tên Pokémon không hợp lệ
   - Mô tả: Kiểm thử API với tên Pokémon không tồn tại.
   - Phương thức: GET
   - Endpoint: `/pokemon/invalidpokemon`
   - Mong đợi: HTTP Status 404, thông báo lỗi "Not Found".
   - ![image](https://github.com/shiro1351/API/assets/151829009/bbb98416-c5a5-491a-8562-00503c8fa4a7)


4. Kiểm thử với ID Pokémon không hợp lệ
   - Mô tả: Kiểm thử API với ID Pokémon không tồn tại.
   - Phương thức: GET
   - Endpoint: `/pokemon/99999`
   - Mong đợi: HTTP Status 404, thông báo lỗi "Not Found".
   - ![image](https://github.com/shiro1351/API/assets/151829009/175a28ec-b2e2-4f80-bb26-f66c728305c2)


 4. Sử dụng Postman để thực hiện các trường hợp kiểm thử

 4.1. Tạo Collection và Request trong Postman

- Tạo một Collection mới tên là "PokeAPI Tests".
- Tạo các Request tương ứng với từng trường hợp kiểm thử.

 4.2. Thực hiện các trường hợp kiểm thử

- Test 1: 
  - Request: `GET /api/v2/pokemon/pikachu`
  - Kết quả: HTTP 200, dữ liệu đầy đủ về Pikachu.
  - ![Uploading image.png…]()

- Test 2: 
  - Request: `GET /api/v2/pokemon/25`
  - Kết quả: HTTP 200, dữ liệu đầy đủ về Pikachu.
- Test 3: 
  - Request: `GET /api/v2/pokemon/invalidpokemon`
  - Kết quả: HTTP 404, lỗi "Not Found".
- Test 4: 
  - Request: `GET /api/v2/pokemon/99999`
  - Kết quả: HTTP 404, lỗi "Not Found".

 5. Ghi lại kết quả kiểm thử và xác định các lỗi hoặc vấn đề

 5.1. Kết quả kiểm thử

- Test 1: Thành công, nhận được dữ liệu chi tiết về Pikachu.
- Test 2: Thành công, nhận được dữ liệu chi tiết về Pikachu với ID 25.
- Test 3: Thành công, nhận được thông báo lỗi hợp lệ cho tên Pokémon không tồn tại.
- Test 4: Thành công, nhận được thông báo lỗi hợp lệ cho ID Pokémon không tồn tại.

 5.2. Các lỗi hoặc vấn đề

- Không phát hiện lỗi hoặc vấn đề bất thường nào trong quá trình kiểm thử.

 6. Viết báo cáo kiểm thử chi tiết

 6.1. Mục tiêu kiểm thử

- Xác minh tính đúng đắn và hoạt động của các endpoint chính của PokeAPI.
- Đảm bảo API phản hồi chính xác với các yêu cầu hợp lệ và không hợp lệ.

 6.2. Phạm vi kiểm thử

- Kiểm thử các chức năng chính của PokeAPI bao gồm việc lấy thông tin Pokémon bằng tên và ID.
- Kiểm thử phản hồi của API với các trường hợp lỗi thông thường.

 6.3. Kết quả kiểm thử

| Test Case | Expected Result | Actual Result | Status |
|-----------|-----------------|---------------|--------|
| Test 1    | HTTP 200, Data for Pikachu | HTTP 200, Data for Pikachu | Passed |
| Test 2    | HTTP 200, Data for Pikachu | HTTP 200, Data for Pikachu | Passed |
| Test 3    | HTTP 404, Error "Not Found" | HTTP 404, Error "Not Found" | Passed |
| Test 4    | HTTP 404, Error "Not Found" | HTTP 404, Error "Not Found" | Passed |

 6.4. Khuyến nghị

- Tiếp tục kiểm thử với nhiều trường hợp khác nhau để đảm bảo tính ổn định và tin cậy của API.
- Thực hiện kiểm thử tự động hóa để tăng hiệu quả kiểm thử.

 Kết luận

Quá trình kiểm thử đã xác minh rằng PokeAPI hoạt động đúng như mong đợi với các trường hợp kiểm thử đã định nghĩa. Các kết quả kiểm thử đều đúng với dự đoán và không phát hiện lỗi nào bất thường.
