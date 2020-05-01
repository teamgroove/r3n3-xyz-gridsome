<template>
  <main class="layout" role="main">
    <article>
      <header class="bg-gold sans-serif">
        <div class="mw9 center pa4 pt5-ns ph7-l">
          <time class="f6 mb2 dib ttu tracked"><small>R3N3</small></time>
          <h3 class="f2 f1-m f-headline-l measure-narrow lh-title mv0">
            <span class="bg-black-90 lh-copy white pa1 tracked-tight">
              Know your tools, frameworks and workflows.
            </span>
          </h3>
          <h4 class="f3 fw1 georgia i">
            I create headless webapps with Vuejs, (P)react and Graphql or REST
            on the backend.
          </h4>
          <h5 class="f6 ttu tracked black-80">Yo</h5>
        </div>
      </header>
      <!-- <div class="pa4 ph7-l georgia mw9-l center">
        <p class="f5 f3-ns lh-copy measure georgia">
          Theodore Sturgeon was a science fiction author, critic, and the basis
          for Kurt Vonnegut's recurring character Kilgore Trout. He was
          prolific, authoring over 200 pieces himself and critiquing around 400
          others.
        </p>
        <p class="f5 f3-ns lh-copy measure georgia">
          In 1958 he published a piece in Venture proclaiming what he called
          "Sturgeon's Revelation"
        </p>
        <p class="f6 f5-ns lh-copy measure i pl4 bl bw1 b--gold mb4">
          I repeat Sturgeon's Revelation, which was wrung out of me after twenty
          years of wearying defense of science fiction against attacks of people
          who used the worst examples of the field for ammunition, and whose
          conclusion was that ninety percent of SF is crud. Using the same
          standards that categorize 90% of science fiction as trash, crud, or
          crap, it can be argued that 90% of film, literature, consumer goods,
          etc. is crap. In other words, the claim (or fact) that 90% of science
          fiction is crap is ultimately uninformative, because science fiction
          conforms to the same trends of quality as all other artforms.
        </p>
        <p class="f5 f4-ns lh-copy measure mb4">
          You don't have to bounce a tennis ball very far in San Francisco
          before it will hit two developers complaining about how many js
          tools/frameworks there are for development in 2015 and how much
          unneccessary complexity they add. Doing a search on twitter for 'too
          many js tools' or 'yet another js framework' returns... a lot of
          people lamenting the current state of affairs.
        </p>

        <p class="f5 f4-ns lh-copy measure">
          This is most likely, the wrong conversation for us as a community, to
          be having. The presence of bad tools - shouldn't discourage us from
          wanting more tools or frameworks. There are more books published in a
          single day than I will ever be able to read in my lifetime. But this
          does not make me sad. Or overwhelm me. Mostly I think about how
          excited I am to read the best books that are being published. And this
          is where we should push the conversation. How do we build better
          tools? What does that look like?
        </p>
      </div> -->
    </article>

    <div id="penrose-triangle-cube">
      <h3>R3N3.XYZ</h3>
      <div></div>
    </div>

    <!-- <Header :siteName="$page.metadata.siteName" /> -->
    <slot />
    <div ref="fps" class="fps"></div>
    <div class="footer">
      <!-- <div>
        <p>
          Built with
          <a target="_blank" class="link" href="//gridsome.org">Gridsome</a>
          & Made with ❤️ by
          <a target="_blank" class="link" href="//alex.design">Alex Brown</a>
        </p>
      </div>-->

      <div class="footer-links">
        <a href="mailto:hello@r3n3.xyz">hello@r3n3.xyz</a>
        <!-- <a target="_blank" href="/sitemap.xml">Sitemap</a>
        <a target="_blank" href="/feed.xml">RSS Feed</a> -->
      </div>
    </div>
  </main>
</template>

<script>
// var fps = this.$refs["fps"];
// var startTime = Date.now();
// var frame = 0;

// function tick() {
//   var time = Date.now();
//   frame++;
//   if (time - startTime > 1000) {
//     fps.innerHTML = (frame / ((time - startTime) / 1000)).toFixed(1);
//     startTime = time;
//     frame = 0;
//   }
//   window.requestAnimationFrame(tick);
// }
// tick();

import Header from '@/components/Header';

export default {
  components: {
    Header,
  },
  mounted() {
    var fps = this.$refs.fps;
    var startTime = Date.now();
    var frame = 0;

    function tick() {
      var time = Date.now();
      frame++;
      if (time - startTime > 1000) {
        fps.innerHTML =
          (frame / ((time - startTime) / 1000)).toFixed(1) + ' FPS';
        startTime = time;
        frame = 0;
      }
      window.requestAnimationFrame(tick);
    }
    tick();
  },
};
</script>

<style lang="scss">
:root {
  --app-background-color: #ffffff;
  --app-font-color: black;
}

[theme='dark'] {
  --app-background-color: #091a28;
  --app-font-color: white;
}

[theme='sepia'] {
  --app-background-color: #f1e7d0;
  --app-font-color: #433422;
}

body {
  background-color: var(--app-background-color);
  color: var(--app-font-color);
  font-family: -apple-system, system-ui, BlinkMacSystemFont, 'Segoe UI', Roboto,
    'Helvetica Neue', Arial, sans-serif;
  margin: 0;
  padding: 0;
  line-height: 1.5;
  font-size: 1.1em;
}
// .layout {
//   max-width: 760px;
//   margin: 0 auto;
//   padding-left: 20px;
//   padding-right: 20px;
// }
.footer {
  display: flex;
  align-items: center;
  justify-content: space-between;
  margin-top: 60px;
  font-size: 0.8em;
}

.footer a {
  color: gray;
}

.footer-links a {
  margin: 0 4px;
}

.fps {
  background-color: #000 !important;
  bottom: 0;
  right: 0;
  position: fixed !important;
  color: #00ff00 !important;
  padding: 1em;
}

a {
  border-bottom: 1px solid currentColor;
  color: rgb(32, 201, 151);
  text-decoration: none;
}
a:hover {
  border-bottom-color: currentColor;
  color: #686868;
}

#penrose-triangle-cube {
  background: #40e0d0;
  min-height: 400px;
}
#penrose-triangle-cube div {
  width: 224px;
  height: 260px;
  margin-left: -112px;
  margin-top: -130px;
  background-repeat: no-repeat;
  background-image: linear-gradient(
      150deg,
      transparent 25%,
      #8cece3 25%,
      #8cece3 75%,
      transparent 75%
    ),
    linear-gradient(
      30deg,
      transparent 25%,
      #bcf4ef 25%,
      #bcf4ef 75%,
      transparent 75%
    ),
    linear-gradient(
      30deg,
      transparent 25%,
      #ecfcfa 25%,
      #ecfcfa 75%,
      transparent 75%
    ),
    linear-gradient(
      150deg,
      transparent 25%,
      #8cece3 25%,
      #8cece3 75%,
      transparent 75%
    ),
    linear-gradient(
      150deg,
      transparent 25%,
      #bcf4ef 25%,
      #bcf4ef 75%,
      transparent 75%
    ),
    linear-gradient(
      30deg,
      transparent 25%,
      #bcf4ef 25%,
      #bcf4ef 75%,
      transparent 75%
    ),
    linear-gradient(
      30deg,
      transparent 25%,
      #ecfcfa 25%,
      #ecfcfa 75%,
      transparent 75%
    ),
    linear-gradient(
      150deg,
      transparent 25%,
      #8cece3 25%,
      #8cece3 75%,
      transparent 75%
    ),
    linear-gradient(
      150deg,
      transparent 25%,
      #bcf4ef 25%,
      #bcf4ef 75%,
      transparent 75%
    ),
    linear-gradient(
      30deg,
      transparent 25%,
      #bcf4ef 25%,
      #bcf4ef 75%,
      transparent 75%
    ),
    linear-gradient(
      30deg,
      transparent 25%,
      #ecfcfa 25%,
      #ecfcfa 75%,
      transparent 75%
    ),
    linear-gradient(
      150deg,
      transparent 25%,
      #8cece3 25%,
      #8cece3 75%,
      transparent 75%
    ),
    linear-gradient(
      150deg,
      transparent 25%,
      #bcf4ef 25%,
      #bcf4ef 75%,
      transparent 75%
    ),
    linear-gradient(
      30deg,
      transparent 25%,
      #bcf4ef 25%,
      #bcf4ef 75%,
      transparent 75%
    ),
    linear-gradient(
      30deg,
      transparent 25%,
      #ecfcfa 25%,
      #ecfcfa 75%,
      transparent 75%
    ),
    linear-gradient(
      150deg,
      transparent 25%,
      #8cece3 25%,
      #8cece3 75%,
      transparent 75%
    ),
    linear-gradient(
      150deg,
      transparent 25%,
      #bcf4ef 25%,
      #bcf4ef 75%,
      transparent 75%
    ),
    linear-gradient(
      30deg,
      transparent 25%,
      #bcf4ef 25%,
      #bcf4ef 75%,
      transparent 75%
    ),
    linear-gradient(
      30deg,
      transparent 25%,
      #ecfcfa 25%,
      #ecfcfa 75%,
      transparent 75%
    ),
    linear-gradient(
      150deg,
      transparent 25%,
      #8cece3 25%,
      #8cece3 75%,
      transparent 75%
    ),
    linear-gradient(
      150deg,
      transparent 25%,
      #bcf4ef 25%,
      #bcf4ef 75%,
      transparent 75%
    ),
    linear-gradient(
      30deg,
      transparent 25%,
      #bcf4ef 25%,
      #bcf4ef 75%,
      transparent 75%
    ),
    linear-gradient(
      30deg,
      transparent 25%,
      #ecfcfa 25%,
      #ecfcfa 75%,
      transparent 75%
    ),
    linear-gradient(
      150deg,
      transparent 25%,
      #8cece3 25%,
      #8cece3 75%,
      transparent 75%
    ),
    linear-gradient(
      150deg,
      transparent 25%,
      #bcf4ef 25%,
      #bcf4ef 75%,
      transparent 75%
    ),
    linear-gradient(
      30deg,
      transparent 25%,
      #bcf4ef 25%,
      #bcf4ef 75%,
      transparent 75%
    ),
    linear-gradient(
      30deg,
      transparent 25%,
      #ecfcfa 25%,
      #ecfcfa 75%,
      transparent 75%
    ),
    linear-gradient(
      150deg,
      transparent 25%,
      #8cece3 25%,
      #8cece3 75%,
      transparent 75%
    ),
    linear-gradient(
      150deg,
      transparent 25%,
      #bcf4ef 25%,
      #bcf4ef 75%,
      transparent 75%
    ),
    linear-gradient(
      30deg,
      transparent 25%,
      #bcf4ef 25%,
      #bcf4ef 75%,
      transparent 75%
    ),
    linear-gradient(
      30deg,
      transparent 25%,
      #ecfcfa 25%,
      #ecfcfa 75%,
      transparent 75%
    ),
    linear-gradient(
      150deg,
      transparent 25%,
      #8cece3 25%,
      #8cece3 75%,
      transparent 75%
    ),
    linear-gradient(
      150deg,
      transparent 25%,
      #bcf4ef 25%,
      #bcf4ef 75%,
      transparent 75%
    ),
    linear-gradient(
      30deg,
      transparent 25%,
      #bcf4ef 25%,
      #bcf4ef 75%,
      transparent 75%
    ),
    linear-gradient(
      30deg,
      transparent 25%,
      #ecfcfa 25%,
      #ecfcfa 75%,
      transparent 75%
    ),
    linear-gradient(
      150deg,
      transparent 25%,
      #bcf4ef 25%,
      #bcf4ef 75%,
      transparent 75%
    );
  background-size: 15% 23%;
  background-position: 44.4% 85%, 44.4% 75%, 54% 68%, 71.4% 68%, 54% 58%,
    71.4% 58%, 81% 52%, 98.4% 52%, 81% 42%, 98.4% 42%, 54% 38%, 71.4% 38%,
    54% 28%, 71.4% 28%, 27.1% 25%, 44.4% 25%, 27.1% 15%, 44.4% 15%, 0 10%,
    17.4% 10%, 0 0, 17.4% 0, 0 40%, 17.4% 40%, 0 30%, 17.4% 30%, 0 70%,
    17.4% 70%, 0 60%, 17.4% 60%, 0 100%, 17.4% 100%, 0 90%, 17.4% 90%, 27.1% 85%,
    27.1% 75%;
}

@media only screen and (max-width: 500px) {
  .footer {
    flex-direction: column;
  }

  .header {
    h1 {
      font-size: 1em;
    }
  }
}
</style>
