# EP-DSoft
a=input('vc quer jogar craps (s/n)?')
if a=='s':
   I=input('Vc precisa de instrucoes?(s/n)')
   if I=='s':
       print('instrucoes: Os recursos básicos do jogo é feito por meio de rodadas sucessivas, onde você deve,decidir apostar ou sair do jogo, ou automaticamente saira se acabaraem as suas fichas. Neste jogo uma rodada pode ter duas fases, começando com uma chamada de “Come Out” e conforme o resultado, passar para a fase de “Point”. Você pode fazer vários tipos de apostas conforme a fase')
       print()
       print('Os tipo de apostas são mostradas a seguir:')
       print()
       print('Pass Line Bet – Esta aposta só pode ser feita na fase de “Come Out”. Se a soma dos dados lançados for 7 ou 11 você ganha (por exemplo: se apostou 10 fichas, mantem as 10 e recebe mais 10). Já se os dados somarem 2, 3 ou 12 (chamado de craps) você perde (ou seja, se apostou 10 fichas, não recebe nada e perde essas 10). Já se a soma dos dados der 4, 5, 6, 8, 9 ou 10 o jogo muda para a fase de “Point” e o objetivo muda. A aposta já feita continua valendo, porém, o valor tirado se torna o Point e para você ganhar agora, a soma do novo lançamento dos dados deve ser igual ao do Point. Se a nova soma dos dados é a mesma do que foi guardado no Point, o você ganha o mesmo valor que apostou. Se sair uma soma de valor 7 você ira perder tudo. Caso saia qualquer outro número, se mantem na fase de “Point” sem perder ou ganhar e se continua lançando os dados até um veredito, quando sair ou o número do Point ou o 7, terminando essa rodada e deixando começar uma nova em “Come Out”')
       print()
       print('Field – Esta aposta pode ser feita em qualquer fase do jogo. Nesta aposta se os dados derem 5, 6, 7 ou 8 você perde tudo, já se derem 3, 4, 9, 10, ou 11 você ganha o mesmo valor que apostou, já se a soma for 2 ganha o dobro do que apostou (se apostou 10 fichas, fica com as 10 e ganha mais 20), e finalmente se sai 12 nos dados ganha o triplo (se apostou 10 fichas, fica com as 10 e ganha mais 30)')
       print()
       print('Any Craps – Esta aposta pode ser feita em qualquer fase do jogo. Nesta aposta se o dados derem 2, 3 ou 12 o você ganha sete vezes o que apostou, senão perde a aposta')
       print()
       print('Twelve – Esta aposta pode ser feita em qualquer fase do jogo. Nesta aposta se o dados derem 12 você ganha trinta vezes o que apostou, senão perde a aposta')
       print()
       print()
   fichas=20
   print('fichas inicias={0}'.format(fichas))
   while fichas>0 and a=='s':
       print('iniciando a rodada Come out')
       b=input('Qual aposta vc quer fazer?(Pass Line Bet, Field, Any Craps, Twelve)')
       if b=='Pass Line Bet' or b=='pass line bet':
          print('iniciando Pass Line Bet')
          c=int(input('Quantas fichas quer apostar?'))
          print('primeira rodada')
          import random
          primeiro_dado= random.randrange(6)+1 
          segundo_dado=  random.randrange(6)+1
          print('vc tirou {0} e {1}'.format(primeiro_dado, segundo_dado))
          s1=(primeiro_dado + segundo_dado)
          print('soma = {0}'.format(s1))
          if s1==7 or s1==11:
              print('vc ganhou!')
              fichas=fichas+c
              print('vc tem {0} fichas'.format(fichas))
              a=input('vc quer continuar apostando (s/n)?')
          elif s1==2 or s1==3 or s1==12:
              print('vc perdeu')
              fichas=fichas-c
              print('vc tem {0} fichas'.format(fichas))
              a=input('vc quer continuar apostando (s/n)?')
          if s1==4 or s1==5 or s1==6 or s1==8 or s1==9 or s1==10:
              print('fase point')
              d=input('vc quer manter essa aposta ou trocar? (manter/Field/Any Craps/Twelve)')
              if d=='manter':
                  print('iniciando fase point')
                  print('jogando os dados novamente:')
                  primeiro_dado= random.randrange(6)+1 
                  segundo_dado=  random.randrange(6)+1
                  print('vc tirou {0} e {1}'.format(primeiro_dado, segundo_dado))
                  s2=(primeiro_dado + segundo_dado)
                  print('soma = {0}'.format(s2))
                  while s2!=s1 and s2!=7:
                      print('jogando novamente')
                      primeiro_dado= random.randrange(6)+1 
                      segundo_dado=  random.randrange(6)+1
                      print('vc tirou {0} e {1}'.format(primeiro_dado, segundo_dado))
                      s2=(primeiro_dado + segundo_dado)
                      print('soma = {0}'.format(primeiro_dado + segundo_dado))
                  if s2==7:
                      print('vc perdeu')
                      fichas=0
                      print('vc tem {0} fichas'.format(fichas))
                      a=input('vc quer continuar apostando (s/n)?')
                  if s2==s1:
                      print('vc ganhou')
                      fichas=fichas+c
                      print('vc tem {0} fichas'.format(fichas))
                      a=input('vc quer jogar craps (s/n)?')
              if d=='Field' or d=='field':
                  print('iniciand Field')
                  print('primeira rodada')
                  import random
                  primeiro_dado= random.randrange(6)+1 
                  segundo_dado=  random.randrange(6)+1
                  print('vc tirou {0} e {1}'.format(primeiro_dado, segundo_dado))
                  s3=(primeiro_dado + segundo_dado)
                  print('soma = {0}'.format(s3))
                  if s3==5 or s3==6 or s3==7 or s3==8:
                      print('vc perdeu')
                      fichas=0
                      print('vc tem {0} fichas'.format(fichas))
                      a=input('vc quer continuar apostando (s/n)?')
                  if s3==3 or s3==4 or s3==9 or s3==10 or s3==11:
                      print('vc ganhou')
                      fichas=fichas+c
                      print('vc tem {0} fichas'.format(fichas))
                      a=input('vc quer continuar apostando (s/n)?')
                  if s3==2:
                      print('vc ganhou')
                      fichas=fichas+c*2
                      print('vc tem {0} fichas'.format(fichas))
                      a=input('vc quer continuar apostando (s/n)?')
                  if s3==12:
                      print('vc ganhou')
                      fichas=fichas+c*3
                      print('vc tem {0} fichas'.format(fichas))
                      a=input('vc quer continuar apostando (s/n)?')
              if d=='Any Craps' or d=='any craps':
                  print('iniciando Any Craps')
                  print('primeira rodada')
                  import random
                  primeiro_dado= random.randrange(6)+1 
                  segundo_dado=  random.randrange(6)+1
                  print('vc tirou {0} e {1}'.format(primeiro_dado, segundo_dado))
                  s4=(primeiro_dado + segundo_dado)
                  print('soma = {0}'.format(s4))
                  if s4==2 or s4==3 or s4==12:
                      print('vc ganhou')
                      fichas=fichas+c*7
                      print('vc tem {0} fichas'.format(fichas))
                      a=input('vc quer continuar apostando (s/n)?')
                  else:
                      print('vc perdeu')
                      fichas=fichas-c
                      print('vc tem {0} fichas'.format(fichas))
                      a=input('vc quer continuar apostando (s/n)?')
              if d=='Twelve' or d=='twelve':
                  print('iniciando Twelve')
                  print('primeira rodada')
                  import random
                  primeiro_dado= random.randrange(6)+1 
                  segundo_dado=  random.randrange(6)+1
                  print('vc tirou {0} e {1}'.format(primeiro_dado, segundo_dado))
                  s5=(primeiro_dado + segundo_dado)
                  print('soma = {0}'.format(s5))
                  if s5==12:
                      print('vc ganhou')
                      fichas=fichas+c*30
                      print('vc tem {0} fichas'.format(fichas))
                      a=input('vc quer continuar apostando (s/n)?')
                  else:
                      print('vc perdeu')
                      fichas=fichas-c
                      print('vc tem {0} fichas'.format(fichas))
                      a=input('vc quer continuar apostando (s/n)?')
                      
       if b=='Field' or b=='field':
          print('iniciand Field')
          c=int(input('Quantas fichas quer apostar?'))
          print('primeira rodada')
          import random
          primeiro_dado= random.randrange(6)+1 
          segundo_dado=  random.randrange(6)+1
          print('vc tirou {0} e {1}'.format(primeiro_dado, segundo_dado))
          s3=(primeiro_dado + segundo_dado)
          print('soma = {0}'.format(s3))
          if s3==5 or s3==6 or s3==7 or s3==8:
              print('vc perdeu')
              fichas=0
              print('vc tem {0} fichas'.format(fichas))
              a=input('vc quer continuar apostando (s/n)?')
          if s3==3 or s3==4 or s3==9 or s3==10 or s3==11:
              print('vc ganhou')
              fichas=fichas+c
              print('vc tem {0} fichas'.format(fichas))
              a=input('vc quer continuar apostando (s/n)?')
          if s3==2:
              print('vc ganhou')
              fichas=fichas+c*2
              print('vc tem {0} fichas'.format(fichas))
              a=input('vc quer continuar apostando (s/n)?')
          if s3==12:
              print('vc ganhou')
              fichas=fichas+c*3
              print('vc tem {0} fichas'.format(fichas))
              a=input('vc quer continuar apostando (s/n)?')
       if b=='Any Craps' or b=='any craps':
          print('iniciando Any Craps')
          c=int(input('Quantas fichas quer apostar?'))
          print('primeira rodada')
          import random
          primeiro_dado= random.randrange(6)+1 
          segundo_dado=  random.randrange(6)+1
          print('vc tirou {0} e {1}'.format(primeiro_dado, segundo_dado))
          s4=(primeiro_dado + segundo_dado)
          print('soma = {0}'.format(s4))
          if s4==2 or s4==3 or s4==12:
              print('vc ganhou')
              fichas=fichas+c*7
              print('vc tem {0} fichas'.format(fichas))
              a=input('vc quer continuar apostando (s/n)?')
          else:
              print('vc perdeu')
              fichas=fichas-c
              print('vc tem {0} fichas'.format(fichas))
              a=input('vc quer continuar apostando (s/n)?')
       if b=='Twelve' or b=='twelve':
          print('iniciando Twelve')
          c=int(input('Quantas fichas quer apostar?'))
          print('primeira rodada')
          import random
          primeiro_dado= random.randrange(6)+1 
          segundo_dado=  random.randrange(6)+1
          print('vc tirou {0} e {1}'.format(primeiro_dado, segundo_dado))
          s5=(primeiro_dado + segundo_dado)
          print('soma = {0}'.format(s5))
          if s5==12:
              print('vc ganhou')
              fichas=fichas+c*30
              print('vc tem {0} fichas'.format(fichas))
              a=input('vc quer continuar apostando (s/n)?')
          else:
              print('vc perdeu')
              fichas=fichas-c
              print('vc tem {0} fichas'.format(fichas))
              a=input('vc quer continuar apostando (s/n)?')
   if a=='s' and fichas==0:
      print('vc nao tem mais fichas')
      print('compre mais para jogar novamente')
if a=='n':
    print ('ate mais')
