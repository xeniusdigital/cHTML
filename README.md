# cHTML
This is custom JS for tracking mouse hover tracking via google tag manager


<script>
var btnInfoElements = document.querySelectorAll('.add_to_cart_button');
for (var i = 0; i < btnInfoElements.length; i++) {
    btnInfoElements[i].addEventListener('mouseover', function(){
        var button = this;
        var timer = setTimeout(function(){
        var buttonText = button.textContent.trim();
        dataLayer.push({
            'event': 'hover',
            'element': 'Button',
            'elementText': buttonText
        });
        }, 3000);
        button.addEventListener('mouseout', function(){
            clearTimeout(timer);
        });
    });
}
</script>

