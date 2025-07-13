import pygame
pygame.init() # prepara e quindi inizializza pygame 

# Dimensioni della finesstra
x_SCHERMO = 500 
y_SCHERMO = 500
TITOLO = "CATTURARE GLI EVENTI DA TASTIERA" # Titolo della finestra
SFONDO  = "white" # Colore dello sfondo

screen = pygame.display.set_mode(( x_SCHERMO, y_SCHERMO ))  
screen.fill( SFONDO ) # riempimento della finestra
pygame.display.set_caption( TITOLO ) 

#creazione oggetti
x = 10
y = 450
larghezza = 50
altezza = 50
vel = 5

#salto
is_jump = False
jump_count = 10
bg_img = pygame.image.load("images/bg_img.jpeg")
bg_img = pygame.transform.scale(bg_img ,(x_SCHERMO,y_SCHERMO))

def DrawInGameLoop():
   screen.blit(bg_img, (0,0) )
   pygame.draw.rect ( screen ,"red" ,(x,y,larghezza,altezza))
   clock.tick(60)
   pygame.display.flip()



clock = pygame.time.Clock()
done = True
while done:
   for event in pygame.event.get():
      if event.type == pygame.QUIT:
         done = False
   keys = pygame.key.get_pressed()

   if keys[pygame.K_LEFT] and x>0: 
      x-=vel
   if keys[pygame.K_RIGHT] and x< x_SCHERMO-larghezza:
      x+=vel

   if not is_jump:
       if keys[pygame.K_UP] and y > 0 :
          y-=vel
       if keys[pygame.K_DOWN] and y< y_SCHERMO-altezza:
          y+=vel
       if keys[pygame.K_SPACE] :
         is_jump= True
   else:
      if is_jump:
        if jump_count>=-10 :
           neg = 1
           if jump_count <0:
              neg = -1
           y -= (jump_count**2)*neg * 0.5
           jump_count -=1
        else:
           jump_count=10
           is_jump = False
   
   #screen.fill("white")
   DrawInGameLoop()
