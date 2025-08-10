

# نکات مهم 

استراتژی Branching (Git Flow)
۱. شاخه‌های اصلی (Long-lived branches)
main :

همیشه در وضعیت deployable

فقط از طریق PR و پس از review می‌توان به آن merge کرد

تگ‌های نسخه در این شاخه ایجاد می‌شوند

develop:

شاخه اصلی توسعه

تمام featureها به این شاخه merge می‌شوند
=

۲. شاخه‌های موقت (Short-lived branches)
الف) Feature branches (برای توسعه ویژگی‌های جدید)
نامگذاری: feature/[نام-ویژگی] یا feat/[نام-ویژگی]

مثال:

feature/user-authentication

feat/product-filter

ایجاد از: develop

merge به: develop

ب) Release branches (برای آماده‌سازی نسخه)
نامگذاری: release/[version]

مثال: release/v1.0.0

ایجاد از: develop

merge به: develop و main

ج) Hotfix branches (برای رفع باگ‌های فوری)
نامگذاری: hotfix/[نام-رفع]

مثال: hotfix/login-bug

ایجاد از: main

merge به: develop و main




#قبل از شروع کار
git checkout develop
git pull origin develop
git checkout -b feature/[نام-ویژگی]

#پس از اتمام کار روزانه
git add .
git commit -m "پیام توصیفی و معنادار"
git push origin feature/[نام-ویژگی]

#نکات مهم 
هنگام ایجاد Pull Request:

PR باید به develop merge شود

حداقل نیاز به یک Approve دارد

تمام تست‌ها باید پاس شوند

باید شامل توضیحات کافی باشد


git fetch origin
git rebase origin/develop
# رفعconflict
git add .
git rebase --continue
git push --force-with-lease
