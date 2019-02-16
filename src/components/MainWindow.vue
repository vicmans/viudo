<template>
  <Window title="Bienvenidos" width="400" height="150" margined v-on:close="exit">
    <Box>
      <Text>Hola que tal ok!</Text>
      <Form padded>
        <TextInput label="First name:" v-model="firstName"/>
        <TextInput label="Last name:" v-model="lastName" />
      </Form>
      <Text>{{firstName}}</Text>
      <Separator horizontal/>
      <Box horizontal padded>
        <Button v-on:click="count-=1">-</Button>
        <Text>{{count}}</Text>
        <Button @click="count+=1">+</Button>
      </Box>
      <Box horizontal padded>
        <Button v-on:click="showMessage()">OK</Button>
        <Button v-on:click="exit()">Cancel</Button>
      </Box>
    </Box>
  </Window>
</template>

<script>
import libui from 'libui-node'

export default {
  methods: {

    exit() {
      libui.stopLoop();
    },
    showMessage(){
      this.$dialogs.msgBox( 'Title', 'This is the message.' );
    }
  },
  data(){
    return {
      count: 0,
      firstName: 'nombre',
      lastName: 'apellido'
    }
  }
}
</script>
