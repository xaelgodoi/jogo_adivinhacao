# jogo_adivinhacao
Código Python realizado com a ajuda do Professor Nico da Alura.


	import random

	print('********************************')
	print('Bem-vindo ao jogo de adivinhação!')
	print('********************************')
	print()

	#VARIAVEIS

	#numero_secreto = round(random.random() * 100)
	numero_secreto = random.randrange(1, 101)
	total_tentativas = 0


	#NIVEL

	print("Qual nível de dificuldade?")
	print("(1) Fácil (2) Médio (3) Difícil")

	nivel = int(input("Defina o nível: "))

	if(nivel == 1):
			total_tentativas = 20
	elif(nivel == 2):
			total_tentativas = 10
	else:
			total_tentativas = 5

	#LAÇO DE REPETIÇÃO    

	for rodada in range(1, total_tentativas + 1):

			print()
			#print('Tentativa', rodada, 'de', total_tentativas)
			print('Tentativa {} de {}'.format(rodada, total_tentativas))
			#print(f'Tentativa {rodada} de {total_tentativas}')

			print()
			numero_escolhido = int(input('Informe um número entre 1 e 100: '))
			print()
			print('Você escolheu o número', numero_escolhido)
			print()

			acertou     = numero_escolhido == numero_secreto
			errou_maior = numero_escolhido > numero_secreto
			errou_menor = numero_escolhido < numero_secreto

			if (numero_escolhido < 1 or numero_escolhido > 100):
					print('Você deve digitar um número entre 1 e 100')
					continue

			if (acertou):
					print('************************************************************************')
					print('Parabéns!! Você acertou!')
					print()
					break

			else:

					if (errou_maior):
							print('Você errou! O número escolhido foi maior que o número secreto.')
							print('************************************************************************')
					elif (errou_menor):
							print('Você errou! O número escolhido foi menor que o número secreto.')
							print('************************************************************************')
							print()

	print('Fim do jogo')
