var vm = new Vue({
  el: '#chat-box',
  data: {
    input_message: '',
    messages: [
      {id: 1, name: 'rubber-duck', message: 'quark', datetime: (new Date().toISOString())},
    ],
  },
  methods:{
    send: function(event){
      var next_id = this.messages.length + 1;
      this.messages.unshift({id:next_id, name: 'You', message: this.input_message, datetime: (new Date().toISOString())});
      this.messages.unshift({id: next_id + 1, name: 'rubber-duck', message: 'quark', datetime: (new Date().toISOString())});
      this.input_message = '';
    }
  }
})
