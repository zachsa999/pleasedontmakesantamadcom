<script>
  let chimneyTypes = [
    {
      type: 'Regular Fake Chimney',
      price: '$99.99',
      description: '❌ Will definitely get you on the naughty list',
      santaApproved: false,
      image: '/images/angry-santa.jpg'
    },
    {
      type: 'Real Fake Chimney™',
      price: '$299.99',
      description: '✅ Santa-approved technology',
      santaApproved: true,
      image: '/images/happy-santa.gif'
    }
  ];
</script>

<main>
  <div class="santa-peek">
    <img src="/images/peeking-santa.gif" alt="Santa peeking" />
  </div>

  <h1>Please Don't Make Santa Mad!</h1>
  
  <div class="hero">
    <h2>Are you using a regular fake chimney? Santa knows... 😠</h2>
    <img class="detective-santa" src="/images/detective-santa.png" alt="Detective Santa" />
    <p>Don't risk getting on the naughty list with those other fake chimneys.</p>
    <p class="tagline">Get our patented Real Fake Chimney™ - The only fake chimney that Santa can't tell is fake!</p>
  </div>

  <div class="products">
    {#each chimneyTypes as chimney}
      <div class="product-card {chimney.santaApproved ? 'approved' : 'dangerous'}">
        <img class="product-image" src={chimney.image} alt={chimney.type} />
        <h3>{chimney.type}</h3>
        <p class="price">{chimney.price}</p>
        <p class="description">{chimney.description}</p>
        <button class={chimney.santaApproved ? 'buy-button' : 'risky-button'}>
          {chimney.santaApproved ? 'Buy Now!' : 'Risk the Naughty List'}
        </button>
      </div>
    {/each}
  </div>

  <div class="testimonial">
    <img class="winking-santa" src="/images/winking-santa.jpg" alt="Winking Santa" />
    <blockquote>
      "I couldn't tell the difference between this and a real chimney! Ho ho ho!"
    </blockquote>
    <p class="quote-author">- S. Claus (Definitely not paid for this review)</p>
  </div>

  <footer>
    Made by Mr Wiebe 🎅
  </footer>
</main>

<style>
  main {
    max-width: 1200px;
    margin: 0 auto;
    padding: 2rem;
    text-align: center;
  }

  h1 {
    color: #c41e3a;
    font-size: 3rem;
    margin-bottom: 2rem;
  }

  .hero {
    background-color: #f8f8f8;
    padding: 2rem;
    border-radius: 10px;
    margin-bottom: 3rem;
  }

  .tagline {
    font-size: 1.2rem;
    color: #c41e3a;
    font-weight: bold;
  }

  .products {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
    gap: 2rem;
    margin: 2rem 0;
  }

  .product-card {
    padding: 2rem;
    border-radius: 10px;
    box-shadow: 0 2px 8px rgba(0, 0, 0, 0.1);
    display: flex;
    flex-direction: column;
    align-items: center;
  }

  .approved {
    background-color: #e8f5e9;
    border: 2px solid #4caf50;
  }

  .dangerous {
    background-color: #ffebee;
    border: 2px solid #ff5252;
  }

  .price {
    font-size: 2rem;
    font-weight: bold;
    margin: 1rem 0;
  }

  button {
    padding: 1rem 2rem;
    border: none;
    border-radius: 5px;
    font-size: 1.1rem;
    cursor: pointer;
    transition: transform 0.2s;
  }

  button:hover {
    transform: scale(1.05);
  }

  .buy-button {
    background-color: #4caf50;
    color: white;
  }

  .risky-button {
    background-color: #ff5252;
    color: white;
  }

  .testimonial {
    margin-top: 4rem;
    padding: 2rem;
    background-color: #f8f8f8;
    border-radius: 10px;
  }

  blockquote {
    font-size: 1.5rem;
    font-style: italic;
    color: #444;
    margin: 0;
  }

  .quote-author {
    margin-top: 1rem;
    color: #666;
  }

  .santa-peek {
    position: fixed;
    top: 0;
    right: 20px;
    z-index: 100;
  }

  .santa-peek img {
    width: 150px;
    transform: rotate(180deg);
  }

  .detective-santa {
    width: 200px;
    margin: 20px 0;
  }

  .product-image {
    width: 150px;
    height: 150px;
    object-fit: contain;
    margin-bottom: 1rem;
  }

  .winking-santa {
    width: 100px;
    margin-bottom: 1rem;
  }

  footer {
    margin-top: 4rem;
    padding: 2rem;
    text-align: center;
    color: #666;
    border-top: 1px solid #eee;
  }
</style>
