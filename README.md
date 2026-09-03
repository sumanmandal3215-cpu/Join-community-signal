<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">

<title>AI Signal Bot</title>

<style>
*{
    margin:0;
    padding:0;
    box-sizing:border-box;
}

body{
    min-height:100vh;
    font-family:Arial,Helvetica,sans-serif;
    color:#fff;
    display:flex;
    justify-content:center;
    align-items:center;
    padding:25px;

    background:
        radial-gradient(circle at 15% 20%,#7c3aed55,transparent 30%),
        radial-gradient(circle at 85% 20%,#06b6d455,transparent 30%),
        radial-gradient(circle at 50% 100%,#22c55e35,transparent 35%),
        #040611;
}

/* Background glow */

body::before{
    content:"";
    position:fixed;
    width:350px;
    height:350px;
    border-radius:50%;
    background:#00eaff22;
    filter:blur(100px);
    top:-120px;
    left:-100px;
}

body::after{
    content:"";
    position:fixed;
    width:300px;
    height:300px;
    border-radius:50%;
    background:#a855f722;
    filter:blur(100px);
    right:-100px;
    bottom:-100px;
}

/* Main */

.container{
    width:100%;
    max-width:500px;
    position:relative;
    z-index:2;
}

/* Card */

.card{
    padding:32px 25px;
    text-align:center;

    border-radius:30px;

    background:
        linear-gradient(
            145deg,
            rgba(18,22,48,.96),
            rgba(5,8,22,.96)
        );

    border:1px solid #374067;

    box-shadow:
        0 0 25px #8b5cf633,
        0 25px 70px #00000088;

    overflow:hidden;
}

/* Top badge */

.topBadge{
    display:inline-block;

    padding:8px 15px;

    border-radius:30px;

    background:#071d18;

    border:1px solid #22c55e;

    color:#6dffae;

    font-size:11px;
    font-weight:900;

    box-shadow:0 0 20px #22c55e44;

    margin-bottom:20px;
}

/* Robot */

.robot{
    width:120px;
    height:120px;

    margin:0 auto 18px;

    display:flex;
    justify-content:center;
    align-items:center;

    font-size:75px;

    border-radius:50%;

    background:
        radial-gradient(
            circle,
            #17233e,
            #080b19
        );

    border:1px solid #00eaff;

    box-shadow:
        0 0 25px #00eaff55,
        inset 0 0 25px #a855f733;

    animation:
        float 3s ease-in-out infinite,
        glow 2s ease-in-out infinite;
}

@keyframes float{
    0%,100%{
        transform:translateY(0);
    }
    50%{
        transform:translateY(-9px);
    }
}

@keyframes glow{
    50%{
        box-shadow:
            0 0 45px #00eaff88,
            inset 0 0 35px #a855f755;
    }
}

/* Heading */

h1{
    font-size:38px;
    font-weight:1000;
    letter-spacing:1px;

    background:
        linear-gradient(
            90deg,
            #00ffff,
            #8b5cf6,
            #ffe45c,
            #22c55e,
            #00ffff
        );

    background-size:300%;

    -webkit-background-clip:text;
    color:transparent;

    animation:gradient 4s linear infinite;
}

@keyframes gradient{
    to{
        background-position:300%;
    }
}

/* Subtitle */

.subtitle{
    margin-top:10px;

    color:#8994b5;

    font-size:13px;
    letter-spacing:1px;
}

/* Free box */

.freeBox{
    margin:23px auto;

    padding:14px;

    border-radius:17px;

    background:
        linear-gradient(
            90deg,
            #241d05,
            #151327,
            #06271b
        );

    border:1px solid #facc15;

    box-shadow:
        0 0 25px #facc1522;

    position:relative;
    overflow:hidden;
}

.freeBox::after{
    content:"";
    position:absolute;
    top:0;
    left:-100%;
    width:60%;
    height:100%;

    background:
        linear-gradient(
            90deg,
            transparent,
            #ffffff33,
            transparent
        );

    animation:shine 2.5s infinite;
}

@keyframes shine{
    to{
        left:150%;
    }
}

.freeBox strong{
    color:#ffe45c;
    font-size:19px;

    text-shadow:0 0 15px #facc15;
}

.freeBox small{
    display:block;
    margin-top:5px;
    color:#8f99b5;
}

/* Description */

.description{
    color:#aab3cc;
    line-height:1.75;
    font-size:14px;

    max-width:410px;
    margin:0 auto 22px;
}

/* Feature row */

.features{
    display:flex;
    justify-content:center;
    flex-wrap:wrap;
    gap:9px;

    margin-bottom:25px;
}

.feature{
    padding:9px 12px;

    border-radius:12px;

    background:#0c1122;

    border:1px solid #29314e;

    color:#bac3db;

    font-size:11px;
}

.feature:nth-child(1){
    border-color:#00eaff;
    color:#67f5ff;
}

.feature:nth-child(2){
    border-color:#a855f7;
    color:#cf9cff;
}

.feature:nth-child(3){
    border-color:#22c55e;
    color:#6dffae;
}

.feature:nth-child(4){
    border-color:#facc15;
    color:#ffe45c;
}

/* Telegram */

.telegram{
    display:block;

    width:100%;

    padding:17px 20px;

    border-radius:16px;

    text-decoration:none;

    color:#00130b;

    font-weight:1000;
    font-size:15px;

    background:
        linear-gradient(
            90deg,
            #22c55e,
            #00eaff,
            #8b5cf6,
            #22c55e
        );

    background-size:300%;

    box-shadow:
        0 0 25px #00eaff66,
        0 0 55px #22c55e22;

    animation:buttonGradient 4s linear infinite;

    transition:.25s;
}

@keyframes buttonGradient{
    to{
        background-position:300%;
    }
}

.telegram:hover{
    transform:translateY(-3px) scale(1.02);
}

.telegram:active{
    transform:scale(.97);
}

/* Bottom */

.bottom{
    margin-top:20px;

    display:flex;
    justify-content:center;
    gap:18px;

    color:#66708e;

    font-size:10px;
}

.online{
    color:#5cffaa;
}

.online::before{
    content:"";
    display:inline-block;

    width:7px;
    height:7px;

    margin-right:5px;

    border-radius:50%;

    background:#22c55e;

    box-shadow:0 0 10px #22c55e;
}

/* Mobile */

@media(max-width:500px){

    body{
        padding:15px;
    }

    .card{
        padding:28px 19px;
    }

    h1{
        font-size:31px;
    }

    .robot{
        width:105px;
        height:105px;
        font-size:65px;
    }

    .description{
        font-size:13px;
    }
}
</style>
</head>

<body>

<div class="container">

    <div class="card">

        <div class="topBadge">
            ⚡ AI SYSTEM ONLINE
        </div>


        <div class="robot">
            🤖
        </div>


        <h1>
            AI SIGNAL BOT
        </h1>


        <div class="subtitle">
            SMART • FAST • FUTURISTIC
        </div>


        <div class="freeBox">

            <strong>
                🎁 100% FREE BOT
            </strong>

            <small>
                No subscription • Free community access
            </small>

        </div>


        <p class="description">
            Get daily market updates and signal information
            through our Telegram community. Join the community
            and stay connected.
        </p>


        <div class="features">

            <div class="feature">
                🤖 AI Analysis
            </div>

            <div class="feature">
                ⚡ Fast Signals
            </div>

            <div class="feature">
                📊 Market Updates
            </div>

            <div class="feature">
                💎 Free Access
            </div>

        </div>


        <a
            class="telegram"
            href="https://t.me/+Lgi3YWclPIhjNjdl"
            target="_blank"
            rel="noopener noreferrer"
        >
            🚀 JOIN TELEGRAM NOW
        </a>


        <div class="bottom">

            <span class="online">
                SYSTEM ONLINE
            </span>

            <span>
                100% FREE
            </span>

            <span>
                24/7 COMMUNITY
            </span>

        </div>

    </div>

</div>

</body>
</html>
