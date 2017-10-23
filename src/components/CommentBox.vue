<template>
  <div class="commentBox">
    <input type="text" id="commentForm" @keyup.enter="submitComment" >
    <button id='btn' @click="submitComment">提交</button>
    <ul>
      <li v-for="comment in comments">
        {{comment.text}}
      </li>
    </ul>
  </div>
</template>

<script>
  export default {
    name: 'commentBox',
    data: () => ({
      comments: [
        { text: 'Foo' },
        { text: 'Bar' }
      ]
    }),
    methods: {
      submitComment () {
        let input = document.getElementById('commentForm')
        if (input.value !== '') {
          this.comments.push({text: input.value})
          input.value = ''
        }
      }
    }
  }
</script>

<style scoped>
.commentBox{
  height: 150px;
  width: 80%;
  margin: 0 auto;
  background-color: #fff;
  box-shadow: 0 2px 2px rgba(0, 0, 0, 0.5);
  margin-bottom: 30px;
}
.commentBox ul{
  list-style: none;
}
.commentBox li{
  font-size: 18px;
  line-height: 25px;
}
</style>
