// Найдите все строки таблицы
var rows = document.querySelectorAll('.okui-table-row');

// Функция для обработки каждой строки
function processRow(index) {
  if (index >= rows.length) {
    // Все строки обработаны
    return;
  }

  var row = rows[index];
  var deleteButton = row.querySelector('.actions .action:last-child');

  if (deleteButton && deleteButton.textContent === 'Удалить') {
    console.log('Клик на кнопке "Удалить"');
    deleteButton.click();

    // Добавьте задержку в 3 секунды перед кликом на кнопку "Подтвердить"
    setTimeout(function() {
      // Ожидайте появления модального окна
      var modal = document.querySelector('.okui-dialog-window');
      var confirmButton = modal.querySelector('.okui-dialog-footer-box .btn-fill-highlight');

      // Проверьте, найдена ли кнопка "Подтвердить"
      if (confirmButton && confirmButton.textContent === 'Подтвердить') {
        console.log('Клик на кнопке "Подтвердить"');
        confirmButton.click();

        // Добавьте задержку в 3 секунды после клика на кнопку "Подтвердить"
        setTimeout(function() {
          // Обработайте следующую строку
          processRow(index + 1);
        }, 2000); // Задержка в 3 секунды после клика на кнопку "Подтвердить"
      } else {
        // Обработайте следующую строку
        processRow(index + 1);
      }
    }, 300); // Задержка в 3 секунды перед кликом на кнопку "Подтвердить"
  } else {
    // Обработайте следующую строку
    processRow(index + 1);
  }
}

// Начните обработку первой строки
processRow(0);
