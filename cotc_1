ESP:AddObjectListener(workspace.TotemServiceMain.Totems, {
    Color = Color3.fromRGB(255, 0, 255),
})

ESP:AddObjectListener(workspace.TotemServiceMain.RareTotems, {
    Color = Color3.fromRGB(255, 0, 255),
})

ESP:AddObjectListener(workspace.CollectablesPart1.Active, {
    Color = Color3.fromRGB(0, 255, 0)
})

ESP:AddObjectListener(workspace.CollectablesPart2.ActiveItems, {
    Color = Color3.fromRGB(0, 255, 0)
})

--esp

Tab1:AddButton({
    Name = "Cryptid ESP",
    Callback = function()
while true do
wait(0.5)
ESP:AddObjectListener(workspace.Cryptids, {
    Color = Color3.fromRGB(255, 0, 0)
})
end
Lib.prompt('INFO', "You might see the cryptids flashing, I had to use a while true do loop for it, don't mind it.", 17.5)
end
})

Tab1:AddButton({
    Name = "Houseguest ESP",
    Callback = function()
    while true do
        wait(0.5)
    ESP:AddObjectListener(workspace, {
        Color = Color3.fromRGB(255, 0, 0),
        Name = "NervousHouseguest",
        CustomName = "Nervous Houseguest"
    })
end
Lib.prompt('INFO', "Used another while true do loop for this one.", 15)
    end
})

--teleports section
Tab:AddLabel("Backrooms Teleports")

Tab:AddButton({
    Name = "Teleport to The Backrooms",
    Callback = function()
    hrp.CFrame = CFrame.new(-751.821838, 10.3196249, -5103.88135)
    wait(0.1)
    hrp.CFrame = CFrame.new(-751.821838, 10.3196249, -5103.88135)
    end
})

Tab:AddButton({
    Name = "Teleport to Pipe Dreams",
    Callback = function()
        game:GetService("TeleportService"):Teleport(9341597882, LocalPlayer)
    end
})

Tab:AddButton({
    Name = "Teleport to Poolrooms",
    Callback = function()
        if pid ~= 9341597882 then
	    Lib.prompt("info", "oi ur not in the right game, sending you over", 15)
	    wait(7.5)
            game:GetService("TeleportService"):Teleport(9341597882, LocalPlayer)
            if syn then
                syn.queue_on_teleport('wait(10) game:GetService("Players").LocalPlayer:WaitForChild("Character") end game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-1614.55, 193.498, 15.7132)')
            end
        elseif pid == 9341597882 then
        game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-1614.55, 193.498, 15.7132)
        end
    end
})

--collection things

Tab2:AddButton({
    Name = "Collect all Totems",
    Callback = function()
        for i,v in pairs(workspace.TotemServiceMain.Totems:GetDescendants()) do
            if v:IsA("ClickDetector") then
                fireclickdetector(v)
            end
        end
        wait()
        for i,v in pairs(workspace.TotemServiceMain.RareTotems:GetDescendants()) do
            if v:IsA("ClickDetector") then
                fireclickdetector(v)
            end
        end
    end
})

Tab2:AddButton({
    Name = "Collect All Fuses, Wires and Lightbulbs",
    Callback = function()
        for i,v in pairs(workspace.CollectablesPart2.ActiveItems:GetDescendants()) do
            if v:IsA("ClickDetector") and v.Parent:IsA("Model") then
                fireclickdetector(v)
            end
        end
    end
})

Tab2:AddButton({
    Name = "Collect All Batteries",
    Callback = function()
        for i,v in pairs(workspace.Gameplay.Batteries:GetDescendants()) do
            if v:IsA("ClickDetector") and v.Parent:IsA("Model") then
                fireclickdetector(v)
            end
        end
    end
})

Tab2:AddButton({
    Name = "Finish Part 1",
    Callback = function()
    if workspace.CollectablesPart1.Active.Fuel.Fuel1.Fuel then
    cservice:FireServer(unpack(args1))
    end
    if workspace.CollectablesPart1.Active.CrowbarHammer.CrowbarHammer then
    cservice:FireServer(unpack(args2))
    end
    if workspace.CollectablesPart1.Active.Keys.Keys then
    cservice:FireServer(unpack(args3))
    end
    if workspace.CollectablesPart1.Active.Tire.Tire1.Tire then
    cservice:FireServer(unpack(args4))
    end
    if workspace.CollectablesPart1.Active.ToolKit.ToolKit then
    cservice:FireServer(unpack(args5))
    end
    wait(0.1)
    if workspace.Map.PreLoadedMap_1.FoundObjects then
    fireclickdetector(workspace.Map.PreLoadedMap_1.FoundObjects:WaitForChild("Sparkles"):WaitForChild("ClickDetector"))
    end
    end
})

Tab2:AddButton({
    Name = "Remove Trees",
    Callback = function()
        game:GetService("Workspace").Map.Trees:Destroy()
    end
})

Tab2:AddParagraph("Info", "You can only multiply up to 50, don't try changing value afterwards either else it'll break.")
Tab2:AddTextbox({
	Name = "Multiply Bullets Fired",
	Default = "1",
	TextDisappear = true,
	Callback = function(Value)
        local settings = {repeatamount = Value, exceptions = {"SayMessageRequest","GunService","CryptidService","AdminService","PartOne","ControlService","CollectableService","GameService","AudioService","GuiService","ShowMessage","LoadService","EndingService","ToolService","PetService","GivePets","SkinService","ApplySkin","BuyCrate","SpawnPets","RemovePet","TotemService","TotemGUIService","BecomeService"}}
        local mt = getrawmetatable(game)
        local old = mt.__namecall
        setreadonly(mt, false)
        mt.__namecall = function(uh, ...)
               local args = {...}
               local method = getnamecallmethod()
               for i,o in next, settings.exceptions do
                       if uh.Name == o then
                           return old(uh, ...)
                       end
               end
               if method == "FireServer" or method == "InvokeServer" then
                       for i = 1,settings.repeatamount do
                           old(uh, ...)
                       end
               end
               return old(uh, ...)
        end
        setreadonly(mt, true)
	end	  
})
