window.onload = function () {
  var buttons = document.getElementsByTagName('span');
  var calcDisplay = document.querySelectorAll('.calcDisplay p')[0];
  var erase = document.getElementsbyClassName('.erase')[0];
  
  for (var n = 0; n < buttons.length; n++) {
    if (buttons[n].innerHTML === '=') {
      buttons[n].addEventListener("click", evaluate(n));
        }
     else
        {
       buttons[n].addEventListener("click", addValues(n));
    }
  }
};

function evaluate(n) {
  return function () {
    calcDisplay.innerHTML = eval(calcDisplay.innerHTML);
  };
}

function addValues (n) {
  return function () {
  calcDisplay.innerHTML = calcDisplay.innerHTML + buttons[n].innerHTML;
  };
}


clear.onclick = function () {
  calcDisplay.innerHTML = '';
}