<template>
  <div class="speaker-box">
    <div class="speaker-image">
      <img :src="speaker.profilePicture" alt>
    </div>
    <div class="bizin-trouv-bien"></div>
    <div class="speaker-meta">
      <div class="name">{{ speaker.fullName }}</div>
      <div class="occupation">{{ speaker.tagLine }}</div>
      <div class="alias"></div>
      <div class="talk-count" v-if="speaker.sessions.length > 1">{{ speaker.sessions.length }} talks</div>
      <div class="talk-count" v-else>{{ speaker.sessions.length }} talk</div>
      <div class="social-media-wrapper"></div>
    </div>
  </div>
</template>

<script>
export default {
  props: ["speaker"],
  data() {
    return {
      defaultSpeaker: {
        "id": "56985eb6-8db1-4657-bc0d-3e925cdf4e60",
        "firstName": "Akshay",
        "lastName": "Gopaul",
        "fullName": "Akshay Gopaul",
        "bio": "Name : Akshay Gopaul\r\nSoftware Developer at ASTEK Mauritius\r\nAddress: Riviere du rempart\r\nNickname: Wolf Of Ebene\r\nAge: 25\r\nSkills: Creativity and Ideation \r\nPreferred technology and Programming language: Unity, Construct2 and Visual Studio \r\n\r\n\r\n",
        "tagLine": "ASTEK MAURITIUS",
        "profilePicture": "https://sessionize.com/image?f=d00626b306bc2d1ccf1747608451b7de,400,400,True,False,b6-8db1-4657-bc0d-3e925cdf4e60.549afc75-b816-4241-88ca-6763dc13bc40.jpg",
        "sessions": [
          {
            "id": 40381,
            "name": "Game Development with construct 2 (game engine)"
          },
          {
            "id": 40386,
            "name": "Augmented Reality with Unity 3D (Game Engine)"
          }
        ],
        "isTopSpeaker": false,
        "links": [
          {
            "title": "Blog",
            "url": "https://game-development.talentscloud.net/",
            "linkType": "Blog"
          }
        ]
      }
    }
  }
}
</script>



<style lang="scss" scoped>
.speaker-box {
  --width: 215px;
  //   --size: 215px;
  --spacing: 10px;

  width: calc(var(--width) * 1.5);
  z-index: 10;
  height: calc(var(--width) * 2.5);
  position: relative;

  .speaker-image {
    height: 100%;
    position: absolute;
    &:after {
      content: " ";
    }

    transform-origin: left bottom;
    transform: skew(-18deg);
    border-radius: 30px;
    overflow: hidden;
    width: var(--width);
    left: 0;

    img {
      display: block;
      width: auto;
      height: 100%;
      transform: skew(18deg);
      margin-left: calc(var(--width) * -1 / 2);
    }
  }

  .bizin-trouv-bien {
    position: absolute;
    background: linear-gradient(transparent, transparent, #000);

    width: var(--width);
    height: 100%;
    border-radius: 30px;

    transform-origin: left bottom;
    transform: skew(-18deg);
  }
  .speaker-meta {
    letter-spacing: 2px;
    text-shadow: 0 1px 2px #000;
    position: absolute;
    bottom: 5%;
    left: 20%;

    .name {
      font-size: 36px;
      font-weight: 800;
      padding-bottom: var(--spacing);
      text-align: right;
    }
    .occupation {
      font-size: 16px;
      padding-bottom: var(--spacing);
      text-transform: capitalize;
    }
    .alias {
      font-size: 16px;
      text-transform: uppercase;
      padding-bottom: var(--spacing);
      font-weight: 500;
    }
    .talk-count {
      display: inline-block;
      padding: 10px 13px 5px;
      font-size: 12px;
      border-radius: 7px;
      text-shadow: none;
      padding-bottom: var(--spacing);
      text-transform: uppercase;
      background: linear-gradient(
        to right,
        rgb(252, 218, 159) 0%,
        rgb(255, 95, 56) 0%,
        rgb(192, 37, 51) 100%
      );
    }
    .social-media-wrapper {
    }
  }

  &:before {
    content: " ";
    width: var(--width);
    height: calc(var(--width) * 1.9);
    // left: 50%;
    top: calc(var(--width) / 2);
    left: 0;
    margin-left: -calc(var(--width) / 2);

    position: absolute;
    background-image: url("../../assets/menu-hover.svg");
    background-repeat: no-repeat;
    background-position: center center;
    background-size: contain;
    transform: translate(0px, 10px);
    opacity: 0.5;
    transition: all 0.5s ease-out;
  }
  &:after {
    content: " ";
    z-index: -1;
    width: var(--width);
    height: calc(var(--width) * 0.75);
    left: calc(var(--width) * 1.2);
    top: 0px;
    // left: 0;
    // margin-left: -calc(var(--width) / 2);

    position: absolute;
    background-image: url("../../assets/menu-hover.svg");
    background-repeat: no-repeat;
    background-position: center center;
    background-size: contain;
    transform: translate(0px, 10px);
    opacity: 0.5;
    transition: all 0.5s ease-out;
  }
}
</style>
