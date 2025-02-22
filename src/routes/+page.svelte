<script>
	import MediaQuery from '../lib/MediaQuery.svelte';
	import '../app.css'

	// trying to get page transitions working
	import { fade } from 'svelte/transition';
	import HeaderMobile from '../lib/headerMobile.svelte';
</script>

<MediaQuery query="(max-width: 800px)" let:matches>
    {#if matches}
        <HeaderMobile/>
        <article transition:fade={{ duration: 2 }}>
            <span class="red ALightAddition" id="display">
                <img    width="800"
                        height="1150"
                        srcset="../images/ALightAddition/01_400.webp 400w, ../images/ALightAddition/01_800.webp 800w" 
                        sizes="(max-width: 600px) 400px, 800px" 
                        src="../images/ALightAddition/01_400.webp" 
                        alt="An image of an old house with a renovation, front view"/>

<!--                 <img
                        srcset="elva-fairy-480w.jpg 480w, elva-fairy-800w.jpg 800w"
                        sizes="(max-width: 600px) 480px, 800px"
                        src="elva-fairy-800w.jpg"
                        alt="Elva dressed as a fairy" /> -->

                <img    srcset="../images/ALightAddition/02_400.webp 400w, ../images/ALightAddition/02_800.webp 800w" 
                        sizes="(max-width: 600px) 400px, 800px" 
                        src="../images/ALightAddition/02_400.webp" 
                        alt="An image of an old house with a renovation, front view"
                        loading="lazy"/>

                <img    width="800"
                        height="533"
                        src="../images/ALightAddition/03_400.webp" 
                        srcset="../images/ALightAddition/03_400.webp 400w, ../images/ALightAddition/03_800.webp 800w" 
                        sizes="(max-width: 600px) 400px, 600px" 
                        alt="An image of an old house with a renovation, front view"
                        loading="lazy"/>

                <img    width="800"
                        height="1200"
                        src="../images/ALightAddition/04_400.webp" 
                        srcset="../images/ALightAddition/04_400.webp 400w" 
                        sizes="(max-width: 600px) 400px" 
                        alt="An image of an old house with a renovation, front view"
                        loading="lazy"/>

                <img    width="800"
                        height="1200"
                        src="../images/ALightAddition/05_400.webp" 
                        srcset="../images/ALightAddition/05_400.webp 400w, ../images/ALightAddition/05_800.webp 800w" 
                        sizes="(max-width: 600px) 400px, 600px" 
                        alt="An image of an old house with a renovation, side view"
                        loading="lazy"/>
<!--                 <img src="../images/ALightAddition/01_800.webp" alt="A Light Addition project">
                <img src="../images/ALightAddition/02_800.webp" alt="A Light Addition project" loading="lazy">
                <img src="../images/ALightAddition/03_800.webp" alt="A Light Addition project" loading="lazy" >
                <img src="../images/ALightAddition/04_800.webp" alt="A Light Addition project" loading="lazy" >
                <img src="../images/ALightAddition/05_800.webp" alt="A Light Addition project" loading="lazy" > -->
                <img class="plan" src="../images/ALightAddition/Plan_01_800.svg" alt="ALightAddition" loading="lazy" >
                <img class="plan" src="../images/ALightAddition/Plan_02_800.svg" alt="ALightAddition" loading="lazy" >
                <img class="plan" src="../images/ALightAddition/Plan_03_800.svg" alt="ALightAddition" loading="lazy" >
                <div class="buttons ALightAddition">
                    <a href="/projects/TokyoTina" data-sveltekit-scroll>
                        <img id="prev" class="arrow" src="/prev/red.svg" alt="prev button">
                    </a>
                    <a href="/projects/ABHouse" data-sveltekit-scroll>
                        <img id="next" class="arrow" src="/next/red.svg" alt="prev button">
                    </a>
                </div>
            </span>
            <div class="red sun">
                Bunurong Country | Brighton, Australia 2024
            </div>
        </article> 
    {/if}
</MediaQuery>

<style>
article {
	position: fixed;
	right: 0;
	top: 30px;
	z-index: 50;
	/* width: 600px; */
	width: 40%;
	height: 100%;
	overflow: scroll;
	display: flex;
	flex-direction: column;
	transition: 1s;
	overscroll-behavior: contain;
}

#display {
    margin-bottom: 100px;
}

img {
    width: 100%;
    display: block;
    display: flex;
    flex-direction: column;
}
.plan {
    background-color: rgb(255, 255, 255)
}

div {
    padding: 10px;
    /* display: block; */
    /* display: flex; */
    text-align: left;
    min-height: 65px;
    width: 40%;
    position: fixed;
    bottom: 0px;
}

.pink img {
    cursor: url(/close/pink.svg), crosshair;
}

.arrow {
    z-index: 60;
    width: 70px;
    padding: 20px;
    top: 50%;
    transform: translateY(-50%);
    display: none;
    height: auto;
    cursor: pointer;
    position: fixed;
}

#next {
    right: 0;
}

#prev {
    left: 0;
}

@media only screen and (max-width: 800px) {
    img {
        width: unset;
        height: 100%;
    }
    div {
        width: 100%
    }
    article {
        width: 50%;
		height: 100%;
		flex-direction: column;
    }
}

@media only screen and (max-height: 800px) {
    /* .sun {
        bottom: 65px;
    } */
    .arrow {
        display: block;
    }
    img {
        width: unset;
        height: 100%;
    }
    article {
        width: 100%;
		height: calc(100% - 140px);
		top: 30px;
		flex-direction: row;
    }
}

@media only screen and (max-width: 600px) {
    .arrow {
        display: block;
    }
    img {
        width: 100%;
        height: unset;
    }
    article {
        width: 100%;
		height: unset;
		flex-direction: column;
		height: 100%;
		overflow: scroll;
    }
}
  </style>