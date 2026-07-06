### 🌟 Пошаговое руководство по развертыванию проекта с использованием **CI/CD через GitHub Actions и PythonAnywhere**

---

#### 1️⃣ Зарегистрируйтесь на GitHub 🐙  
- Используйте вашу почту.

---


#### 2️⃣ Сделайте форк репозитория 📂  
- Перейдите по ссылке: [course_qa_manual_ci_actions](https://github.com/danilfg/course_qa_manual_ci_actions).  
- Нажмите кнопку **Fork** в правом верхнем углу, чтобы создать копию проекта в вашем GitHub-аккаунте.

---

#### 3️⃣ Зарегистрируйтесь на сайте OpenWeatherMap 🌍  
- Перейдите на [openweathermap.org](https://openweathermap.org/) и создайте аккаунт.

---

#### 4️⃣ Создайте API Key 🔑  
- После регистрации в OpenWeatherMap создайте новый **API Key**, который понадобится для работы с погодным API.

---

#### 5️⃣ Добавьте API Key в файл `weather/views.py` 🔧  
1. Откройте файл `weather/views.py`.  
2. Найдите переменную `API_KEY`.  
3. Замените значение на ваш API ключ:  
   ```python
   API_KEY = "ваш_ключ_API"
   ```
4. Сохраните изменения.

---

#### 6️⃣ Зарегистрируйтесь на PythonAnywhere ☁️  
- Перейдите на [pythonanywhere.com](https://www.pythonanywhere.com/) и создайте аккаунт.  
- Обязательно подтвердите вашу почту! 📧

---

#### 7️⃣ Создайте веб-приложение на PythonAnywhere 🌐  
1. Перейдите в **Dashboard → Web**.  
2. Нажмите **"Add a new web app"**.  
3. Укажите настройки:  
   - **Domain name**: оставьте предложенное (`your-username.pythonanywhere.com`).  
   - **Python version**: выберите версию, совместимую с проектом (например, 3.9).

---

#### 8️⃣ Создайте API-токен для PythonAnywhere 🔐  
1. Перейдите в раздел **Account → API Token**.  
2. Нажмите **"Create new API token"**.  
3. Сохраните его, он понадобится для настройки.  

---

#### 9️⃣ Найдите ID консоли на PythonAnywhere 💻  
1. Перейдите в **Consoles**.  
2. Создайте новую консоль, выбрав **Other: Bash**.  
3. Скопируйте **ID консоли** из URL (например, `/user/<username>/consoles/<id>/`).

---

#### 🔟 Добавьте переменные в GitHub 🔧  
1. В вашем репозитории перейдите в **Settings → Secrets and variables → Actions → New repository secret**.  
2. Создайте следующие переменные:  
   - `PYTHONANYWHERE_API_TOKEN` — ваш API-токен.  
   - `PYTHONANYWHERE_USERNAME` — ваш логин на PythonAnywhere.  
   - `CONSOLE_ID` — ID консоли, который вы скопировали на предыдущем шаге.  

---

#### 1️⃣1️⃣ Добавьте новое поле влажности (Humidity) в проект 🌧️  
1. В файле `views.py` передайте влажность:  
   ```python
   weather_info = {
       'humidity': data['main']['humidity'],  # Новое поле
   }
   ```
2. В файле `index.html` отобразите влажность в UI:  
   ```javascript
   if (response.ok) {
       result.innerHTML = `
       <p>Humidity: ${data.humidity}%</p>  <!-- Новое поле -->
       `;
   }
   ```

3. Закоммитьте и запушьте изменения:  
   ```bash
   git add .
   git commit -m "Добавлено поле влажности в UI"
   git push origin main
   ```

---

Теперь ваш проект развернут с использованием **GitHub Actions** и работает на **PythonAnywhere**! 🚀
