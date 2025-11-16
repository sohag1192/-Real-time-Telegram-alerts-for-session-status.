# -Real-time-Telegram-alerts-for-session-status. ![Badge](https://hitscounter.dev/api/hit?url=https%3A%2F%2Fgithub.com%2Fsohag1192%2F-Real-time-Telegram-alerts-for-session-status&label=&icon=github&color=%23198754&message=&style=flat&tz=UTC)
 
✅ Real-time Telegram alerts for  status.

---

## 🔧 Installation / ইনস্টলেশন

1. MikroTik RouterOS স্ক্রিপ্টে নিচের কোড ব্যবহার করুন।
2. Telegram Bot Token এবং Chat ID কনফিগার করুন।

---

## 🚀 Features / ফিচার

- ✅ BGP UP হলে Telegram এ লাইভ নোটিফিকেশন
- ❌ BGP DOWN হলে Critical Alert
- 📅 টাইম ও ডেট সহ লগ

---


```mikrotik
:local host "your ip or host"
:local CurDate [/system clock get date]
:local CurTime [/system clock get time]
:local CHID "-1003145062343"
:local BotID "7196063280:AAFhAgYxnKcOl7_yW7aIfYBifwqZDdTkQRI"

:local Message "%E2%9C%85%20**FACEBOOK%20P2P%20BGP%20UP%20NOW%20LIVE**%0A%0A%F0%9F%93%B1%20**Peer%20IP:**%20$host%0A%F0%9F%93%8A%20**Service:**%20FB%20P2P%20BGP%0A%F0%9F%95%92%20**Time:**%20$CurTime%0A%F0%9F%93%85%20**Date:**%20$CurDate%0A%0A%E0%A6%8F%E0%A6%96%E0%A6%A8%20%E0%A6%B2%E0%A6%BE%E0%A6%87%E0%A6%AD%20%E0%A6%9A%E0%A6%B2%E0%A6%9B%E0%A7%87%20%E2%9C%A8"

:local URL ("https://api.telegram.org/bot" . $BotID . "/sendMessage?chat_id=" . $CHID . "&text=" . $Message)

/tool fetch url=$URL keep-result=no
```

And here’s the **BGP DOWN NOW OFFLINE** version:

```mikrotik
:local host "your ip or host"
:local CurDate [/system clock get date]
:local CurTime [/system clock get time]
:local CHID "-1003145062343"
:local BotID "7196063280:AAFhAgYxnKcOl7_yW7aIfYBifwqZDdTkQRI"

:local Message "%E2%9D%8C%20**FACEBOOK%20P2P%20BGP%20DOWN%20NOW%20OFFLINE**%0A%0A%F0%9F%93%B1%20**Peer%20IP:**%20$host%0A%F0%9F%93%8A%20**Service:**%20FB%20P2P%20BGP%0A%F0%9F%95%92%20**Time:**%20$CurTime%0A%F0%9F%93%85%20**Date:**%20$CurDate%0A%0A%E0%A6%8F%E0%A6%96%E0%A6%A8%20%E0%A6%85%E0%A6%AB%E0%A6%B2%E0%A6%BE%E0%A6%87%E0%A6%A8%20%E0%A6%9A%E0%A6%B2%E0%A6%9B%E0%A7%87%20%F0%9F%9A%A8"

:local URL ("https://api.telegram.org/bot" . $BotID . "/sendMessage?chat_id=" . $CHID . "&text=" . $Message)

/tool fetch url=$URL keep-result=no
```




## 📬 Contact

Telegram: [@sohag1192](https://t.me/sohag1192)
