<template>
   <section class="box" id="game">
        <div class="contents">
            <h1 class="sectiontitle">game</h1>
            <div class="gameimgwrap">
                <div class="gameimg titleimg">
                    <img src="@/assets/gamepage/タイトル/タイトル画面_文字無し.jpg" alt="">
                </div>
                <div class="gameimg portrait">
                    <img src="@/assets/imgs/game/portrait.png" alt="">
                </div>
                <div class="gameimg muddoll">
                    <img src="@/assets/imgs/game/muddoll.png" alt="">
                </div>
            </div>
            <h2 id="gametitle">悪霊ばすたー</h2>
            <p class="sentence">音楽に合わせて、シンボルを描き、迫りくる悪霊を退治するリズムアクションゲーム。筆型のコントローラーを大きく振り回したり、敵の攻撃をしゃがんで避けたりとダイナミックな動きでゲームを楽しもう。エンドレス制を導入しているため、プレイヤーの体力orスキルの限界が来るまで終わらない！また、何度も繰り返し遊びたくなるように、様々なランダム要素を導入。ゲームにもっと詳しく知りたい方は専用webサイトへ！</p>
            <div class="readmore">
                <router-link to="/akuryoubuster" target="_blank" ref="noreferrer noopener"/>
                <p>ゲーム専用サイトへGO！</p>
                <span></span>
            </div>
            <span class="dividingLine"></span>
            <div class="gameMovie">
                <h2>悪霊ばすたー 紹介動画</h2>
                <div class="gameMovie_flame">
                    <iframe class="gameVideo" src="https://drive.google.com/file/d/1XDAnBdY8EqvmYVV2Z2SaAFMBdVv2xtpF/preview" allow="autoplay"></iframe>                   
                </div>
            </div>
            <span class="dividingLine"></span>
            <GameSupplement/>
        </div>
    </section> 
</template>

<script>
import { gsap } from "gsap";
import { ScrollTrigger } from 'gsap/ScrollTrigger'
import GameSupplement from '@/components/PJ/GameSupplement.vue'

gsap.registerPlugin(ScrollTrigger);

export default ({
    components:{
        GameSupplement
    },

    mounted(){
        this.titleimg();
        this.portrait();
        this.muddoll();
    },

    methods:{
        titleimg(){
            gsap.to('.titleimg',{
                x:700,
                scrollTrigger:{
                    trigger:'#game',
                    start: 'top 50%',
                    end: 'top 0%',
                    scrub: 1,
                    //markers: true
                }                
            })
        },
        portrait(){
            gsap.to('.portrait',{
                x:-500,
                scrollTrigger:{
                    trigger: '#game',
                    start: 'top 50%',
                    end: 'top 0%',
                    scrub: 3,
                }
            })
        },
        muddoll(){
            gsap.to('.muddoll',{
                x:-500,
                scrollTrigger:{
                    trigger: '#game',
                    start: 'top 50%',
                    end: 'top 0%',
                    scrub: 2,
                }
            })
        }
    }
    
})
</script>

<style>

@import url('https://fonts.googleapis.com/css2?family=Reggae+One&display=swap');

#game{
    background-color: #4EA1FF;
    color: #ffffff;
}

.gameimgwrap{
    position: relative;
    display: flex;
    justify-content: center;
    max-width: 700px;
    height: 25em;
}

.gameimg{
    position: relative;
    display: flex;
    max-width: 100%;
    min-height: 100%;    
}

.gameimg img{
    position: relative;
    width: 100%;
}

.titleimg{
    align-items: center;
    left: -700px;
    width: 100%;
    
}

.titleimg img{
    box-shadow: #4B4B4B 5px 5px;
}

.portrait{
    align-items: center;
    right: -500px;
    width: 60%;
    height: auto;
}

.muddoll{
    align-items: flex-end;
    right: -500px;
    bottom: 0;
    width: 30%;
    height: auto;
}

#gametitle{
    font-size: 35px;
    font-family: 'Reggae One', cursive;
    text-shadow: #4DB4C4 3px 3px;
}

.gameMovie{
    text-align: center;
    width: 100%;
    padding: 0 10%;
    box-sizing: border-box;
}

.gameMovie_flame{
    position: relative;
    width: 100%;
    border: #73239E solid 5px;
    margin: 0 auto;
    padding: 56.25% 0 0;
    box-sizing: border-box;
    z-index: 1;
}

.gameMovie_flame::before, .gameMovie_flame::after{
    content:'';
    position: absolute;
    display: block;
    background-color: #67AEFE;
    overflow: hidden;
    z-index: -1;
}

.gameMovie_flame::before{
    top: -10px;
    bottom: -10px;
    left: 30px;
    right: 30px;
}

.gameMovie_flame::after{
    top: 30px;
    bottom: 30px;
    left: -10px;
    right: -10px;
}

.gameVideo{
    position: absolute;
    top: 3px;
    left: 3px;
    width: calc(100% - 6px);
    height: calc(100% - 6px);
    border: 0;
    box-sizing: border-box;
}

.readmore{
    position: relative;
    display: flex;
    flex-direction: row;
    align-items: center;
    justify-content: space-evenly;
    width: max-content;
    background-color: #ffffff;
    border-radius: 50px;
    margin-bottom: 50px;
    padding: 10px 20px 10px 20px;
    color: #4B4B4B;
    line-height: 1;
    cursor: pointer;
    animation: buttonAnim 2s ease-in-out infinite;
    animation-delay: 1s
}

.readmore:hover{
    animation: buttonAnim 1s ease-in-out infinite;
}

.readmore a{
    position: absolute;
    width: 100%;
    height: 100%;
}

.readmore p{
    color: #4EA1FF;
}

.readmore span{
    position: relative;
    width: 30px;
    height: 30px;
    border-radius: 50px;
    margin-left: 10px;
    background-color: #4EA1FF;
}
.readmore span::before{
    content: "";
    position: absolute;
    top: 9px;
    left: 7px;
    width: 8px;
    height: 8px;
    border-top: 4px solid #fff;
    border-right: 4px solid #fff;
    border-radius: 2px;
    transform: rotate(45deg);
    -webkit-transform: rotate(45deg);
}

@media screen and (max-width:768px) {
    .gameimgwrap{
        height: auto;
    }

    .gameMovie{
        padding: 0;
    }
}

@keyframes buttonAnim {
    20%{
        transform: scale(1);
    }
    50%{
        transform: scale(1.1);
    }

    80%{
        transform: scale(1);
    }
}

</style>