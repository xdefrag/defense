---
theme: default
highlighter: shiki
lineNumbers: false
title: Как Славко Анкапич в блокчейне право искал
transition: slide-up
colorSchema: dark
layout: image-right
image: ./images/slavko_ancapich.png
backgroundSize: 25em
hideInToc: true
---

# Как Славко Анкапич
## в блокчейне право искал

<div class="absolute bottom-10">
  <span class="font-500">
    Стас Каркавин
  </span>
</div>

---
hideInToc: true
layout: image-right
image: ./images/stas_speaker.jpg
---

# Стас Каркавин
Представитель и член Совета «Ассоциации Монтелиберо».

tw: [twitter.com/xdefrag](https://twitter.com/xdefrag)

tg: [xdefrag.t.me](https://xdefrag.t.me)

<div class="grid grid-cols-2 mt-10">
  <div class="cols-6 grid-justify-self-center">
    <a href="https://twitter.com/xdefrag" target="_blank"><img src="/images/me_tw.png" class="w-30" /></a>
  </div>
  <div class="cols-6 grid-justify-self-center">
    <a href="https://xdefrag.t.me" target="_blank"><img src="/images/me_tg.png" class="w-30" /></a>
  </div>
</div>
---
hideInToc: true
layout: default
---

# О чем поговорим?

<Toc></Toc>

---
layout: image-left
image: ./images/slavko_ancapich.png
backgroundSize: 25em
hideInToc: true
---

# Славко Анкапич

<v-clicks>

- Не прибегает к насилию, кроме случаев обороны.

- Признает частную собственность и право собственности на самого себя.

- Обладает хотя бы одним конкурентным навыком.

- Хочет внести вклад в строительство свободного мира на либертарианских принципах.

</v-clicks>

---
layout: image-right
image: ./images/blockchain.png
backgroundSize: 25em
---

# Блокчейн

<v-clicks>

- По дизайну отсутствует возможность централизованной регуляции.

- Создание личного или корпоративного счета без бюрократии.

- Децентрализованная и неизменяемая бухгалтерская книга.

- Децентрализованный и неизменяемый реестр данных.

</v-clicks>

---
layout: image-left
image: ./images/stellar.png
backgroundSize: 25em
---

# Stellar

<v-clicks>

- Прост в использовании.

- Встроенная биржа.

- Много функционала работает из коробки (создание токенов, ключ-значения на счетах етц).

- Простые инструменты для разработчиков.

</v-clicks>

---
layout: image-right
image: ./images/slavko_capitalist.png
backgroundSize: 16em
---

# Токеномика

Токены как

<v-clicks>

- Замена фиату (стейблкоины) или другой крипты.

- Обозначение рабочих часов и взаимодействий.

- Акции и облигации бизнес-проектов.

- Фиксация владения земли, недвижимости, золота и прочих ресурсов.

</v-clicks>

---
layout: default
---

# Создание токена

```go {all|1|3-11|13-23|all}
token := txnbuild.CreditAsset{Code: "ANCAP", Issuer: issuer.Address()}
...
tx, _ := txnbuild.NewTransaction(txnbuild.TransactionParams{
  SourceAccount: distributorDetails,
  Operations: []txnbuild.Operation{
    &txnbuild.ChangeTrust{
      Line: txnbuild.ChangeTrustAssetWrapper{Asset: token},
    },
  },
  ...
})
...
tx, _ := txnbuild.NewTransaction(txnbuild.TransactionParams{
  SourceAccount:        &issuerDetails,
  Operations: []txnbuild.Operation{
    &txnbuild.Payment{
      Amount:      "1000",
      Asset:       token,
      Destination: distributor.Address(),
    },
  },
  ...
})
```

---
layout: image-left
image: ./images/slavko_matrix.png
backgroundSize: 25em
---

# Нотариат

Позволяет фиксировать

<v-clicks>

- Родственные связи, совместные проекты, доверие друг к другу.

- Договорные отношения между владельцами счетов.

- Двусторонние отношения (долевое владение, представительство).

- Статусы отношения или участия к счетам сообществ.

</v-clicks>

---
layout: default
---

# Создание ключ-значения на счете

```go {all|1-10|12-21|all}
tx, _ := txnbuild.NewTransaction(txnbuild.TransactionParams{
  SourceAccount:        &employeeDetails, // аккаунт сотрудника
  Operations: []txnbuild.Operation{
    &txnbuild.ManageData{
      Name:  "Employer", // работодатель
      Value: []byte(employer.Address()),
    },
  },
  ...
})
...
tx, _ := txnbuild.NewTransaction(txnbuild.TransactionParams{
  SourceAccount:        &employerDetails, // аккаунт работодателя
  Operations: []txnbuild.Operation{
    &txnbuild.ManageData{
      Name:  "Employee", // сотрудник
      Value: []byte(employee.Address()),
    },
  },
  ...
})
...
```
---
layout: default
backgroundSize: 16em
---

# А дальше что?

<div class="grid grid-cols-2 mt-10">
  <div class="cols-6 grid-justify-self-center">
    <a href="https://t.me/Seasteading_EastEurope" target="_blank"><img src="/images/qr_mtl.png" class="w-60 m-10" /></a>
  </div>
  <div class="cols-6 grid-justify-self-center">
    <a href="https://gist.github.com/xdefrag/63e6014bf6c2d172a8fe9a63424a1e8f" target="_blank"><img src="/images/qr_stellar_gist.png" class="w-60 m-10" /></a>
  </div>
</div>
