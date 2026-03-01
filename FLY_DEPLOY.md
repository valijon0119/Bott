# Fly.io — tezkor deploy

## 1. CLI o'rnatish (Windows PowerShell)

```powershell
iwr https://fly.io/install.ps1 -useb | iex
```

## 2. Login

```powershell
fly auth login
```

## 3. Loyiha papkasida secretlarni o'rnatish

**Muhim:** Token va linkni `fly.toml` da qoldirmang. Faqat secret sifatida:

```powershell
cd c:\Users\User\Desktop\Bot

fly secrets set BOT_TOKEN="8723577678:AAHYKj1k8b1qmzIa4Gawb7P1J1mhfCys8dQ"
fly secrets set ADMIN_GROUP_LINK="https://t.me/studentstiia"
```

## 4. Birinchi marta launch (agar ilgari `fly launch` qilmagan bo'lsangiz)

```powershell
fly launch --no-deploy
```

- App nomi: `telegram-file-bot` (yoki o'zingizniki)
- Region: `fra` (Frankfurt)
- PostgreSQL: **No**

Keyin deploy:

```powershell
fly deploy
```

## 5. Faqat deploy (loyiha allaqachon Fly da bo'lsa)

```powershell
fly deploy
```

## 6. Tekshirish

```powershell
fly status
fly logs
```

## 7. To'xtatish / qayta ishga tushirish

```powershell
fly stop
fly start
```

---

**GitHub Actions** (ixtiyoriy):  
Repository → Settings → Secrets → `FLY_API_TOKEN` qo'shing (`fly tokens create deploy` dan). Keyin `main` ga push qilganda avtomatik deploy bo'ladi.
