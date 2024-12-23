# Studentlist

## 安裝與執行指引

1. __複製專案倉庫：__
    ```
    git clone https://github.com/pyq1000/Studentlist.git
    cd Studentlist
    ```
2. __安裝項目：__
    * 後端：
        ```
        cd backend
        npm install
        ```
    * 前端：
        ```
        cd frontend
        npm install
        ```
3. __設置環境變數：__
    * 在後端資料夾中建立一個 `.env` 文件，內容如下：
        ```
        DBUSER = test
        DBPASSWORD = password
        DBHOST = 127.0.0.1
        DBPORT = 8974
        DBNAME = name
        PORT = 2083
        LogPath = logs
        assetsPath = /assets
        HomePagePath = /index.html
        privateKey = key
        ```
4. __執行程式：__
    * 後端：
    ```
    cd backend
    npm run dev
    ```
    * 前端：
    ```
    cd backend
    npm run dev
    ```
5. 打開瀏覽器並訪問 `http://localhost:5173`


## API規格說明

### 基本URL

```
http://localhost:1000/api/v1/user
```
### 端點
1. __查詢所有學生資訊__
    * 方法：GET
    * 端點：`/findAll`
    * 回應：
        ```
        {
            "code": 200,
            "message": "find sucess",
            "body": [
                {
                    "_id": "ID",
                    "userName": "tkuxx0000",
                    "sid": "座號",
                    "name": "姓名",
                    "department": "科系",
                    "grade": "年級",
                    "class": "班級",
                    "email": "example@gmail.com"
                },
                ...
            ]
        }
        ```
2. __新增學生資訊__
    * 方法：POST
    * 端點：`/insertOne`
    * 請求：
        ```
        {
        "userName": "tkuxx0000",
        "name": "姓名",
        "department": "科系",
        "grade": "年級",
        "class": "班級",
        "email": "example@gmail.com"
        }
        ```
    * 回應：
        ``` 
        {
            "code": 200,
            "message": "insert success",
            "body": {
                "userName": "tkuxx0000",
                "sid": "座號",
                "name": "姓名",
                "department": "科系",
                "grade": "年級",
                "class": "班級",
                "email": "example@gmail.com",
                "_id": "ID",
                "__v": 缺席次數
            }
        }
        ```
3. __依ID查詢單一學生資訊__
    * 方法：GET
    * 端點：`/findByID`
    * 請求：
        | 名稱  | 類型   |
        | ----- |:------:|
        | `id`  | String |
    * 回應：
        ``` 
        {
            "code": 200,
            "message": "Success",
            "body": {
                "_id": "ID",
                "userName": "tkuxx0000",
                "sid": "座號",
                "name": "姓名",
                "department": "科系",
                "grade": "年級",
                "class": "班級",
                "email": "example@gmail.com"
            }
        }
        ```
4. __依ID更新學生姓名__
    * 方法：PUT
    * 端點：`/updateNameByID`
    * 請求：
        ```
        {
            "id":"ID",
            "name":"要更改的名字"
        }
        ```
    * 回應：
        ``` 
        {
            "code": 200,
            "message": "Update Success",
            "body": {
                "_id": "ID",
                "userName": "tkuxx0000",
                "sid": "座號",
                "name": "姓名",
                "department": "科系",
                "grade": "年級",
                "class": "班級",
                "email": "example@gmail.com",
                "__v": 缺席次數
            }
        }
        ```
5. __依ID刪除學生資訊__
    * 方法：Delete
    * 端點：`/deleteByID`
    * 請求：
        | 名稱  | 類型   |
        | ----- |:------:|
        | `id`  | String |
    * 回應：
        ``` 
        {
            "code": 200,
            "message": "Success",
            "body": {
                "acknowledged": true,
                "deletedCount": 1
            }
        }
        ```

## 架構圖

![架構圖](image/架構圖.png "架構圖")

## 流程圖

![流程圖](image/流程圖.png "流程圖")

## Demo影片
<https://youtu.be/irZhgtVfVb0>




