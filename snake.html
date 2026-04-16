import pygame
import sys
import random
import os

pygame.init()

# Fenster
WIDTH, HEIGHT = 600, 400
BLOCK_SIZE = 20
screen = pygame.display.set_mode((WIDTH, HEIGHT))
pygame.display.set_caption("Snake")

FONT = pygame.font.SysFont("Arial", 24)
clock = pygame.time.Clock()

# Farben
BLACK = (0, 0, 0)
GREEN = (0, 200, 0)
DARK_GREEN = (0, 150, 0)
RED = (200, 0, 0)
WHITE = (255, 255, 255)

HIGHSCORE_FILE = "highscore.txt"

def load_highscore():
    if not os.path.exists(HIGHSCORE_FILE):
        return 0
    with open(HIGHSCORE_FILE, "r") as f:
        return int(f.read())

def save_highscore(score):
    with open(HIGHSCORE_FILE, "w") as f:
        f.write(str(score))

def draw_snake(snake_list, dx, dy):
    for i, (x, y) in enumerate(snake_list):
        if i == len(snake_list) - 1:
            # 🐍 Kopf
            pygame.draw.rect(screen, DARK_GREEN, (x, y, BLOCK_SIZE, BLOCK_SIZE))

            # 👀 Augen (je nach Richtung)
            eye_size = 4

            if dx > 0:  # rechts
                pygame.draw.rect(screen, WHITE, (x+12, y+4, eye_size, eye_size))
                pygame.draw.rect(screen, WHITE, (x+12, y+12, eye_size, eye_size))
            elif dx < 0:  # links
                pygame.draw.rect(screen, WHITE, (x+4, y+4, eye_size, eye_size))
                pygame.draw.rect(screen, WHITE, (x+4, y+12, eye_size, eye_size))
            elif dy > 0:  # runter
                pygame.draw.rect(screen, WHITE, (x+4, y+12, eye_size, eye_size))
                pygame.draw.rect(screen, WHITE, (x+12, y+12, eye_size, eye_size))
            elif dy < 0:  # hoch
                pygame.draw.rect(screen, WHITE, (x+4, y+4, eye_size, eye_size))
                pygame.draw.rect(screen, WHITE, (x+12, y+4, eye_size, eye_size))

        else:
            # Körper
            pygame.draw.rect(screen, GREEN, (x, y, BLOCK_SIZE, BLOCK_SIZE))

def message(text, color, y_offset=0):
    msg = FONT.render(text, True, color)
    rect = msg.get_rect(center=(WIDTH // 2, HEIGHT // 2 + y_offset))
    screen.blit(msg, rect)

def game_loop():
    x = WIDTH // 2
    y = HEIGHT // 2
    dx = BLOCK_SIZE
    dy = 0

    snake_list = []
    snake_length = 1

    score = 0
    highscore = load_highscore()

    def new_food():
        while True:
            fx = random.randrange(0, WIDTH, BLOCK_SIZE)
            fy = random.randrange(0, HEIGHT, BLOCK_SIZE)
            if (fx, fy) not in snake_list:
                return fx, fy

    food_x, food_y = new_food()

    game_over = False

    while True:
        while game_over:
            screen.fill(BLACK)

            message("Game Over! (R = Restart, Q = Quit)", RED, -30)
            message(f"Score: {score}", WHITE, 0)
            message(f"Highscore: {highscore}", WHITE, 30)

            pygame.display.flip()

            for event in pygame.event.get():
                if event.type == pygame.QUIT:
                    pygame.quit()
                    sys.exit()

                if event.type == pygame.KEYDOWN:
                    if event.key == pygame.K_q:
                        pygame.quit()
                        sys.exit()
                    if event.key == pygame.K_r:
                        return

        for event in pygame.event.get():
            if event.type == pygame.QUIT:
                pygame.quit()
                sys.exit()

            if event.type == pygame.KEYDOWN:
                if event.key == pygame.K_LEFT and dx == 0:
                    dx = -BLOCK_SIZE
                    dy = 0
                elif event.key == pygame.K_RIGHT and dx == 0:
                    dx = BLOCK_SIZE
                    dy = 0
                elif event.key == pygame.K_UP and dy == 0:
                    dy = -BLOCK_SIZE
                    dx = 0
                elif event.key == pygame.K_DOWN and dy == 0:
                    dy = BLOCK_SIZE
                    dx = 0

        # Bewegung
        x += dx
        y += dy

        # Wrap
        if x < 0:
            x = WIDTH - BLOCK_SIZE
        elif x >= WIDTH:
            x = 0

        if y < 0:
            y = HEIGHT - BLOCK_SIZE
        elif y >= HEIGHT:
            y = 0

        snake_head = (x, y)
        snake_list.append(snake_head)

        if len(snake_list) > snake_length:
            del snake_list[0]

        if snake_head in snake_list[:-1]:
            game_over = True
            if score > highscore:
                save_highscore(score)

        # Essen
        if x == food_x and y == food_y:
            snake_length += 1
            score += 1

            if score > highscore:
                highscore = score

            food_x, food_y = new_food()

        # Zeichnen
        screen.fill(BLACK)

        pygame.draw.rect(screen, RED, (food_x, food_y, BLOCK_SIZE, BLOCK_SIZE))
        draw_snake(snake_list, dx, dy)

        screen.blit(FONT.render(f"Score: {score}", True, WHITE), (10, 10))
        screen.blit(FONT.render(f"Highscore: {highscore}", True, WHITE), (10, 35))

        pygame.display.flip()

        # ⚡ Geschwindigkeit steigt mit Score
        speed = 10 + score // 3
        clock.tick(speed)

# Start
while True:
    game_loop()
