const Discord = require('discord.js');
const client = new Discord.Client();
const settings = require('./settings.json');
const prefix = '#';

const http = require('http');
const express = require('express');
const app = express();

client.on('ready',() => {
  console.log('It\'s a new day!');
})

client.on('ready', () => {
  console.log("Lady Freya is awake");
});

client.on('guildMemberAdd', member => {
  let newmember = client.guilds.get('462870874413072395').channels.get('462871734140272650');
  console.log('User ' + member.user.username + ' has joined the Realm!')
  newmember.send('Welcome ' + member.user.username + ' to the Realm of Peripéteia! \n \nPlease read our Rules and Guidelines, to progress onto the next stage.')
})

client.on('message', message => {
  
  let msg = message.content.toLowerCase();
  let sender = message.author;
  let command = message.content.toLowerCase().split(' ')[0];
  command = command.slice(prefix.length);
  let arg = message.content.split(' ').slice(1);
  
  let args = message.content.substring(prefix.length).split(" ");
  let player = message.guild.member(message.mentions.users.first() || message.guild.members.get(args[1]))

  let newmember = client.guilds.get('462870874413072395').channels.get('462871734140272650');
  let general = client.guilds.get('462870874413072395').channels.get('462870874413072397');
  let arena = client.guilds.get('462870874413072395').channels.get('462890257604673537');
  let city = client.guilds.get('462870874413072395').channels.get('462877793517043723');
  let castle = client.guilds.get('462870874413072395').channels.get('462892248175214592');
  let jail = client.guilds.get('462870874413072395').channels.get('464185849311920128');
  let resolve = client.guilds.get('462870874413072395').channels.get('464610468133208086');
  let submit = client.guilds.get('462870874413072395').channels.get('467864411172896778');
  let feedback = client.guilds.get('462870874413072395').channels.get('476645268809449475');

  let role_general = message.member.guild.roles.find('name', '────── General ──────');
  let role_member = message.member.guild.roles.find('name', '☘️');
  let rolethree = message.member.guild.roles.find('name', 'Arena');
  let rolefour = message.member.guild.roles.find('name', 'City');
  let rolefive = message.member.guild.roles.find('name', 'Castle');
  let role_jail = message.member.guild.roles.find('name', '⛓️');
  let roleseven = message.member.guild.roles.find('name', 'Resolve');

  let guildhs = client.guilds.get('462870874413072395').channels.get('716091172010852412');
  let guildar = client.guilds.get('462870874413072395').channels.get('716085809878663189');
  let guildpm = client.guilds.get('462870874413072395').channels.get('717219606972071937');
  let guildww = client.guilds.get('462870874413072395').channels.get('719905783680073758');
 
  let memberhs = message.member.guild.roles.find('name', '🌟Honor Society');
  let memberar = message.member.guild.roles.find('name', '💞Arcane Recovery');
  let memberpm = message.member.guild.roles.find('name', '✨Praetorium Magi');
  let memberww = message.member.guild.roles.find('name', '💪Warriors Way');
  
  let guesths = message.member.guild.roles.find('name', 'HS Guest');
  let guestar = message.member.guild.roles.find('name', 'AR Guest');
  let guestpm = message.member.guild.roles.find('name', 'PM Guest');
  let guestww = message.member.guild.roles.find('name', 'WW Guest')

if (message.author.bot) return;

  if (command === 'goodnight') {
    if(message.author.id !== process.env.ownerID) return;
    general.send("Farewell Adventurers!").then(()=>process.exit(0))
  }

  if (command === 'ihavereadtherules') {
      message.delete();
      message.member.addRole(role_general);
      message.member.addRole(role_member);
      general.send(message.member.displayName + ' has officially joined our ranks!');
  }
  
  if (command === 'feedback') {
      feedback.send(arg.join(" "));
      message.delete(100);
      submit.send('Thank you for submitting anonymous feedback - this will help us to make improvements around here!');
  }

  switch (args[0]) {
  case "invite":
//    if(!player) return message.reply("That person cannot be found!");
      
    if(message.member.roles.find("name","🌟Honor Society")) 
    {
      player.addRole(guesths);
      guildhs.send(player.displayName + ' has been invited to the guild hall!');
      setTimeout(() => {player.removeRole(guesths);}, 1000 *  60 * 60 * 8 );
    }
    if(message.member.roles.find("name","💞Arcane Recovery")) 
    {
      player.addRole(guestar);
      guildar.send(player.displayName + ' has been invited to the guild hall!');
      setTimeout(() => {player.removeRole(guestar);}, 1000 *  60 * 60 * 8 );
    }
    if(message.member.roles.find("name","✨Praetorium Magi")) 
    {
      player.addRole(guestpm);
      guildpm.send(player.displayName + ' has been invited to the guild hall!');
      setTimeout(() => {player.removeRole(guestpm);}, 1000 *  60 * 60 * 8 );
    }
    if(message.member.roles.find("name","💪Warriors Way")) 
    {
      player.addRole(guestww);
      guildww.send(player.displayName + ' has been invited to the guild hall!');
      setTimeout(() => {player.removeRole(guestww);}, 1000 *  60 * 60 * 8 );
    }
  break;
  }

  if (command === 'entercity') {
      message.member.addRole(rolefour);
      message.member.removeRole(rolefive);
      city.send('You may pass ' + message.member.displayName + '. We hope you enjoy your stay!');
  }

  if (command === 'enterjail') {
      message.channel.send(message.member.displayName + ' has been arrested and will spend the night in jail.')
      message.member.addRole(role_jail);
      message.member.removeRole(rolefour);
      message.member.removeRole(rolefive);
      jail.send(message.member.displayName + ' is now in jail.');
  }
  
  switch (args[0]) {
  case "sendjail":
      if(!player) return message.reply("That person cannot be found!");
      message.channel.send(player.displayName + ' has been arrested and will spend the night in jail.');
      player.addRole(role_jail);
      player.removeRole(rolefour);
      player.removeRole(rolefive);
      jail.send(player.displayName + ' is now in jail.');
  break;
  }
  
  if (command === 'leavejail') {
      message.member.addRole(rolefour);
      message.member.removeRole(role_jail);
      jail.send(message.member.displayName + ' has been released from jail.');
  }

  if (msg.startsWith(prefix + 'link')) {
      message.channel.send('https://discord.gg/zxg5pUQ')
  }

})

client.login(process.env.token);
