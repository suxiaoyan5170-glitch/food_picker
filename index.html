# <!DOCTYPE html>  
# <html lang="zh-TW">  
# <head>  
#     <meta charset="UTF-8">  
#     <meta name="viewport" content="width=device-width, initial-scale=1.0">  
#     <title>視覺系吃貨地圖 v4.0</title>  
#     <style>  
#         :root { --primary: #FF3B30; --bg: #F2F2F7; --card: #FFFFFF; }  
#         body { font-family: -apple-system, sans-serif; background: var(--bg); display: flex; justify-content: center; padding: 20px; }  
#         .container { background: var(--card); width: 100%; max-width: 450px; padding: 25px; border-radius: 24px; box-shadow: 0 15px 35px rgba(0,0,0,0.1); position: relative; }  
#           
#         /* 分類標籤 */  
#         .category-tabs { display: flex; gap: 8px; overflow-x: auto; margin-bottom: 20px; padding-bottom: 5px; }  
#         .tab { white-space: nowrap; padding: 8px 16px; background: #E5E5EA; border-radius: 20px; font-size: 14px; cursor: pointer; }  
#         .tab.active { background: var(--primary); color: white; }  
#   
#         /* 列表樣式 */  
#         .list-container { border: 1px solid #E5E5EA; border-radius: 15px; max-height: 180px; overflow-y: auto; margin-bottom: 20px; }  
#         li { padding: 12px 15px; display: flex; justify-content: space-between; border-bottom: 1px solid #F2F2F7; user-select: none; cursor: pointer; }  
#         li:active { background-color: #f0f0f0; }  
#   
#         /* 圖片預覽浮窗 */  
#         #imagePreview {   
#             position: fixed; display: none; width: 200px; height: 150px;   
#             background: #000; border-radius: 15px; z-index: 100;   
#             box-shadow: 0 10px 20px rgba(0,0,0,0.3); overflow: hidden;  
#             pointer-events: none; /* 防止遮擋鼠標 */  
#         }  
#         #previewImg { width: 100%; height: 100%; object-fit: cover; }  
#   
#         /* 結果顯示 */  
#         .result-box { text-align: center; margin: 20px 0; min-height: 120px; }  
#         #resultValue { font-size: 36px; font-weight: 800; color: var(--primary); }  
#           
#         .map-link {   
#             display: inline-block; margin-top: 10px; color: #007AFF;   
#             text-decoration: none; font-size: 14px; font-weight: 600;  
#             display: none; /* 抽中前隱藏 */  
#         }  
#   
#         .main-btn { background: #1C1C1E; color: white; width: 100%; padding: 18px; border-radius: 15px; font-size: 20px; border: none; cursor: pointer; }  
#     </style>  
# </head>  
# <body>  
#   
# <div id="imagePreview"><img id="previewImg" src="" alt="預覽"></div>  
#   
# <div class="container">  
#     <h1>🍴 視覺系選擇器</h1>  
#   
#     <div class="category-tabs" id="tabs">  
#         <div class="tab active" onclick="switchTheme('custom')">自定義</div>  
#         <div class="tab" onclick="switchTheme('sichuan')">川菜🌶️</div>  
#         <div class="tab" onclick="switchTheme('cantonese')">粵菜🍤</div>  
#         <div class="tab" onclick="switchTheme('shanghai')">本幫菜</div>  
#     </div>  
#   
#     <div class="list-container">  
#         <ul id="itemList"></ul>  
#     </div>  
#   
#     <div class="result-box">  
#         <div id="resultValue">點擊下方開始</div>  
#         <a id="mapLink" class="map-link" target="_blank">📍 在地圖上搜尋附近餐廳</a>  
#     </div>  
#   
#     <button class="main-btn" onclick="roll()">開始隨機抽選</button>  
#     <p style="font-size: 10px; color: #888; text-align: center;">提示：長按選項可預覽圖片</p>  
# </div>  
#   
# <script>  
#     const database = {  
#         sichuan: ["麻婆豆腐", "宮保雞丁", "水煮魚", "回鍋肉", "辣子雞"],  
#         cantonese: ["白切雞", "燒鵝", "蝦餃", "乾炒牛河", "蒸排骨"],  
#         shanghai: ["小籠包", "紅燒肉", "糖醋排骨", "生煎包", "大閘蟹"],  
#         custom: JSON.parse(localStorage.getItem('myFoodList')) || ["火鍋", "拉麵", "壽司"]  
#     };  
#   
#     let currentList = [...database.custom];  
#     let pressTimer;  
#   
#     function renderList() {  
#         const ul = document.getElementById('itemList');  
#         ul.innerHTML = currentList.map((item, i) => `  
#             <li onmousedown="startPress(event, '${item}')"   
#                 onmouseup="endPress()"   
#                 ontouchstart="startPress(event, '${item}')"   
#                 ontouchend="endPress()">  
#                 ${item}  
#             </li>  
#         `).join('');  
#     }  
#   
#     // --- 長按預覽邏輯 ---  
#     function startPress(e, itemName) {  
#         pressTimer = setTimeout(() => {  
#             showPreview(e, itemName);  
#         }, 800); // 設定長按 0.8 秒觸發  
#     }  
#   
#     function endPress() {  
#         clearTimeout(pressTimer);  
#         document.getElementById('imagePreview').style.display = 'none';  
#     }  
#   
#     function showPreview(e, name) {  
#         const preview = document.getElementById('imagePreview');  
#         const img = document.getElementById('previewImg');  
#           
#         // 使用 Unsplash API 獲取圖片 (關鍵字搜尋)  
#         img.src = `https://source.unsplash.com/featured/400x300?food,${name}`;  
#           
#         // 設定浮窗位置 (跟隨手指或滑鼠)  
#         const x = e.clientX || e.touches[0].clientX;  
#         const y = e.clientY || e.touches[0].clientY;  
#         preview.style.left = (x - 100) + 'px';  
#         preview.style.top = (y - 160) + 'px';  
#         preview.style.display = 'block';  
#     }  
#   
#     // --- 抽選與地圖邏輯 ---  
#     function roll() {  
#         let count = 0;  
#         document.getElementById('mapLink').style.display = 'none';  
#           
#         const timer = setInterval(() => {  
#             const temp = currentList[Math.floor(Math.random() * currentList.length)];  
#             document.getElementById('resultValue').innerText = temp;  
#             count++;  
#               
#             if (count > 12) {  
#                 clearInterval(timer);  
#                 const final = currentList[Math.floor(Math.random() * currentList.length)];  
#                 document.getElementById('resultValue').innerText = "✨ " + final;  
#                   
#                 // 設定地圖連結  
#                 const mapLink = document.getElementById('mapLink');  
#                 mapLink.href = `https://www.google.com/maps/search/${final}+餐廳`;  
#                 mapLink.style.display = 'inline-block';  
#             }  
#         }, 80);  
#     }  
#   
#     function switchTheme(theme) {  
#         currentList = [...database[theme]];  
#         renderList();  
#         // 更新 UI 選項卡狀態 (省略細節)  
#     }  
#   
#     renderList();  
# </script>  
#   
# </body>  
# </html>  
#   
