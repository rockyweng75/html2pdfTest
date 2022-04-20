<template>
    <div id="element-to-print">
        <slot/>
    </div>
    <button v-on:click="print">print</button>
</template>
<script>
import html2pdf from 'html2pdf.js'
export default {
    setup() {
        const print = () =>{
            var element = document.getElementById('element-to-print');
            html2pdf(element).save();
        }

        return{
            print
        }
    },
}
</script>