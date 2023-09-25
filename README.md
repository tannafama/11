from spellchecker import SpellChecker

# Создаем объект SpellChecker
spell = SpellChecker()

# Функция для исправления опечаток в тексте
def correct_spelling(text):
    # Разделяем текст на слова
    words = text.split()
    
    # Создаем список для исправленных слов
    corrected_words = []
    
    for word in words:
        # Проверяем, является ли слово опечаткой
        if spell.unknown([word]):
            # Если слово опечатка, исправляем его
            corrected_word = spell.correction(word)
            corrected_words.append(corrected_word)
        else:
            corrected_words.append(word)
    
    # Собираем исправленный текст из слов
    corrected_text = ' '.join(corrected_words)
    
    return corrected_text

# Пример использования
input_text = "Пример тексста с ошеибками"
corrected_text = correct_spelling(input_text)
print(corrected_text)
