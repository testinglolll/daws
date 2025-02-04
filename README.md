-- Script para Administrador no ServerScriptService

local gamepasses = {
    ["2xStrength"] = 1003391412,
    ["2xDamage"] = 1003733340,
    ["2xMoney"] = 1004681429,
    ["2xAttackSpeed"] = 1003889477,
    ["MagicDrops"] = 1004549423,
    ["Lucky"] = 1004549424,
    ["SuperLucky"] = 1004741439,
    ["UltraLucky"] = 1003955551,
    ["SmallStorage"] = 1003307511,
    ["BigStorage"] = 1002851470
    -- Adicione mais gamepasses conforme necessário
}

-- Função para simular a posse do gamepass
local function grantGamepassToPlayer(player, gamepassName)
    local gamepassId = gamepasses[gamepassName]

    if gamepassId then
        -- Simulando que o jogador tem o gamepass
        -- Pode ser alterado conforme o que o gamepass faz
        local gamepassValue = Instance.new("BoolValue")
        gamepassValue.Name = gamepassName
        gamepassValue.Parent = player

        -- Aqui você pode colocar a lógica para aplicar o efeito do gamepass
        if gamepassName == "2xStrength" then
            -- Exemplo: Dobrar a força
            player.StrengthIncome = 2  -- Aplique o efeito de 2x força, altere conforme seu sistema
        elseif gamepassName == "2xDamage" then
            -- Exemplo: Dobrar o dano
            player.DamageMultiplier = 2  -- Aplique o efeito de 2x dano, altere conforme seu sistema
        elseif gamepassName == "2xMoney" then
            -- Exemplo: Dobrar o dinheiro ganho
            player.MoneyMultiplier = 2  -- Aplique o efeito de 2x dinheiro, altere conforme seu sistema
        elseif gamepassName == "2xAttackSpeed" then
            -- Exemplo: Dobrar a velocidade de ataque
            player.AttackSpeed = 2  -- Aplique o efeito de 2x velocidade de ataque
        elseif gamepassName == "MagicDrops" then
            -- Exemplo: Aumentar chance de drops
            player.MagicDropChance = true  -- Aplique o efeito de MagicDrops
        elseif gamepassName == "Lucky" then
            -- Exemplo: Aumentar sorte
            player.Lucky = true  -- Aplique o efeito de Lucky
        elseif gamepassName == "SuperLucky" then
            -- Exemplo: Aumentar super sorte
            player.SuperLucky = true  -- Aplique o efeito de SuperLucky
        elseif gamepassName == "UltraLucky" then
            -- Exemplo: Aumentar ultra sorte
            player.UltraLucky = true  -- Aplique o efeito de UltraLucky
        elseif gamepassName == "SmallStorage" then
            -- Exemplo: Aumentar espaço de armazenamento
            player.StorageSpace = 150  -- Aplique o efeito de SmallStorage
        elseif gamepassName == "BigStorage" then
            -- Exemplo: Aumentar espaço de armazenamento
            player.StorageSpace = 300  -- Aplique o efeito de BigStorage
        end
    else
        warn("Gamepass não encontrado!")
    end
end

-- Comando de admin para aplicar gamepasses manualmente ao jogador
game.Players.PlayerAdded:Connect(function(player)
    -- Exemplo de como usar para um jogador específico
    -- Substitua "NomeDoJogador" pelo nome real do jogador que você quer aplicar o gamepass
    if player.Name == "best_aimlabPlayer" then
        -- Aplique o gamepass desejado
        grantGamepassToPlayer(player, "2xStrength")  -- Mude para o nome do gamepass que você deseja aplicar
    end
end)
