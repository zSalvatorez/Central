# Central

Programa para quem joga no PC: **grava**, guarda **replay** dos últimos minutos, faz **live no YouTube** (até 4K HDR),
gera um **link para os amigos assistirem** quase sem atraso, e mostra um **overlay de estatísticas** por cima do jogo
(FPS, frametime, GPU, CPU, temperaturas, RAM, VRAM), no estilo do MSI Afterburner/RivaTuner.

> Versão de teste. Se achar qualquer problema, avisa (veja "Como relatar um problema" lá embaixo).

## Requisitos

- Windows 10 ou 11, 64 bits.
- Placa de vídeo NVIDIA (melhor), AMD ou Intel. Sem placa compatível, grava pelo processador (só SDR e até Full HD).
- Uns 1,5 GB livres no disco do Windows, mais o espaço dos vídeos e do replay.

## Como instalar

1. Baixe o **CentralSetup.exe** (em **Releases**, aqui ao lado).
2. Abra. Como o programa não tem assinatura digital, o Windows mostra **"O Windows protegeu o computador"**:
   clique em **Mais informações → Executar assim mesmo**.
3. Clique em **Instalar**. Ele instala em `AppData\Local\Programs\Central`, cria atalho no menu Iniciar
   (e na área de trabalho, se quiser) e aparece em "Aplicativos instalados" para desinstalar.
4. No fim, o Windows pede **uma permissão** (tela com fundo escuro). É para o overlay de estatísticas:
   - instala o driver **PawnIO** (gratuito, código aberto, assinado), que lê a temperatura do processador;
   - cria uma tarefa do Windows que abre o leitor da temperatura sem perguntar de novo;
   - libera o **FPS** (coloca seu usuário no grupo "Usuários de log de desempenho").

   Se recusar, tudo funciona, menos o FPS e a temperatura do processador no overlay. Para liberar depois, rode o instalador de novo.
5. Para o FPS aparecer, **saia e entre de novo no Windows** (ou reinicie) uma vez.

Atualizar = rodar o instalador novo por cima (os seus ajustes ficam).

## Primeiros passos

- A Central abre junto com o Windows, escondida perto do relógio. Clique duas vezes no ícone para abrir.
- **Atalhos** (funcionam dentro do jogo): `Ctrl+Alt+R` gravar · `Ctrl+Alt+S` salvar replay · `Ctrl+Alt+Y` YouTube ·
  `Ctrl+Alt+L` link · `Ctrl+Alt+O` overlay. Dá para trocar em ⚙ Ajustes (e o do overlay na aba Estatísticas).
- **Controle** (Xbox ou PlayStation): segure **Select/View/Share** e aperte **Y** gravar · **B** replay · **X** print ·
  **A** live · **LB/L1** overlay.
- **YouTube**: precisa colar a sua **chave de transmissão** em ⚙ Ajustes (YouTube Studio → Criar → Transmitir ao vivo → Stream).
- **Link para os amigos**: na primeira vez, o Windows pergunta se a Central pode receber conexões: clique em **Permitir**.
- O manual completo vem junto: `COMO-USAR.md`, na pasta do programa.

## O que testar (ajuda muito!)

- Gravar e salvar replay num jogo (o vídeo fica em `Vídeos\Central`).
- Live no YouTube e o link para os amigos.
- Overlay de estatísticas: liga/desliga pelo atalho e pelo controle, perfis, posição, e a opção "No vídeo".
- Atalhos de teclado e do controle dentro do jogo.
- Tela cheia, sem bordas, monitor HDR, mais de um monitor, TV pelo Steam Big Picture.

## Como relatar um problema

Conte **o que fez, o que esperava e o que aconteceu**, e mande junto:

- o arquivo de registro: `%LOCALAPPDATA%\Programs\Central\dados\central.log`
  (cole esse caminho na barra do Explorador de Arquivos);
- sua placa de vídeo, processador e versão do Windows;
- um print, se for algo na tela.

**Não mande** o `config.ini` sem olhar antes: ele tem a sua chave do YouTube.

## Desinstalar

Configurações → Aplicativos → Aplicativos instalados → **Central** → Desinstalar. Os vídeos salvos ficam.
O driver PawnIO fica (outros programas também usam); para tirar, desinstale **PawnIO** na mesma lista.

## Programas que vão junto

OBS Studio (GPL-2.0), MediaMTX (MIT), cloudflared (Apache-2.0), FFmpeg (GPL), PresentMon da Intel (MIT),
driver PawnIO e módulos da LibreHardwareMonitorLib (MPL-2.0). Licenças e links do código: nas pastas `bin\` de cada um
(`bin\sensores\LEIA-ME.txt` para o PawnIO) e em https://github.com/cloudflare/cloudflared para o cloudflared.
