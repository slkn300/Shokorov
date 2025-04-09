
# Инструкция: работа с SSH и GitHub

## 1. Создание SSH-ключа

```bash
# Создание нового SSH-ключа с комментарием (email от GitHub)
ssh-keygen -t ed25519 -C "your_email@example.com"

# Если система не поддерживает ed25519:
ssh-keygen -t rsa -b 4096 -C "your_email@example.com"

# При запросе пути сохранить в (нажми Enter для пути по умолчанию):
# > Enter file in which to save the key (/home/user/.ssh/id_ed25519):

# При запросе пароля можно оставить пустым
```

## 2. Добавление ключа на GitHub

```bash
# Скопировать содержимое публичного ключа
cat ~/.ssh/id_ed25519.pub

# Или, если на macOS:
pbcopy < ~/.ssh/id_ed25519.pub
```

```text
# Далее:
1. Перейти в GitHub → Settings → SSH and GPG keys
2. Нажать "New SSH key"
3. Вставить скопированный ключ в поле "Key"
4. Указать название в поле "Title" (например, "My Laptop")
5. Нажать "Add SSH key"
```

## 3. Клонирование репозитория по SSH

```bash
# Скопировать SSH-ссылку репозитория с GitHub, например:
# git@github.com:username/repository.git

# Клонировать репозиторий
git clone git@github.com:username/repository.git
```

## 4. Проверка подключения

```bash
# Проверить, что всё работает
ssh -T git@github.com

# При успехе будет сообщение:
# Hi username! You've successfully authenticated, but GitHub does not provide shell access.
```
