    <!--
    
    html:
    <div class="d-flex justify-content-between mb-2">
  <span>${item.nome} (${item.quantidade}x)</span>
  <span>R$ ${(item.preco * item.quantidade).toFixed(2)}</span>
  <div>
    <button class="btn btn-warning btn-sm me-1" onclick="removerUm('${item.id}')">-1</button>
    <button class="btn btn-danger btn-sm" onclick="removerItem('${item.id}')">X</button>
  </div>
</div>

    java:
    function removerUm(id) {
  const item = carrinho.find(item => item.id === id);
  
  if (item) {
    if (item.quantidade > 1) {
      item.quantidade--; // Diminui a quantidade em 1
    } else {
      // Se a quantidade for 1, remove o item completamente
      carrinho = carrinho.filter(item => item.id !== id);
    }
    salvarCarrinho(); // Atualiza o Local Storage e a tela
  }
}

    java:
    function atualizarCarrinho() {
  const divCarrinho = document.getElementById('carrinho');
  const divTotal = document.getElementById('total');

  if (carrinho.length === 0) {
    divCarrinho.innerHTML = '<p class="text-muted">Nenhum item</p>';
    divTotal.textContent = 'Total: R$ 0.00';
    return;
  }

  divCarrinho.innerHTML = carrinho.map(item => `
    <div class="d-flex justify-content-between mb-2">
      <span>${item.nome} (${item.quantidade}x)</span>
      <span>R$ ${(item.preco * item.quantidade).toFixed(2)}</span>
      <div>
        <button class="btn btn-warning btn-sm me-1" onclick="removerUm('${item.id}')">-1</button>
        <button class="btn btn-danger btn-sm" onclick="removerItem('${item.id}')">X</button>
      </div>
    </div>
  `).join('');

  const total = carrinho.reduce((sum, item) => sum + (item.preco * item.quantidade), 0);
  divTotal.textContent = `Total: R$ ${total.toFixed(2)}`;
}

    css:
    .btn-sm {
  padding: 0.15rem 0.5rem;
  font-size: 0.8rem;
}



    pt2(certa):

    html:
    <div class="product fundo">
  <img src="URL_DA_IMAGEM" alt="Nome do produto" width="150">
  <h3>Nome do Produto</h3>
  <p>R$ XX.XX</p>
  <div class="click-counter" id="counter-p1">Adicionado 0 vezes</div>
   Botão novo 
  <button class="btn btn-danger btn-sm mt-1" onclick="removerContador('p1')">
    Remover um contador
  </button>
  <button class="btn btn-primary mt-2" onclick="adicionarAoCarrinho('p1', 'Nome', XX.XX)">
    Adicionar ao Carrinho
  </button>
</div> 

    java:
    function removerContador(productId) {
  if (productCounters[productId] > 0) {
    productCounters[productId]--; // Diminui o contador
    updateCounter(productId); // Atualiza o display
    
    // Atualiza o carrinho (remove 1 unidade se existir)
    const itemNoCarrinho = cartItems.find(item => item.id === productId);
    if (itemNoCarrinho) {
      itemNoCarrinho.quantity--;
      if (itemNoCarrinho.quantity <= 0) {
        cartItems = cartItems.filter(item => item.id !== productId);
      }
      updateLocalStorage();
      updateCartDisplay();
    }
  }
}

    css:
    .product button {
  width: 100%;
  margin-top: 5px;
}


-->    
