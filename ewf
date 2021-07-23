--[[
	ChangeLog: Thank you for using shadoeHax! It's something I've been working on, I ask nicely that you don't steal any scripts from here. I won't do anything about it if you do, just a kind gesture to not.
	
	--//Updates [ 
	+made chams the teamcolor of the player, default is white. 
	+added console lines all the way up to 3500, this should help you guys diagnose bugs in your code.
	]
	
	Future updates [ look forward to: improved detection method, ignored remotes for remote spy, more server sided commands for backdoors (If you find a backdoor game, please send me the link lol) and lots of extra goodies. ]
--]]

--------------------[[Settings]]

local shadoeHax = {

 toggleKey = ("f3"):upper();
 detectedBackdoors = {("OnChatRequest"), ("BackDoor"), ("Backdoor"), ("shadowAntiCheat"), ("Test"), ("Back"), ("")};
 scannedServices = {game:GetService("ReplicatedStorage"), game.Workspace, game:GetService("JointsService")};
	
	["TweenInfo's"] = {
		playerFinder = {
				whatchanged = {
					firstTween = {
				Size = UDim2.new(0.2, 0, 1, 0)
				};
			secondTween = {
	Size = UDim2.new(0, 0, 1, 0)
};
			};	
		info = TweenInfo.new(
			1, Enum.EasingStyle.Quint, Enum.EasingDirection.Out, 0, false, 0
		)};
	};
	 flycontrol = {
	--//Any keys here, they're replaced; Expl: forward = Enum.KeyCode.W --//Note: must have it labeled as uncapital 'forward = [KeyCode Here]'. Have fun! - shadow

	flyingSpeed = 70;
};

	misc = {};
};

-------------------------------[[]]

local player = game:GetService("Players").LocalPlayer

repeat wait() until player:IsDescendantOf(game:GetService("Players"))

repeat wait() until player.Character
repeat wait() until player.Character:IsDescendantOf(game.Workspace)

local character = player.Character

local humanoid = character:WaitForChild("Humanoid")
local mouse = player:GetMouse()
local currentCamera = game.Workspace.CurrentCamera

local coreGui = game:GetService("CoreGui")
local runService = game:GetService("RunService")
local tweenService = game:GetService("TweenService")
local replicatedstorage = game:GetService("ReplicatedStorage")
local userInputService = game:GetService("UserInputService")
local soundService = game:GetService("SoundService")


	local _VERSION = _VERSION
local _version = ("1.4.3")
local _console_version = ("1.5.1")
local _variable_hecker_menu_version = ("1.1.2")
local _shadoehax_terminal_version = ("1.1.2")

	local _REGISTRY = debug.getregistry()

--//Instances
--//Client
local mainGui = Instance.new("ScreenGui")
local mainFrame = Instance.new("ScrollingFrame")
local Header = Instance.new("TextLabel")
local gameInfo = Instance.new("TextLabel")
local uiGrid = Instance.new("UIGridLayout")
local speed = Instance.new("TextBox")
local jump = Instance.new("TextBox")
local destroyTool = Instance.new("TextButton")
local teleportTool = Instance.new("TextButton")
local viewAll = Instance.new("TextButton")
local nameTags = Instance.new("TextButton")
local gravity = Instance.new("TextBox")
local remoteSpy = Instance.new("TextButton")
local fly = Instance.new("TextButton")
local variableHecker = Instance.new("TextButton")

--//Server
local destroy = Instance.new("TextButton")
local serverconsoleButton = Instance.new("TextButton")
local serverGravity = Instance.new("TextBox")
local killAll = Instance.new("TextButton")
local killOthers = Instance.new("TextButton")

--//Other
local activateExtras = Instance.new("TextButton")
local playerFinder = Instance.new("TextBox")
local playerToShow = Instance.new("TextLabel")

--//Client+Server
local playerSpecificScripts = Instance.new("Frame")
local viewPlayer = Instance.new("TextButton")
local teleportTo = Instance.new("TextButton")
local shadoeHaxTerminal = Instance.new("TextButton")

--//DigitalObjects
local isToggled = true

local changecolors = {
	 mainFrame, Header, gameInfo, speed, jump, destroy, serverconsoleButton, destroyTool, teleportTool, viewAll, nameTags, gravity, serverGravity, remoteSpy, fly, variableHecker, killAll, killOthers, playerSpecificScripts, shadoeHaxTerminal
};
local specialRainBowed = {
	playerFinder, playerToShow, activateExtras, viewPlayer, teleportTo
};

--//Audio
local clickSound = Instance.new("Sound", mainGui)
clickSound.Name = "clickSound"
clickSound.SoundId = "rbxassetid://226892749"
clickSound.Volume = 0.1

soundService.AmbientReverb = "NoReverb"
--//FunctionLibrary

function shadoeHax:SpoofMTProperty(objectSpoofed, properySpoofed, ...)
	local fakeReturns = (...)
Header.Text = ("Spoofing " .. properySpoofed .. "...")
wait(0.4)
						warn("[shadoeHax] Spoof bypass: " .. properySpoofed)
	spawn(function()
			local spoofedMetaTable = getrawmetatable(objectSpoofed, true)
	setreadonly(spoofedMetaTable, false)

local spoofedMetaIndex = spoofedMetaTable.__index
	spoofedMetaTable.__index = newcclosure(function(object, propertyName)

			if  object == (objectSpoofed) and propertyName == (properySpoofed) then
			
	return (fakeReturns);
			end
			return spoofedMetaIndex(object, propertyName);
		end)
	setreadonly(spoofedMetaTable, true)
	end)
end

function shadoeHax:SpoofObjectFunction(objectSpoofed, functionName, ...)
					local spoofedReturns = (...)
local spoofedMetaTable = getrawmetatable(objectSpoofed, true)
setreadonly(spoofedMetaTable, false)

local nameCall = spoofedMetaTable.__namecall

spoofedMetaTable.__namecall = newcclosure(function(object, ...)
local tupleArgs = {...}

		local functionMethod = (getnamecallmethod());

if object == (objectSpoofed) and functionMethod == (functionName) then 

	return (spoofedReturns);
end
		return nameCall(object, ...);
	end)
		setreadonly(spoofedMetaTable, true)
end
function shadoeHax:SpoofNewTableIndex(objectSpoofed, spoofedValue, ...)
	local spoofedReturn = (...)
local spoofedMetaTable = getrawmetatable(objectSpoofed, true)
setreadonly(spoofedMetaTable, false)

local newIndex = spoofedMetaTable.__newindex

	spoofedMetaTable.__newindex = newcclosure(function(object, valueName, realValue)

		if object == (objectSpoofed) and valueName == (spoofedValue) then 

	return (spoofedReturn);
		end

		return newIndex(object, valueName, realValue);
	end)
	setreadonly(spoofedMetaTable, true)
end
local function rainbow(adornee)
	spawn(function()
		while script do
	
for i = 0, 1, 0.005 do
	        adornee.BorderColor3 = Color3.fromHSV(i, 1, 1)
				if adornee:IsA("TextLabel") or adornee:IsA("TextButton") or adornee.Name == ("heckVariableBox") or adornee.Name == ("newHeckValue") or adornee.Name == ("mainTerminalTextLine")then

adornee.TextColor3 = Color3.fromHSV(i, 1, 1)
		end
	        runService.RenderStepped: wait()
	    end
end
	end)
end

local function specialRainBow(adornee)
	spawn(function()
		while script do
	
for i = 0, 1, 0.0025 do
	        adornee.BorderColor3 = Color3.fromHSV(i, 1, 1)

adornee.BackgroundColor3 = Color3.fromHSV(i, 1, 1)
	        runService.RenderStepped: wait()
	end
end
		end)
end

function clientError(errormsg)
local headerText = Header.Text
	local headerColor = Header.TextColor3	
	Header.Text = errormsg
Header.TextColor3 = Color3.new(255, 0, 0)
	wait(4)
Header.Text = headerText
	Header.TextColor3 = headerColor

		return {}
end
function criticalError(errorInformation)
local errorData = {mainHeader = Instance.new("TextLabel"), errorInfo = Instance.new("TextLabel"), closeButton = Instance.new("TextButton")}

errorData.mainHeader.Parent = mainGui
errorData.mainHeader.Name = ("criticalErrorHeader")	
errorData.mainHeader.Size = UDim2.new(0.3, 0, 0.02, 0)
errorData.mainHeader.Position = UDim2.new(0.5, 0, 0.3, 0)
errorData.mainHeader.AnchorPoint = Vector2.new(0.75, 0.75)
errorData.mainHeader.BackgroundTransparency = 0.5
errorData.mainHeader.BackgroundColor3 = Color3.new(0, 0, 0)
errorData.mainHeader.BorderSizePixel = 2
errorData.mainHeader.BorderColor3 = Color3.new(25, 255, 0)
errorData.mainHeader.TextScaled = true
errorData.mainHeader.Text = ("shadoeHax Critical Error")
errorData.mainHeader.Active = true
errorData.mainHeader.Draggable = true

errorData.errorInfo.Parent = errorData.mainHeader
errorData.errorInfo.Name = ("mainErrorInfo")
errorData.errorInfo.Size = UDim2.new(1, 0, 15, 0)
errorData.errorInfo.Position = UDim2.new(0, 0, 1.1, 0)
errorData.errorInfo.BackgroundTransparency = 0.5
errorData.errorInfo.BackgroundColor3 = Color3.new(0, 0, 0)
errorData.errorInfo.BorderSizePixel = 2
errorData.errorInfo.BorderColor3 = Color3.new(25, 255, 0)
errorData.errorInfo.TextSize = 10
errorData.errorInfo.TextWrapped = true
errorData.errorInfo.TextXAlignment = Enum.TextXAlignment.Left
errorData.errorInfo.TextYAlignment = Enum.TextYAlignment.Top
errorData.errorInfo.Text = (errorInformation)

errorData.closeButton.Parent = errorData.mainHeader
errorData.closeButton.Name = ("closeButton")
errorData.closeButton.Size = UDim2.new(0.05, 0, 1, 0)
errorData.closeButton.Position = UDim2.new(1, 0, 0, 0)
errorData.closeButton.AnchorPoint = Vector2.new(1, 0)
errorData.closeButton.BackgroundTransparency = 0.5
errorData.closeButton.BackgroundColor3 = Color3.new(0, 0, 0)
errorData.closeButton.BorderSizePixel = 2
errorData.closeButton.BorderColor3 = Color3.new(25, 255, 0)
errorData.closeButton.TextScaled = true
errorData.closeButton.Text = ("X")


errorData.closeButton.MouseButton1Click:connect(function()


	errorData.mainHeader:Destroy()

end)

for _k, v in pairs(errorData) do
rainbow(v)
end

	return {}
end

userInputService.InputBegan:connect(function(key)
	if key.KeyCode == Enum.KeyCode[shadoeHax.toggleKey] then
		if isToggled == true then
			isToggled = false
			
			mainGui.Enabled = false
	else
			isToggled = true
			
			mainGui.Enabled = true
		end
	end
end)

for _k, adornee in pairs(changecolors) do
	rainbow(adornee)
end
for _k, adornee in pairs(specialRainBowed) do
	specialRainBow(adornee)
end
--//Code Begin

local status, err = pcall(function()
	
	local function GenerateRandomCode()
local sourceCharacters = {
	"a"; "b"; "c"; "d"; "e"; "f"; "g"; "h"; "i"; "j"; "k"; "l"; "m"; "n"; "o"; "p"; "q"; "r"; "s"; "t"; "u"; "v"; "w"; "x"; "y"; "z"; 
	1, 2, 3, 4, 5, 6, 7, 8, 9, 0; "!"; "@"; "#"; "$"; "%"; "^"; "&"; "*"; "|"; "+"; "_"; "-";
}

local mainCode = {}

for i = 0, 15, 1 do
local characterCode = math.random(1, #sourceCharacters)
local characterChosen = sourceCharacters[characterCode]
table.insert(mainCode, characterChosen)
wait()
end

local function finalizeCode(insertedCharacter)
	
table.insert(mainCode, 6, insertedCharacter)
table.insert(mainCode, 12, insertedCharacter)

local generatedCode = mainCode

return generatedCode
end

local generatedCode = finalizeCode("-")

local finalCode = ""

for _k, v in pairs(generatedCode) do
	finalCode = finalCode .. v
end
generatedCode = string.upper(finalCode)

for character in (string.gmatch(generatedCode, "[%w%p]+")) do
	generatedCode = character
end

return generatedCode
end
	
	mainGui.Name = GenerateRandomCode()
		mainGui.Parent = coreGui
	
Header.Parent = mainGui
Header.Name = "Header"
Header.Position = UDim2.new(0.5, 0, 0.375, 0)
Header.AnchorPoint = Vector2.new(0.5, 1.5)
		Header.Size = UDim2.new(0.01, 0, 0.02, 0)
		Header:TweenSize(UDim2.new(0.3, 0, 0.02, 0))
Header.Active = true
Header.Draggable = true
Header.BackgroundTransparency = 0.5
Header.BackgroundColor3 = Color3.new(0, 0, 0)
Header.BorderSizePixel = 2
Header.BorderColor3 = Color3.new(255, 25, 0)
Header.Font = Enum.Font.Arial
Header.TextColor3 = Color3.new(255, 25, 0)
Header.TextScaled = true
Header.Text = "shadoeHax is bypassing some anticheats xd..."

--//bypasses [
wait(1)
shadoeHax:SpoofMTProperty(character:WaitForChild("Humanoid"), ("WalkSpeed"), (16))
shadoeHax:SpoofMTProperty(character:WaitForChild("Humanoid"), ("JumpPower"), (50))
shadoeHax:SpoofMTProperty(game.Workspace, ("Gravity"), (196.2))

--]

	local backdoor, nobackdoor = false, false
	
local backdoorcheck = function(services)

		Header.Text = ("Searching for backdoor...");
		wait(1);
for _k, service in pairs(services) do
		local children = service:GetDescendants()
		for _k, portal in pairs(children) do
			if portal:IsA("RemoteFunction") or portal:IsA("RemoteEvent") then
				for _k, detected in pairs(shadoeHax.detectedBackdoors) do

				if (portal.Name == detected) then
					backdoor = true;
					return (portal)
			else
					nobackdoor = true;
				end
						end
		end
end
					end
end
local backdoorportal = backdoorcheck(shadoeHax.scannedServices)

mainFrame.Parent = Header
		mainFrame.Name = "mainFrame"
		mainFrame.Size = UDim2.new(1, 0, 1, 0)
		mainFrame:TweenSize(UDim2.new(1, 0, 20, 0))
		mainFrame.Position = UDim2.new(0, 0, 1.1, 0)
		mainFrame.AnchorPoint = Vector2.new(0, 0)
		mainFrame.BackgroundColor3 = Color3.new(0, 0, 0)
		mainFrame.BackgroundTransparency = 0.5
		mainFrame.BorderSizePixel = 2
mainFrame.BorderColor3 = Color3.new(255, 25, 0)
				wait(2)
gameInfo.Parent = Header
gameInfo.Name = "gameInfo"
gameInfo.Position = UDim2.new(0, 0, 21.2, 0)
gameInfo.Size = UDim2.new(1, 0, 1, 0)
gameInfo.BackgroundTransparency = 0.5
gameInfo.BackgroundColor3 = Color3.new(0, 0, 0)
gameInfo.BorderSizePixel = 2
gameInfo.BorderColor3 = Color3.new(255, 25, 0)
gameInfo.TextScaled = true
gameInfo.Font = Enum.Font.Arial
gameInfo.TextColor3 = Color3.new(255, 25, 0)

activateExtras.Parent = Header
activateExtras.Name = ("activateExtras")
activateExtras.Size = UDim2.new(0.05, 0, 1, 0)
activateExtras.Position = UDim2.new(0, 0, 0, 0)
activateExtras.BorderSizePixel = 2
activateExtras.Text = ("+")
activateExtras.TextScaled = true
activateExtras.TextColor3 = Color3.new(1, 1, 1)
activateExtras.Visible = true
local extrasAreEnabled = false

activateExtras.MouseButton1Click:connect(function(addExtras)

		if extrasAreEnabled == false then
			extrasAreEnabled = true

playerFinder.Visible = true
			tweenService:Create(playerFinder, shadoeHax["TweenInfo's"].playerFinder.info, shadoeHax["TweenInfo's"].playerFinder.whatchanged.firstTween):Play()
activateExtras.Text = ("x")
		elseif extrasAreEnabled == true then
			extrasAreEnabled = false

			tweenService:Create(playerFinder, shadoeHax["TweenInfo's"].playerFinder.info, shadoeHax["TweenInfo's"].playerFinder.whatchanged.secondTween):Play()
		wait(0.35)
			playerFinder.Visible = false
activateExtras.Text = ("+")
		end
end)

playerFinder.Parent = Header
playerFinder.Name = ("playerFinder")
playerFinder.Size = UDim2.new(0, 0, 1, 0)
playerFinder.AnchorPoint = Vector2.new(1, 0)
playerFinder.Position = UDim2.new(-0.01, 0, 0, 0)
playerFinder.BorderSizePixel = 2
playerFinder.Text = ("Search Players")
playerFinder.PlaceholderText = ("Search Players")
playerFinder.TextScaled = true
playerFinder.Visible = false

playerToShow.Parent = playerFinder
playerToShow.Name = ("playerToShow")
playerToShow.Size = UDim2.new(1, 0, 1, 0)
playerToShow.Position = UDim2.new(0, 0, 1, 0)
playerToShow.BorderSizePixel = 2
playerToShow.Text = ([[]])
playerToShow.TextScaled = true
playerToShow.Visible = false

playerFinder.Focused:connect(function(make_Visible)
	
	
				playerToShow.Visible = true
				
end)

playerFinder.FocusLost:connect(function()
	playerToShow.Visible = false
	
		local searchedForPlayer = playerFinder.Text
	
if searchedForPlayer ~= ([[]]) then
	for _k, player in pairs(game:GetService("Players"):GetChildren()) do
			local playerName = player.Name
		
		local foundPlayer = string.match(string.lower(playerName), (string.lower(searchedForPlayer) .. "[%w%p]+"))
		
		if string.lower(playerName) == (foundPlayer) then
			
			playerFinder.Text = (playerToShow.Text)
			break;
		end
		if string.lower(searchedForPlayer) == string.lower(playerName) then
			
			playerFinder.Text = (playerToShow.Text)
			break;
		end
	end
end
end)
playerFinder.Changed:connect(function(update_Text)
	
	local searchedForPlayer = playerFinder.Text
	
	if searchedForPlayer ~= ([[]]) then
		for _k, player in pairs(game:GetService("Players"):GetChildren()) do
				local playerName = player.Name
				
		local foundPlayer = string.match(string.lower(playerName), (string.lower(searchedForPlayer) .. "[%w%p]+"))
		
		if string.lower(playerName) == (foundPlayer) then
			
			playerToShow.Text = (playerName)
			break;
		end
	end
end
end)

playerSpecificScripts.Parent = playerFinder
playerSpecificScripts.Name = ("playerSpecificScripts")
playerSpecificScripts.Size = UDim2.new(1, 0, 19.2, 0)
playerSpecificScripts.Position = UDim2.new(0, 0, 3, 0)
playerSpecificScripts.BackgroundTransparency = 0.2
playerSpecificScripts.BackgroundColor3 = Color3.new(0, 0, 0)
playerSpecificScripts.BorderSizePixel = 2
playerSpecificScripts.BorderColor3 = Color3.new(255, 25, 0)
--//playerSpecificScripts.ScrollingEnabled = true
--//playerSpecificScripts.CanvasSize = UDim2.new(0.525, 0, 421, 0)
--//playerSpecificScripts.CanvasPosition = Vector2.new(65, 0)
--//playerSpecificScripts.ScrollBarImageColor3 = Color3.new(255, 255, 0)
--//playerSpecificScripts.ElasticBehavior = "WhenScrollable"
--//playerSpecificScripts.VerticalScrollBarInset = "None"
--//playerSpecificScripts.HorizontalScrollBarInset = "None"

local playerSpecialUiGrid = Instance.new("UIGridLayout", playerSpecificScripts)
playerSpecialUiGrid.Name = ("uiGrid")
playerSpecialUiGrid.CellPadding = UDim2.new(0.005, 0, 0.001, 0)
playerSpecialUiGrid.CellSize = UDim2.new(1, 0, 0.05, 0)

	if backdoorportal then
local loadstringenabled, loadstringunavailable = pcall(function()		
if backdoorportal:IsA("RemoteFunction") then

backdoorportal:InvokeServer([[print("shadoeHax SS engine loaded.")]])
elseif backdoorportal:IsA("RemoteEvent") then

backdoorportal:FireServer([[print("shadoeHax SS engine loaded.")]])
	end
end)
if loadstringenabled then

	warn([[ shadoeHax SS engine loaded ]])
	elseif loadstringunavailable then

		criticalError("shadoeHax internal SS error :beginning of SS engine: loadstring is not enabled.")
end	
			runService.RenderStepped:connect(function(updatePhysicsFps)
				local realPhysicsFps = math.floor(game.Workspace:GetRealPhysicsFPS())
		gameInfo.Text = "Toggle Key: " .. shadoeHax.toggleKey .. "; Backdoor Aquired: " .. backdoorportal.Name .. "; Found In: " .. "game." ..  backdoorportal:GetFullName() .. "; RealTimePhysicsFps = " .. realPhysicsFps
		end)
	else
		
			runService.RenderStepped:connect(function(updatePhysicsFps)
				local realPhysicsFps = math.floor(game.Workspace:GetRealPhysicsFPS())
		gameInfo.Text = "Toggle Key: " .. shadoeHax.toggleKey .. "; v" .. _version .. ", RealTimePhysicsFps = " .. realPhysicsFps
		end)
	end

uiGrid.Parent = mainFrame
uiGrid.Name = "uiGrid"
uiGrid.CellPadding = UDim2.new(0.005, 0, 0.005588, 0)
uiGrid.CellSize = UDim2.new(0.19, 0, 0.17, 0)

if backdoor then
	Header.Text = "BackDoor found; full access aquired."
	wait(2)
	Header.Text = "shadoeHax v" .. _version .. ", " .. _VERSION
	--//Commands	
destroy.Parent = mainFrame
destroy.Name = "Destroy"
destroy.BackgroundTransparency = 0.5
destroy.BackgroundColor3 = Color3.new(math.random(255)/255, math.random(255)/255, math.random(255)/255)
destroy.BorderSizePixel = 2
destroy.Font = Enum.Font.Arial
destroy.TextScaled = true
destroy.TextColor3 = Color3.new(math.random(255)/255, math.random(255)/255, math.random(255)/255)
destroy.Text = "Destroy Server"
destroy.MouseButton1Click:connect(function(destroyserver)
	clickSound:Play()	
local serverinstructions = [[
local music = Instance.new("Sound", workspace)
	music.MaxDistance = math.huge
	music.Volume = 10
	music.SoundId = "rbxassetid://212675193"
	music.Looped = true
	music:Play()
spawn(function()
	
	local childrentable = game.Workspace:GetDescendants()
	
	for _k, v in pairs(childrentable) do
		if v:IsA("BasePart") then
			local image = Instance.new("Decal", v)
		image.Texture = "rbxassetid://671961987"
			image.Face = "Front"
						local image2 = Instance.new("Decal", v)
			image2.Texture = "rbxassetid://671961987"
		image2.Face = "Back"
			local image3 = Instance.new("Decal", v)
		image3.Texture = "rbxassetid://671961987"
			image3.Face = "Left"
		local image4 = Instance.new("Decal", v)
			image4.Texture = "rbxassetid://671961987"
image4.Face = "Right"
			local image5 = Instance.new("Decal", v)
		image5.Texture = "rbxassetid://671961987"
		image5.Face = "Top"
		local image6 = Instance.new("Decal", v)
		image6.Texture = "rbxassetid://671961987"
		image6.Face = "Bottom"
					local sparklez = Instance.new("Sparkles", v)
		end
	end
end)
		while wait(0.5) do
		game:GetService("Lighting").Ambient = Color3.new(math.random(255)/255, math.random(255)/255, math.random(255)/255)
	for _k, player in pairs(game:GetService("Players"):GetPlayers()) do
		repeat wait() until player.Character
	repeat wait() until player.Character:IsDescendantOf(game.Workspace)
		
		local character = player.Character
		
		for _k, v in pairs(character:GetChildren()) do
		if v:IsA("Humanoid") then
			v.Health = 0
			end
		end
	end end 
	]]
	if backdoorportal:IsA("RemoteFunction") then
		backdoorportal:InvokeServer(serverinstructions)
	elseif backdoorportal:IsA("RemoteEvent") then
		backdoorportal:FireServer(serverinstructions)
	end
end)
serverconsoleButton.Parent = mainFrame
serverconsoleButton.Name = "serverConsoleButton"
serverconsoleButton.BackgroundTransparency = 0.5
serverconsoleButton.BackgroundColor3 = Color3.new(math.random(255)/255, math.random(255)/255, math.random(255)/255)
serverconsoleButton.BorderSizePixel = 2
serverconsoleButton.Font = Enum.Font.Arial
serverconsoleButton.TextScaled = true
serverconsoleButton.TextColor3 = Color3.new(math.random(255)/255, math.random(255)/255, math.random(255)/255)
serverconsoleButton.Text = "Server Console"
local consoleisactive = false
serverconsoleButton.MouseButton1Click:connect(function(addConsole)
	clickSound:Play()	
	if consoleisactive == false then
		consoleisactive = true
			local serverConsole = {
		consoleHeader = Instance.new("TextLabel");
		consoleframeHeader = Instance.new("Frame"), consolemainFrame = Instance.new("ScrollingFrame"), consoleLine = Instance.new("TextBox"), lineCount = Instance.new("TextLabel"), executeButton = Instance.new("TextButton"), outputFrame = Instance.new("ScrollingFrame"), outPut = Instance.new("TextLabel"), clearButton = Instance.new("TextButton");
		}
			
for _k, adornee in pairs(serverConsole) do
	rainbow(adornee)
end

if backdoorportal:IsA("RemoteFunction") then
		backdoorportal:InvokeServer([[local serveroutPut = Instance.new("RemoteEvent", game:GetService("ReplicatedStorage"):WaitForChild("DefaultChatSystemChatEvents"))
			serveroutPut.Name = "ChatError"]])
	elseif backdoorportal:IsA("RemoteEvent") then
		backdoorportal:FireServer([[local serveroutPut = Instance.new("RemoteEvent", game:GetService("ReplicatedStorage"):WaitForChild("DefaultChatSystemChatEvents"))
			serveroutPut.Name = "ChatError"]])
end 
local activated = false

spawn(function()
	repeat
	Header.Text = "Loading." wait(0.2) Header.Text = "Loading.." wait(0.2) Header.Text = "Loading..."  wait(0.2)
	until activated == true
	
	Header.Text = "shadoeHax v" .. _version .. ", " .. _VERSION
end)
		wait(2)
		activated = true
	
		local serveroutPut = replicatedstorage:WaitForChild("DefaultChatSystemChatEvents"):WaitForChild("ChatError")
			
	  serverConsole.consoleframeHeader.Parent = mainGui
 serverConsole.consoleframeHeader.Name = "consoleFrameHeader"
	serverConsole.consoleframeHeader.Size = UDim2.new(0.3, 0, 0.02, 0)
	serverConsole.consoleframeHeader.Position = Header.Position + UDim2.new(-0.45, 0, 0, 0)
		serverConsole.consoleframeHeader.BackgroundTransparency = 1
serverConsole.consoleframeHeader.BackgroundColor3 = Color3.new(0, 0, 0)
   serverConsole.consoleframeHeader.BorderSizePixel = 0
	serverConsole.consoleframeHeader.Active = true
serverConsole.consoleframeHeader.Draggable = true
	serverConsole.consoleframeHeader.ZIndex = 10
	
		serverConsole.consoleHeader.Parent = serverConsole.consoleframeHeader
serverConsole.consoleHeader.Name = "consoleHeader"
serverConsole.consoleHeader.Position = UDim2.new(0, 0, 0, 0)
serverConsole.consoleHeader.AnchorPoint = Vector2.new(0, 0)
		serverConsole.consoleHeader.Size = UDim2.new(1, 0, 1, 0)
serverConsole.consoleHeader.Active = false
serverConsole.consoleHeader.Draggable = false
serverConsole.consoleHeader.BackgroundTransparency = 0.5
serverConsole.consoleHeader.BackgroundColor3 = Color3.new(0, 0, 0)
serverConsole.consoleHeader.BorderSizePixel = 2
serverConsole.consoleHeader.BorderColor3 = Color3.new(255, 25, 0)
serverConsole.consoleHeader.Font = Enum.Font.Arial
serverConsole.consoleHeader.TextColor3 = Color3.new(255, 25, 0)
serverConsole.consoleHeader.TextScaled = true
serverConsole.consoleHeader.Text = "shadoeHax Server Console v" .. _console_version

serverConsole.consolemainFrame.Parent = serverConsole.consoleframeHeader
		serverConsole.consolemainFrame.Name = "consoleMainFrame"
		serverConsole.consolemainFrame.Size = UDim2.new(1, 0, 20, 0)
		serverConsole.consolemainFrame.CanvasSize = UDim2.new(200, 0, 4000, 0)
		serverConsole.consolemainFrame.CanvasPosition = Vector2.new(0, 0)
		serverConsole.consolemainFrame.Position = UDim2.new(0, 0, 1.1, 0)
		serverConsole.consolemainFrame.AnchorPoint = Vector2.new(0, 0)
		serverConsole.consolemainFrame.BackgroundColor3 = Color3.new(0, 0, 0)
		serverConsole.consolemainFrame.BackgroundTransparency = 0.5
		serverConsole.consolemainFrame.BorderSizePixel = 2
serverConsole.consolemainFrame.BorderColor3 = Color3.new(255, 25, 0)
serverConsole.consolemainFrame.ScrollBarImageColor3 = Color3.new(255, 255, 0)
serverConsole.consolemainFrame.ScrollingEnabled = true
serverConsole.consolemainFrame.ElasticBehavior = "WhenScrollable"
serverConsole.consolemainFrame.VerticalScrollBarInset = "None"
serverConsole.consolemainFrame.HorizontalScrollBarInset = "None"

serverConsole.lineCount.Parent = serverConsole.consolemainFrame
serverConsole.lineCount.Name = "lineCount"
serverConsole.lineCount.Size = UDim2.new(0.0003, 0, 1, 0)
serverConsole.lineCount.ZIndex = 10
serverConsole.lineCount.BorderSizePixel = 0
serverConsole.lineCount.BackgroundColor3 = Color3.new(0, 0, 0)
serverConsole.lineCount.BackgroundTransparency = 0.1
serverConsole.lineCount.TextYAlignment = Enum.TextYAlignment.Top
serverConsole.lineCount.TextColor3 = Color3.new(255, 25, 0)
serverConsole.lineCount.TextSize = 15
serverConsole.lineCount.Font = Enum.Font.Code
serverConsole.lineCount.Text = ("")

for i = 16, 3500, 1 do
	
	serverConsole.lineCount.Text = serverConsole.lineCount.Text .. i .. "\n"
end

serverConsole.consoleLine.Parent = serverConsole.consolemainFrame
serverConsole.consoleLine.Name = "consoleLine"
serverConsole.consoleLine.Size = UDim2.new(1, 0, 1, 0)
serverConsole.consoleLine.Position = UDim2.new(0.00031, 0, 0, 0)
serverConsole.consoleLine.BackgroundTransparency = 0.2
serverConsole.consoleLine.BackgroundColor3 = Color3.new(0, 0, 0)
serverConsole.consoleLine.TextXAlignment = Enum.TextXAlignment.Left
serverConsole.consoleLine.TextYAlignment = Enum.TextYAlignment.Top
serverConsole.consoleLine.Font = Enum.Font.Code
serverConsole.consoleLine.MultiLine = true
serverConsole.consoleLine.ClearTextOnFocus = false
serverConsole.consoleLine.TextColor3 = Color3.new(255, 200/255, 0)
serverConsole.consoleLine.TextWrapped = true
serverConsole.consoleLine.TextSize = 15
serverConsole.consoleLine.Text = ('--[[ \n Why does it start at line 16 you may ask? \n Well, there is some precode to get everything \n working that was made by me. \n This should help fix any issues with diagnosing problemos -shadow. \n ]]-- \n \n print("Hello World!")')

serverConsole.executeButton.Parent = serverConsole.consoleHeader
serverConsole.executeButton.Name = "executeButton"
serverConsole.executeButton.Size = UDim2.new(0.15, 0, 1, 0)
serverConsole.executeButton.Position = UDim2.new(1, 0, 0, 0)
serverConsole.executeButton.AnchorPoint = Vector2.new(1, 0)
serverConsole.executeButton.BackgroundTransparency = 0.2
serverConsole.executeButton.BorderSizePixel = 0
serverConsole.executeButton.BackgroundColor3 = Color3.new(255, 200/255, 0)
serverConsole.executeButton.Font = Enum.Font.Code
serverConsole.executeButton.TextColor3 = Color3.new(255, 255, 255)
serverConsole.executeButton.TextScaled = true
serverConsole.executeButton.Text = [[ Execute ]]

serverConsole.outputFrame.Parent = serverConsole.consoleHeader
serverConsole.outputFrame.Name = "outputFrame"
serverConsole.outputFrame.Size = UDim2.new(0.325, 0, 21.1, 0)
serverConsole.outputFrame.Position = UDim2.new(-0.33, 0, 0, 0)
serverConsole.outputFrame.BackgroundTransparency = 0.2
serverConsole.outputFrame.BackgroundColor3 = Color3.new(0, 0, 0)
serverConsole.outputFrame.BorderSizePixel = 2
serverConsole.outputFrame.BorderColor3 = Color3.new(255, 25, 0)
serverConsole.outputFrame.ScrollingEnabled = true
serverConsole.outputFrame.CanvasSize = UDim2.new(0.525, 0, 421, 0)
serverConsole.outputFrame.CanvasPosition = Vector2.new(65, 0)
serverConsole.outputFrame.ScrollBarImageColor3 = Color3.new(255, 255, 0)
serverConsole.outputFrame.ElasticBehavior = "WhenScrollable"
serverConsole.outputFrame.VerticalScrollBarInset = "None"
serverConsole.outputFrame.HorizontalScrollBarInset = "None"

serverConsole.outPut.Parent = serverConsole.outputFrame
serverConsole.outPut.Name = "outPut"
serverConsole.outPut.Size = UDim2.new(0.975, 0, 1, 0)
serverConsole.outPut.Position = UDim2.new(0.5, 0, 0.5, 0)
serverConsole.outPut.AnchorPoint = Vector2.new(0.5, 0.5)
serverConsole.outPut.BackgroundTransparency = 0.4
serverConsole.outPut.BackgroundColor3 = Color3.new(0, 0, 0)
serverConsole.outPut.BorderSizePixel = 2
serverConsole.outPut.BorderColor3 = Color3.new(255, 25, 0)
serverConsole.outPut.Font = Enum.Font.Code
serverConsole.outPut.TextYAlignment = Enum.TextYAlignment.Top
serverConsole.outPut.TextSize = 15
serverConsole.outPut.TextScaled = false
serverConsole.outPut.TextWrapped = true
serverConsole.outPut.TextColor3 = Color3.new(255/255, 0, 0)
serverConsole.outPut.Text = [[shadoe-Server-Log
]]
serverConsole.clearButton.Parent = serverConsole.consoleHeader
serverConsole.clearButton.Name = "clearButton"
serverConsole.clearButton.Size = UDim2.new(0.1, 0, 1, 0)
serverConsole.clearButton.Position = UDim2.new(0, 0, 0, 0)
serverConsole.clearButton.AnchorPoint = Vector2.new(0, 0)
serverConsole.clearButton.BackgroundTransparency = 0.2
serverConsole.clearButton.BorderSizePixel = 0
serverConsole.clearButton.BackgroundColor3 = Color3.new(255, 200/255, 0)
serverConsole.clearButton.Font = Enum.Font.Code
serverConsole.clearButton.TextColor3 = Color3.new(255, 255, 255)
serverConsole.clearButton.TextScaled = true
serverConsole.clearButton.Text = [[ Clear ]]

serverConsole.executeButton.MouseButton1Click:connect(function(execute)
	clickSound:Play()	
pcall(function()
	local serverCode = serverConsole.consoleLine.Text
	
	local serverInstructions = [[
		local shadoeHax = {};

		local replicatedStorage = game:GetService("ReplicatedStorage")
		local serveroutPut = replicatedStorage:WaitForChild("DefaultChatSystemChatEvents"):WaitForChild("ChatError")
		
		repeat wait() until serveroutPut:IsDescendantOf(replicatedStorage)
		
		local print = function(msg)
			print(msg)
			serveroutPut:FireAllClients(msg, false)
		end
		function shadoeHax:KillPlayer(playerName) local player = game:GetService("Players")[playerName] local playerCharacter = player.Character playerCharacter:WaitForChild("Humanoid").Health = 0 end function shadoeHax:KickPlayer(playerName, kickReason) local player = game:GetService("Players")[playerName] player:Kick(kickReason) end

		local status, err = pcall(function()
			
		]] .. serverCode .. [[
		
		end)
		
		if status then
			--//serveroutPut:FireAllClients("Program Executed", false)
			elseif err then
			serveroutPut:FireAllClients(err, true)
		end
		]]
if backdoorportal:IsA("RemoteFunction") then
		backdoorportal:InvokeServer(serverInstructions)
	elseif backdoorportal:IsA("RemoteEvent") then
		backdoorportal:FireServer(serverInstructions)
end 
	end)
end)

serverConsole.clearButton.MouseButton1Click:connect(function(clearText)
	clickSound:Play()	
		serverConsole.consoleLine.Text = ""
		serverConsole.outPut.Text = [[shadoe-Server-Log
		]]
end)

serveroutPut.OnClientEvent:connect(function(serverErr, type)
	local ostimetable = os.date(("*t"), os.time())
	
	if type ~= false then
	serverConsole.outPut.Text = serverConsole.outPut.Text .. [[
		
		Stack Begin
	]] .. string.format(ostimetable.hour .. ":" .. ostimetable.min .. ":" .. ostimetable.sec .. " -- ") .. serverErr .. [[
	
		Stack End
	]]
	elseif type == false then
		serverConsole.outPut.Text = serverConsole.outPut.Text .. [[
			
		]] .. serverErr .. [[
	]]
	end
end)


	else
		consoleisactive = false
		mainGui:WaitForChild("consoleFrameHeader"):Destroy()
if backdoorportal:IsA("RemoteFunction") then
		backdoorportal:InvokeServer([[game:GetService("ReplicatedStorage"):WaitForChild("DefaultChatSystemChatEvents"):WaitForChild("ChatError"):Destroy()]])
	elseif backdoorportal:IsA("RemoteEvent") then
		backdoorportal:FireServer([[game:GetService("ReplicatedStorage"):WaitForChild("DefaultChatSystemChatEvents"):WaitForChild("ChatError"):Destroy()]])
end 
	end
	end)
	serverGravity.Parent = mainFrame
serverGravity.BackgroundTransparency = 0.8
serverGravity.BackgroundColor3 = Color3.new(math.random(255)/255, math.random(255)/255, math.random(255)/255)
serverGravity.BorderSizePixel = 2
serverGravity.Font = Enum.Font.Arial
serverGravity.TextScaled = true
serverGravity.TextColor3 = Color3.new(math.random(255)/255, math.random(255)/255, math.random(255)/255)
serverGravity.PlaceholderColor3 = serverGravity.TextColor3
serverGravity.PlaceholderText = ("Server Gravity")
serverGravity.Text = ("Server Gravity")
serverGravity.FocusLost:connect(function()
	if serverGravity.Text ~= "" then
			
			local serverInstructions = [[game.Workspace.Gravity = ]] .. serverGravity.Text

		if backdoorportal:IsA("RemoteFunction") then
		backdoorportal:InvokeServer(serverInstructions)
	elseif backdoorportal:IsA("RemoteEvent") then
		backdoorportal:FireServer(serverInstructions)
		end
	end
end)

killAll.Parent = mainFrame
killAll.Name = ("killAll")
killAll.BorderSizePixel = 2
killAll.BackgroundTransparency = 0.5
killAll.BackgroundColor3 = Color3.new(math.random(255)/255, math.random(255)/255, math.random(255)/255)
killAll.Font = Enum.Font.Arial
killAll.TextColor3 = Color3.new(math.random(255)/255, math.random(255)/255, math.random(255)/255)
killAll.TextScaled = true
killAll.TextColor3 = Color3.new(255, 255, 255)
killAll.Font = Enum.Font.Arial
killAll.Text = ("Kill All")

killAll.MouseButton1Click:connect(function(killAllLol)
clickSound:Play()

local serverInstructions = [[
	local players = game:GetService("Players")

	for _k, v in pairs(players:GetPlayers()) do
pcall(function()
		local character = v.Character
		character["Humanoid"].Health = 0
		end)
	end
]];

	if backdoorportal:IsA("RemoteFunction") then
backdoorportal:InvokeServer(serverInstructions)
		elseif backdoorportal:IsA("RemoteEvent") then
backdoorportal:FireServer(serverInstructions)
	end
end)

killOthers.Parent = mainFrame
killOthers.Name = ("killOthers")
killOthers.BorderSizePixel = 2
killOthers.BackgroundTransparency = 0.5
killOthers.BackgroundColor3 = Color3.new(math.random(255)/255, math.random(255)/255, math.random(255)/255)
killOthers.Font = Enum.Font.Arial
killOthers.TextColor3 = Color3.new(math.random(255)/255, math.random(255)/255, math.random(255)/255)
killOthers.TextScaled = true
killOthers.TextColor3 = Color3.new(255, 255, 255)
killOthers.Font = Enum.Font.Arial
killOthers.Text = ("Kill Others")

killOthers.MouseButton1Click:connect(function(killOthersLol)
clickSound:Play()

local serverInstructions = [[
	local players = game:GetService("Players")

	for _k, v in pairs(players:GetPlayers()) do
		if v.Name ~= ("]] .. player.Name .. [[") then
pcall(function()
		local character = v.Character
		character["Humanoid"].Health = 0
		end)
	end
	end
]];

	if backdoorportal:IsA("RemoteFunction") then
backdoorportal:InvokeServer(serverInstructions)
		elseif backdoorportal:IsA("RemoteEvent") then
backdoorportal:FireServer(serverInstructions)
	end
end)


viewPlayer.Parent = playerSpecificScripts
viewPlayer.Name = ("viewPlayer")
viewPlayer.BackgroundTransparency = 0
viewPlayer.BackgroundColor3 = Color3.new(math.random(255)/255, math.random(255)/255, math.random(255)/255)
viewPlayer.BorderSizePixel = 2
viewPlayer.Font = Enum.Font.Arial
viewPlayer.TextScaled = true
viewPlayer.TextColor3 = Color3.new(0, 0, 0)
viewPlayer.Text = ("View Player")
local isViewingPlayer = false

viewPlayer.MouseButton1Click:connect(function(viewSpecifiedPlayer)
					clickSound:Play()
pcall(function()
	if isViewingPlayer == false then
		isViewingPlayer = true
local playerString = tostring(playerFinder.Text)
		
			local viewedPlayer = game:GetService("Players")[playerString]

repeat wait() until viewedPlayer.Character
repeat wait() until viewedPlayer.Character:IsDescendantOf(game.Workspace)

			local viewedCharacter = viewedPlayer.Character
local viewedHumanoid = viewedCharacter["Humanoid"]

currentCamera.CameraSubject = viewedHumanoid

viewedHumanoid.Died:connect(function(reset)
		isViewingPlayer = false

	currentCamera.CameraSubject = character["Humanoid"]
end)
viewedPlayer.CharacterAdded:connect(function(resetCharacter)
		isViewingPlayer = false

	currentCamera.CameraSubject = character["Humanoid"]
end)

elseif isViewingPlayer == true then
	isViewingPlayer = false

	currentCamera.CameraSubject = character["Humanoid"]
		end
	end)
end)

teleportTo.Parent = playerSpecificScripts
teleportTo.Name = ("teleportToPlayer")
teleportTo.BackgroundTransparency = 0
teleportTo.BackgroundColor3 = Color3.new(math.random(255)/255, math.random(255)/255, math.random(255)/255)
teleportTo.BorderSizePixel = 2
teleportTo.Font = Enum.Font.Arial
teleportTo.TextScaled = true
teleportTo.TextColor3 = Color3.new(0, 0, 0)
teleportTo.Text = ("Teleport To Player")

teleportTo.MouseButton1Click:connect(function(teleportToPlayerlol)
						clickSound:Play()
	pcall(function()
local playerString = tostring(playerFinder.Text)
		
			local viewedPlayer = game:GetService("Players")[playerString]

repeat wait() until viewedPlayer.Character
repeat wait() until viewedPlayer.Character:IsDescendantOf(game.Workspace)

local viewedCharacter = viewedPlayer.Character
		character["HumanoidRootPart"].CFrame = viewedCharacter["HumanoidRootPart"].CFrame + Vector3.new(math.random(-5, 5), 0, math.random(-5, 5))
	end)
end)

shadoeHaxTerminal.Parent = mainFrame
shadoeHaxTerminal.Name = ("shadoeHaxTerminal")
shadoeHaxTerminal.BackgroundTransparency = 0.8
shadoeHaxTerminal.BackgroundColor3 = Color3.new(math.random(255)/255, math.random(255)/255, math.random(255)/255)
shadoeHaxTerminal.BorderSizePixel = 2
shadoeHaxTerminal.Font = Enum.Font.Arial
shadoeHaxTerminal.TextScaled = true
shadoeHaxTerminal.TextColor3 = Color3.new(math.random(255)/255, math.random(255)/255, math.random(255)/255)
shadoeHaxTerminal.Text = ("shadoe Terminal")
local terminalIsOpen = false

shadoeHaxTerminal.MouseButton1Click:connect(function(initializeTerminal)
if terminalIsOpen == false then
	terminalIsOpen = true

	local terminalData = {mainHeader = Instance.new("TextLabel"), terminalBox = Instance.new("TextBox"), executeButton = Instance.new("TextButton")}

terminalData.mainHeader.Parent = mainGui
terminalData.mainHeader.Name = ("terminalHeader")	
terminalData.mainHeader.Size = UDim2.new(0.375, 0, 0.02, 0)
terminalData.mainHeader.Position = UDim2.new(0.5, 0, 0.3, 0)
terminalData.mainHeader.AnchorPoint = Vector2.new(0.75, 0.75)
terminalData.mainHeader.BackgroundTransparency = 0.25
terminalData.mainHeader.BackgroundColor3 = Color3.new(0, 0, 0)
terminalData.mainHeader.BorderSizePixel = 2
terminalData.mainHeader.BorderColor3 = Color3.new(25, 255, 0)
terminalData.mainHeader.TextScaled = true
terminalData.mainHeader.Text = ("shadoeHax Terminal v" .. _shadoehax_terminal_version)
terminalData.mainHeader.Active = true
terminalData.mainHeader.Draggable = true

terminalData.terminalBox.Parent = terminalData.mainHeader
terminalData.terminalBox.Name = ("mainTerminalTextLine")
terminalData.terminalBox.Size = UDim2.new(1, 0, 20, 0)
terminalData.terminalBox.Position = UDim2.new(0, 0, 1.1, 0)
terminalData.terminalBox.BackgroundTransparency = 0.25
terminalData.terminalBox.BackgroundColor3 = Color3.new(0, 0, 0)
terminalData.terminalBox.BorderSizePixel = 2
terminalData.terminalBox.BorderColor3 = Color3.new(25, 255, 0)
terminalData.terminalBox.TextSize = 10
terminalData.terminalBox.TextWrapped = true
terminalData.terminalBox.TextColor3 = Color3.new(255, 25, 0)
terminalData.terminalBox.MultiLine = true
terminalData.terminalBox.ClearTextOnFocus = true
terminalData.terminalBox.TextXAlignment = Enum.TextXAlignment.Left
terminalData.terminalBox.TextYAlignment = Enum.TextYAlignment.Top
terminalData.terminalBox.PlaceholderText = (">>>")
terminalData.terminalBox.PlaceholderColor3 = Color3.new(255, 25, 0)
terminalData.terminalBox.Text = (">>>");

terminalData.executeButton.Parent = terminalData.mainHeader
terminalData.executeButton.Name = ("executeButton")
terminalData.executeButton.Size = UDim2.new(0.15, 0, 1, 0)
terminalData.executeButton.Position = UDim2.new(1, 0, 0, 0)
terminalData.executeButton.AnchorPoint = Vector2.new(1, 0)
terminalData.executeButton.BackgroundTransparency = 0.5
terminalData.executeButton.BackgroundColor3 = Color3.new(0, 0, 0)
terminalData.executeButton.BorderSizePixel = 2
terminalData.executeButton.BorderColor3 = Color3.new(25, 255, 0)
terminalData.executeButton.TextScaled = true
terminalData.executeButton.Text = ("Execute")

terminalData.executeButton.MouseButton1Click:connect(function(executeCmd)
local cmdExecuted = (terminalData.terminalBox.Text)

	local functionExecuted = ([[
		local shadoeHax = {};

--// PRE-MADE CONSTANTS & FUNCTIONS:

local players = game:GetService("Players")
local player = players.LocalPlayer

repeat wait() until player:IsDescendantOf(game:GetService("Players"))

repeat wait() until player.Character
repeat wait() until player.Character:IsDescendantOf(game.Workspace)

local character = player.Character

local humanoid = character:WaitForChild("Humanoid")
local mouse = player:GetMouse()
local currentCamera = game.Workspace.CurrentCamera

local function GetPlayerList()
	local playerList = game:GetService("Players"):GetPlayers();


	return (playerList);
end

local function GetCharacterList()
	local characterList = {};

	local playerList = game:GetService("Players"):GetPlayers();

	for _k, v in pairs(playerList) do

pcall(function()

		table.insert(characterList, v.Character)
end)
	end

	return (characterList);
end

--// MT-API

function shadoeHax:SpoofMTProperty(objectSpoofed, properySpoofed, ...)
	local fakeReturns = (...)
wait(0.4)
						warn("[shadoeHax] Spoof bypass: " .. properySpoofed)
	spawn(function()
			local spoofedMetaTable = getrawmetatable(objectSpoofed, true)
	setreadonly(spoofedMetaTable, false)

local spoofedMetaIndex = spoofedMetaTable.__index
	spoofedMetaTable.__index = newcclosure(function(object, propertyName)

			if  object == (objectSpoofed) and propertyName == (properySpoofed) then

	return (fakeReturns);
			end
			return spoofedMetaIndex(object, propertyName);
		end)
	setreadonly(spoofedMetaTable, true)
	end)
end

function shadoeHax:SpoofObjectFunction(objectSpoofed, functionName, ...)
					local spoofedReturns = (...)
local spoofedMetaTable = getrawmetatable(objectSpoofed, true)
setreadonly(spoofedMetaTable, false)

local nameCall = spoofedMetaTable.__namecall

spoofedMetaTable.__namecall = newcclosure(function(object, ...)
local tupleArgs = {...}

	local functionMethod = (getnamecallmethod());
if object == (objectSpoofed) and functionMethod == (functionName) then 

	return (spoofedReturns);
end
					return nameCall(object, ...);
	end)
		setreadonly(spoofedMetaTable, true)
end
function shadoeHax:SpoofNewTableIndex(objectSpoofed, spoofedValue, ...)
	local spoofedReturn = (...)
						local spoofedMetaTable = getrawmetatable(objectSpoofed, true)
setreadonly(spoofedMetaTable, false)

local newIndex = spoofedMetaTable.__newindex

	spoofedMetaTable.__newindex = newcclosure(function(object, valueName, realValue)

		if object == (objectSpoofed) and valueName == (spoofedValue) then 

	return (spoofedReturn);
		end

		return newIndex(object, valueName, realValue);
	end)
	setreadonly(spoofedMetaTable, true)
end
	]] .. cmdExecuted)


	loadstring(functionExecuted)()

	terminalData.terminalBox.Text = (terminalData.terminalBox.Text .. ("\n >>>Executed!"))
end)


for _k, v in pairs(terminalData) do
		rainbow(v)
	end
	elseif terminalIsOpen == true then
terminalIsOpen = false

		mainGui:WaitForChild("terminalHeader"):Destroy()
end
end)

	--//End of Server
elseif nobackdoor then
	Header.TextColor3 = Color3.new(255, 0, 0)
	Header.BorderColor3 = Color3.new(255, 0, 0)
	mainFrame.BorderColor3 = Color3.new(255, 0, 0)
	gameInfo.TextColor3 = Color3.new(255, 0, 0)
	gameInfo.BorderColor3 = Color3.new(255, 0, 0)
	Header.Text = "BackDoor not found; client access only."
	wait(2)
	Header.Text = "Initializing client mode..."
	wait(2)
	Header.Text = "shadoeHax(Client) v" .. _version .. ", " .. _VERSION
	--//Commands
	speed.Parent = mainFrame
speed.BackgroundTransparency = 0.8
speed.BackgroundColor3 = Color3.new(math.random(255)/255, math.random(255)/255, math.random(255)/255)
speed.BorderSizePixel = 2
speed.Font = Enum.Font.Arial
speed.TextScaled = true
speed.TextColor3 = Color3.new(math.random(255)/255, math.random(255)/255, math.random(255)/255)
speed.PlaceholderColor3 = speed.TextColor3
speed.PlaceholderText = ("Speed")
speed.Text = ("Speed")
speed.FocusLost:connect(function()
spawn(function()
runService.RenderStepped:connect(function()
	character = player.Character	
	
for _k, humanoid in pairs(character:GetChildren()) do
	if humanoid:IsA("Humanoid") then
	if speed.Text ~= "" then
		humanoid.WalkSpeed = speed.Text
	end
end end
end)
end)
end)
jump.Parent = mainFrame
jump.BackgroundTransparency = 0.8
jump.BackgroundColor3 = Color3.new(math.random(255)/255, math.random(255)/255, math.random(255)/255)
jump.BorderSizePixel = 2
jump.Font = Enum.Font.Arial
jump.TextScaled = true
jump.TextColor3 = Color3.new(math.random(255)/255, math.random(255)/255, math.random(255)/255)
jump.PlaceholderColor3 = jump.TextColor3
jump.PlaceholderText = ("JumpPower")
jump.Text = "JumpPower"
jump.FocusLost:connect(function()
spawn(function()
runService.RenderStepped:connect(function()
	character = player.Character
	
for _k, humanoid in pairs(character:GetChildren()) do
if humanoid:IsA("Humanoid") then
	if jump.Text ~= "" then
		humanoid.JumpPower = jump.Text
	end
end end
end)
end)
end)
destroyTool.Parent = mainFrame
destroyTool.Name = "destroyTool"
destroyTool.BorderSizePixel = 2
destroyTool.BackgroundTransparency = 0.5
destroyTool.BackgroundColor3 = Color3.new(math.random(255)/255, math.random(255)/255, math.random(255)/255)
destroyTool.Font = Enum.Font.Arial
destroyTool.TextColor3 = Color3.new(math.random(255)/255, math.random(255)/255, math.random(255)/255)
destroyTool.TextScaled = true
destroyTool.TextColor3 = Color3.new(255, 255, 255)
destroyTool.Font = Enum.Font.Arial
destroyTool.Text = "Destroy Tool"
local canequip = true

destroyTool.MouseButton1Click:connect(function(deletetool)
clickSound:Play()	
if canequip == true then
			canequip = false

				spawn(function()
	runService.RenderStepped:connect(function()
		character = player.Character
		humanoid = character:WaitForChild("Humanoid")
				end) end)			
		pcall(function()
		
local delete = Instance.new("Tool", player:WaitForChild("Backpack"))
delete.Name = (GenerateRandomCode())
delete.TextureId = ("rbxassetid://2806986819")
delete.RequiresHandle = false
delete.ToolTip = ("delete")

humanoid:EquipTool(delete)

delete.Equipped:connect(function(localmouse)
local selection = Instance.new("SelectionBox", character)
selection.Name = "Selection"

spawn(function()
	while wait() do
		
		selection.Adornee = mouse.Target
	end
end)
localmouse.Button1Down:connect(function(i)
local target = mouse.Target
local explody = Instance.new("Explosion", workspace)
explody.BlastRadius = nil
explody.BlastPressure = nil
explody.Position = target.Position
target:Destroy()
		end) 

delete.Unequipped:connect(function(removeselection)
	selection:Destroy()
end)
end)

		end)
else
	
	canequip = true
	
	humanoid:UnequipTools()
	for _k, v in pairs(character:GetChildren()) do
		if v:IsA("SelectionBox") then
			v:Destroy()
		end
	end
for _k, v in pairs(player:WaitForChild("Backpack"):GetChildren()) do
		if v:IsA("Tool") then
		if v.ToolTip == ("delete") then
			v:Destroy()
		end
	end
end
end
end)

teleportTool.Parent = mainFrame
teleportTool.Name = ("teleportTool")
teleportTool.BorderSizePixel = 2
teleportTool.BackgroundTransparency = 0.5
teleportTool.BackgroundColor3 = Color3.new(math.random(255)/255, math.random(255)/255, math.random(255)/255)
teleportTool.Font = Enum.Font.Arial
teleportTool.TextColor3 = Color3.new(math.random(255)/255, math.random(255)/255, math.random(255)/255)
teleportTool.TextScaled = true
teleportTool.TextColor3 = Color3.new(255, 255, 255)
teleportTool.Font = Enum.Font.Arial
teleportTool.Text = "Teleport Tool"
local canequip = true

teleportTool.MouseButton1Click:connect(function(deletetool)
clickSound:Play()	
if canequip == true then
			canequip = false

				spawn(function()
		runService.RenderStepped:connect(function()
			character = player.Character
			humanoid = character:WaitForChild("Humanoid")
				end) end)
		pcall(function()
		
local teleport = Instance.new("Tool", player:WaitForChild("Backpack"))
teleport.Name = (GenerateRandomCode())
teleport.TextureId = ("rbxassetid://2806996160")
teleport.RequiresHandle = false
teleport.ToolTip = ("teleport")

humanoid:EquipTool(teleport)

teleport.Equipped:connect(function(localmouse)
local selection = Instance.new("Part", character)
selection.Shape = "Cylinder"
selection.BrickColor = BrickColor.new("Bright green")
selection.Material = Enum.Material.Neon
selection.Size = Vector3.new(0.1, 1, 1)
selection.Anchored = true
selection.CanCollide = false
selection.Name = "Selection"

spawn(function()
	while wait() do
		
		selection.CFrame = CFrame.new(mouse.Hit.p) * CFrame.fromEulerAnglesXYZ(0, 0, math.rad(90))
	end
end)
localmouse.Button1Down:connect(function(i)
character:WaitForChild("HumanoidRootPart").CFrame = CFrame.new(mouse.Hit.p) + Vector3.new(0, 2, 0)
		end) 

teleport.Unequipped:connect(function(removeselection)
	selection:Destroy()
end)
end)

		end)
else
	
	canequip = true
	
	humanoid:UnequipTools()
	for _k, v in pairs(character:GetChildren()) do
		if v.Name == "Selection" then
			v:Destroy()
		end
	end
	for _k, v in pairs(player:WaitForChild("Backpack"):GetChildren()) do
		if v:IsA("Tool") then
		if v.ToolTip == ("teleport") then
			v:Destroy()
		end
	end
	end
end
end)
viewAll.Parent = mainFrame
viewAll.Name = "viewAll"
viewAll.BackgroundTransparency = 0.5
viewAll.BackgroundColor3 = Color3.new(math.random(255)/255, math.random(255)/255, math.random(255)/255)
viewAll.BorderSizePixel = 2
viewAll.TextScaled = true
viewAll.Font = Enum.Font.Arial
viewAll.TextColor3 = Color3.new(math.random(255)/255, math.random(255)/255, math.random(255)/255)
viewAll.Text = "View All Players"
local canview = true

viewAll.MouseButton1Click:connect(function(view)
	clickSound:Play()	
	if canview == true then
		canview = false
		for i, p in pairs(game:GetService("Players"):GetChildren()) do
			if p ~= player then
				local c = p.Character
				for i, part in pairs(c:GetChildren()) do
					if part:IsA("BasePart") then
								part.BrickColor = p.TeamColor
						local teamColor = part.Color
						local g1 = Instance.new("SurfaceGui", part)
						g1.Name = "g"
						g1.AlwaysOnTop = true
						g1.LightInfluence = -1
						g1.Face = "Front"
						local f1 = Instance.new("Frame", g1)
						f1.Name = "f"
						f1.Size = UDim2.new(1, 0, 1, 0)
						f1.BackgroundColor3 = teamColor

						f1.BorderSizePixel = 0
						f1.BorderColor3 = Color3.new(0, 0, 0)
						local g2 = Instance.new("SurfaceGui", part)
						g2.Name = "g2"
						g2.AlwaysOnTop = true
						g2.LightInfluence = -1
						g2.Face = "Back"
						local f2 = Instance.new("Frame", g2)
						f2.Name = "f2"
						f2.Size = UDim2.new(1, 0, 1, 0)
						f2.BackgroundColor3 = teamColor

						f2.BorderSizePixel = 0
						f2.BorderColor3 = Color3.new(0, 0, 0)
						local g3 = Instance.new("SurfaceGui", part)
						g3.Name = "g3"
						g3.AlwaysOnTop = true
						g3.LightInfluence = -1
						g3.Face = "Left"
						local f3 = Instance.new("Frame", g3)
						f3.Name = "f3"
						f3.Size = UDim2.new(1, 0, 1, 0)
						f3.BackgroundColor3 = teamColor

						f3.BorderSizePixel = 0
						f3.BorderColor3 = Color3.new(0, 0, 0)
						local g4 = Instance.new("SurfaceGui", part)
						g4.Name = "g4"
						g4.AlwaysOnTop = true
						g4.LightInfluence = -1
						g4.Face = "Right"
						local f4 = Instance.new("Frame", g4)
						f4.Name = "f4"
						f4.Size = UDim2.new(1, 0, 1, 0)
						f4.BackgroundColor3 = teamColor

						f4.BorderSizePixel = 0
						f4.BorderColor3 = Color3.new(0, 0, 0)
						local g5 = Instance.new("SurfaceGui", part)
						g5.Name = "g5"
						g5.AlwaysOnTop = true
						g5.LightInfluence = -1
						g5.Face = "Top"
						local f5 = Instance.new("Frame", g5)
						f5.Name = "f5"
						f5.Size = UDim2.new(1, 0, 1, 0)
						f5.BackgroundColor3 = teamColor

						f5.BorderSizePixel = 0
						f5.BorderColor3 = Color3.new(0, 0, 0)
						local g6 = Instance.new("SurfaceGui", part)
						g6.Name = "g6"
						g6.AlwaysOnTop = true
						g6.LightInfluence = -1
						g6.Face = "Bottom"
						local f6 = Instance.new("Frame", g6)
						f6.Name = "f6"
						f6.Size = UDim2.new(1, 0, 1, 0)
						f6.BackgroundColor3 = teamColor
						
						f6.BorderSizePixel = 0
						f6.BorderColor3 = Color3.new(0, 0, 0)
					end
				end
			end
		end
	else
		canview = true
		for i, p in pairs(game:GetService("Players"):GetChildren()) do
			if p ~= player then
				local c = p.Character
				for i, part in pairs(c:GetChildren()) do
					if part:IsA("BasePart") then
						for i, v in pairs(part:GetChildren()) do
							if v:IsA("SurfaceGui") then
								v:Destroy()
							end
						end
					end		
					end
						end
					end
	end
end)
nameTags.Parent = mainFrame
nameTags.Name = "nameTags"
nameTags.BackgroundTransparency = 0.5
nameTags.BackgroundColor3 = Color3.new(math.random(255)/255, math.random(255)/255, math.random(255)/255)
nameTags.BorderSizePixel = 2
nameTags.TextScaled = true
nameTags.Font = Enum.Font.Arial
nameTags.TextColor3 = Color3.new(math.random(255)/255, math.random(255)/255, math.random(255)/255)
nameTags.Text = "NameTags"
local cannametag = true

nameTags.MouseButton1Click:connect(function(nametag)
	clickSound:Play()	
		if cannametag == true then
		cannametag = false
		for i, p in pairs(game:GetService("Players"):GetChildren()) do
			if p ~= player then
				local c = p.Character
				for i, part in pairs(c:GetChildren()) do
					if part:IsA("BasePart") then
						if part.Name == "Head" then

							local n = Instance.new("BillboardGui", part)
							n.Name = "n"
							n.AlwaysOnTop = true
							n.Size = UDim2.new(0, 110, 0, 30)
							n.StudsOffset = Vector3.new(0, 1.5, 0)
							local nt = Instance.new("TextLabel", n)
							nt.Name = "nt"
							nt.Size = UDim2.new(0, 110, 0, 30)
							nt.BackgroundTransparency = 0.6
							nt.BackgroundColor3 = Color3.new(0, 0 ,0)
							nt.TextScaled = true
							nt.Font = Enum.Font.Cartoon
							nt.TextColor3 = Color3.new(255, 0, 0)

							nt.Text = (p.Name)
			        rainbow(nt)
							if p.Team ~= nil then
							for i, v in pairs(game:GetService("Teams"):GetChildren()) do
								if v == p.Team then
									nt.Text = ("(" .. p.Team.Name .. ") " .. p.Name)
								end 
						end end
	p.Changed:connect(function(update)
		if p.Team ~= nil then
		if p.Team.Name == "Police" then
								nt.TextColor3 = UDim2.new(0, 0, 255)
		end end
							nt.Text = (p.Name)
							if p.Team ~= nil then
							for i, v in pairs(game:GetService("Teams"):GetChildren()) do
								if v ~= p.Team then
									nt.Text = ("(" .. p.Team.Name .. ") " .. p.Name)
								end 
						end end
	end)
					end
				end
			end end
		end
		else
					cannametag = true
		for i, p in pairs(game:GetService("Players"):GetChildren()) do
			if p ~= player then
				local c = p.Character
				for i, part in pairs(c:GetChildren()) do
					if part:IsA("BasePart") then
						for i, v in pairs(part:GetChildren()) do
							if v:IsA("BillboardGui") then
								v:Destroy()
							end
						end
					end		
					end
						end
	end
		end
end)
gravity.Parent = mainFrame
gravity.BackgroundTransparency = 0.8
gravity.BackgroundColor3 = Color3.new(math.random(255)/255, math.random(255)/255, math.random(255)/255)
gravity.BorderSizePixel = 2
gravity.Font = Enum.Font.Arial
gravity.TextScaled = true
gravity.TextColor3 = Color3.new(math.random(255)/255, math.random(255)/255, math.random(255)/255)
gravity.PlaceholderColor3 = gravity.TextColor3
gravity.PlaceholderText = ("LocalPlayer Gravity")
gravity.Text = ("LocalPlayer Gravity")
gravity.FocusLost:connect(function()
	spawn(function()
runService.RenderStepped:connect(function()
	if gravity.Text ~= ([[]]) then

		game.Workspace.Gravity = gravity.Text
	end    end)
	end) 
end)
remoteSpy.Parent = mainFrame
remoteSpy.Name = "remoteSpy"
remoteSpy.BackgroundTransparency = 0.8
remoteSpy.BackgroundColor3 = Color3.new(math.random(255)/255, math.random(255)/255, math.random(255)/255)
remoteSpy.BorderSizePixel = 2
remoteSpy.Font = Enum.Font.Arial
remoteSpy.TextScaled = true
remoteSpy.TextColor3 = Color3.new(math.random(255)/255, math.random(255)/255, math.random(255)/255)
remoteSpy.Text = "Remote Spy"
local isspyActivate = false

remoteSpy.MouseButton1Click:connect(function(spy)
clickSound:Play()
	if isspyActivate == false then
		isspyActivate = true
		clientError("Press f9 to view the client log and get the data.")
warn("Running shadoeHax remote spy \n")

local game_Meta = getrawmetatable(game, true)
setreadonly(game_Meta, false)
local gamemeta_nameCall = game_Meta.__namecall

local functionsSearched = {
	"FireServer",
	"InvokeServer";
}

game_Meta.__namecall = function(instanceCalled, ...)
if (instanceCalled.Name ~= ("CharacterSoundEvent")) then
if isspyActivate == true then

local __vt = {...}
local functionMethod = (getnamecallmethod());

if functionMethod == functionsSearched[1] or functionMethod == functionsSearched[2] then 

wait(0.25)
local returnedPacket = {}
	local last = nil
for _k, v in pairs(__vt) do
	local vobj = v
local objType = typeof(v)
	v = tostring(v)	
print(objType)
if objType == "string" then
	v = [["]] .. (v) .. [["]]
elseif objType == "table" then
local _v = vobj
			local tblestring = "{"
local lastArg = nil
for __k, _v in pairs(vobj) do
	local vobj = _v
	local objType = typeof(_v)
	_v = tostring(_v)					
if objType == "string" then
	_v = [["]] .. (_v) .. [["]]
elseif objType == "Vector3" then
	_v = "Vector3.new(" .. (_v) .. ")"
elseif objType == "EnumType" then
	_v = "Enum." .. tostring(vobj.EnumType) .. "." .. vobj.Name
elseif objType == "Enum" then
	_v = "Enum." .. _v
elseif objType == "Instance" then
	_v = "game." .. tostring(vobj:GetFullName())
elseif objType == "CFrame" then
	_v = "CFrame.new(" .. _v .. ")"
elseif objType == "Vector2" then
	_v = "Vector2.new(" .. _v .. ")"
elseif objType == "UDim2" then
	_v = "UDim2.new(" .. string.gsub(_v, "[{}]", "") .. ")"
elseif objType == "BrickColor" then
	_v = [[BrickColor.new("]] .. _v .. [[")]]
elseif objType == "Color3" then
	_v = [[Color.new(]] .. _v .. [[)]]
elseif objType == "NumberRange" then
	_v = [[NumberRange.new(]] .. _v .. [[)]]
	elseif objType == "PhysicalProperties" then
	_v = [[PhysicalProperties.new(]] .. _v .. [[)]]
end

	tblestring = tblestring .. _v .. "; "

 lastArg = tblestring

		tblestring = tblestring .. _v

end
tblestring = lastArg .. "}"
														v = tblestring
	elseif objType == "Vector3" then
	v = "Vector3.new(" .. (v) .. ")"
elseif objType == "EnumType" then
	v = "Enum." .. tostring(vobj.EnumType) .. "." .. vobj.Name
elseif objType == "Enum" then
	v = "Enum." .. v
elseif objType == "Instance" then
	v = "game." .. tostring(vobj:GetFullName())
elseif objType == "CFrame" then
	v = "CFrame.new(" .. v .. ")"
elseif objType == "Vector2" then
	v = "Vector2.new(" .. v .. ")"
elseif objType == "UDim2" then
	v = "UDim2.new(" .. string.gsub(v, "[{}]", "") .. ")"
elseif objType == "BrickColor" then
	v = [[BrickColor.new("]] .. v .. [[")]]
elseif objType == "Color3" then
	v = [[Color.new(]] .. v .. [[)]]
elseif objType == "NumberRange" then
	v = [[NumberRange.new(]] .. v .. [[)]]
	elseif objType == "PhysicalProperties" then
	v = [[PhysicalProperties.new(]] .. v .. [[)]]
end
table.insert(returnedPacket, v .. ", ")
	last = v

end
returnedPacket[#returnedPacket] = last

local returnedData = string.format("\n [shadoeHax] Remote; " .. "game" .. "." .. tostring(instanceCalled:GetFullName()) .. "\n [shadoeHax] Packed Arguments: {" .. table.concat(returnedPacket) .. "}\n [shadoeHax] Method: " .. functionMethod .. "\n")

print(returnedData)
end
		end
end
return gamemeta_nameCall(instanceCalled, ...)
end
setreadonly(game_Meta, true)
	else
		isspyActivate = false
		warn("shadoeHax remote spy disabled \n")
end
end)
fly.Parent = mainFrame
fly.Name = ("flyButton")
fly.BackgroundTransparency = 0.8
fly.BackgroundColor3 = Color3.new(math.random(255)/255, math.random(255)/255, math.random(255)/255)
fly.BorderSizePixel = 2
fly.Font = Enum.Font.Arial
fly.TextScaled = true
fly.TextColor3 = Color3.new(math.random(255)/255, math.random(255)/255, math.random(255)/255)
fly.Text = ("Fly")
local isFlyingToggle = false

fly.MouseButton1Click:connect(function(flyenable)
clickSound:Play()

	if isFlyingToggle == false then
		isFlyingToggle = true
		
		fly.Text = "Flying Enabled; Press 'v' to toggle"
spawn(function()
runService.RenderStepped:connect(function()
character = player.Character
end) end)

local velocity = {forward = 0, backward = 0, left = 0, right = 0}

local default = {
	forward = Enum.KeyCode.W;
	backward = Enum.KeyCode.S;
	left = Enum.KeyCode.A;
	right = Enum.KeyCode.D;
	toggle = Enum.KeyCode.V;
	flyingSpeed = 70;
}

setmetatable(shadoeHax.flycontrol, { __index = default })
local speed = shadoeHax.flycontrol.flyingSpeed
local isFlying = false
local toggle = false
local currentCamera = game.Workspace.CurrentCamera

runService.RenderStepped:connect(function()
	if isFlyingToggle == true then
	          humanoid = character:WaitForChild("Humanoid")
	if isFlying == true then
		if humanoid.Sit ~= true then
		humanoid.PlatformStand = true
		end
		for _k, flyVelo in pairs(character:WaitForChild("HumanoidRootPart"):GetChildren()) do
	if flyVelo.Name == "flyVelocity" then
		flyVelo.Velocity = ((currentCamera.CoordinateFrame.lookVector * (velocity.forward + velocity.backward)*speed) + (currentCamera.CoordinateFrame * CFrame.new((velocity.left + velocity.right)*speed, 0, 0).p - currentCamera.CoordinateFrame.p))
	end end
				for _k, flyGyro in pairs(character:WaitForChild("HumanoidRootPart"):GetChildren()) do
	if flyGyro.Name == "flyGyro" then
		flyGyro.CFrame = currentCamera.CoordinateFrame * CFrame.fromEulerAnglesXYZ(math.rad(-velocity.forward + -velocity.backward)*5.75, 0, math.rad(-velocity.right + -velocity.left)*6.25)
				end end
	else
		humanoid.PlatformStand = false
	end 
	else
		humanoid.PlatformStand = false
end
end)


userInputService.InputBegan:connect(function(key)
				 humanoid = character:WaitForChild("Humanoid")
if isFlyingToggle == true then
	if key.KeyCode == shadoeHax.flycontrol.forward then
		velocity.forward = 5
	elseif key.KeyCode == shadoeHax.flycontrol.backward then
		velocity.backward = -5
	elseif key.KeyCode == shadoeHax.flycontrol.right then
		velocity.left = 5
	elseif key.KeyCode == shadoeHax.flycontrol.left then
		velocity.right = -5
	elseif key.KeyCode == shadoeHax.flycontrol.toggle then
		if toggle == false then
			toggle = true
			
			isFlying = true
			
			--//Objects
local flyVelo = Instance.new("BodyVelocity", nil)
flyVelo.Name = "flyVelocity"
flyVelo.MaxForce = Vector3.new(math.huge, math.huge, math.huge)
flyVelo.Velocity = Vector3.new(0, 0, 0)
flyVelo.Parent = character:WaitForChild("HumanoidRootPart")
local flyGyro = Instance.new("BodyGyro", nil)
flyGyro.Name = "flyGyro"
flyGyro.MaxTorque = Vector3.new(math.huge, math.huge, math.huge)
flyGyro.Parent = character:WaitForChild("HumanoidRootPart")

		else
				toggle = false
			
			isFlying = false
			
		humanoid.PlatformStand = false
for _k, v in pairs(character:WaitForChild("HumanoidRootPart"):GetChildren()) do
	if (v.Name == ("flyVelocity") or v.Name == ("flyGyro")) then
				v:Destroy()
	end;
end;
		end;
	end; end;
end)
userInputService.InputEnded:connect(function(key)
	if key.KeyCode == shadoeHax.flycontrol.forward then
		velocity.forward = 0
	elseif key.KeyCode == shadoeHax.flycontrol.backward then
		velocity.backward = 0
	elseif key.KeyCode == shadoeHax.flycontrol.right then
		velocity.left = 0
	elseif key.KeyCode == shadoeHax.flycontrol.left then
		velocity.right = 0
end
	end)

	else
		isFlyingToggle = false
		
		fly.Text = "Fly"
for _k, v in pairs(character:WaitForChild("HumanoidRootPart"):GetChildren()) do
	if (v.Name == ("flyVelocity") or v.Name == ("flyGyro")) then
				v:Destroy()
			end;
	end;
				end;
end)

variableHecker.Parent = mainFrame
variableHecker.Name = ("variableHecker")
variableHecker.BackgroundTransparency = 0.8
variableHecker.BackgroundColor3 = Color3.new(math.random(255)/255, math.random(255)/255, math.random(255)/255)
variableHecker.BorderSizePixel = 2
variableHecker.Font = Enum.Font.Arial
variableHecker.TextScaled = true
variableHecker.TextColor3 = Color3.new(math.random(255)/255, math.random(255)/255, math.random(255)/255)
variableHecker.Text = ("Variable Hecker")
local isVariableHecking = false

variableHecker.MouseButton1Click:connect(function(createMenu)
clickSound:Play()

	if isVariableHecking == false then
		isVariableHecking = true
local variableHeckerMenu = {mainHeader = Instance.new("TextLabel"), mainVariableHeckerFrame = Instance.new("Frame"), heckVariableBox = Instance.new("TextBox"), newHeckValue = Instance.new("TextBox"), heckButton = Instance.new("TextButton")}

variableHeckerMenu.mainHeader.Parent = mainGui
variableHeckerMenu.mainHeader.Name = ("mainVariableHeckerHeader")	
variableHeckerMenu.mainHeader.Size = UDim2.new(0.15, 0, 0.02, 0)
variableHeckerMenu.mainHeader.Position = Header.Position + UDim2.new(-0.2, 0, 0, 0)
variableHeckerMenu.mainHeader.AnchorPoint = Vector2.new(0.75, 0.75)
variableHeckerMenu.mainHeader.BackgroundTransparency = 0.5
variableHeckerMenu.mainHeader.BackgroundColor3 = Color3.new(0, 0, 0)
variableHeckerMenu.mainHeader.BorderSizePixel = 2
variableHeckerMenu.mainHeader.BorderColor3 = Color3.new(25, 255, 0)
variableHeckerMenu.mainHeader.TextScaled = true
variableHeckerMenu.mainHeader.Text = ("shadoeHax Variable Hecker v" .. _variable_hecker_menu_version)
variableHeckerMenu.mainHeader.Active = true
variableHeckerMenu.mainHeader.Draggable = true

variableHeckerMenu.mainVariableHeckerFrame.Parent = variableHeckerMenu.mainHeader
variableHeckerMenu.mainVariableHeckerFrame.Name = ("mainVariableHeckerFrame")
variableHeckerMenu.mainVariableHeckerFrame.Size = UDim2.new(1, 0, 15, 0)
variableHeckerMenu.mainVariableHeckerFrame.Position = UDim2.new(0, 0, 1.1, 0)
variableHeckerMenu.mainVariableHeckerFrame.BackgroundTransparency = 0.3
variableHeckerMenu.mainVariableHeckerFrame.BackgroundColor3 = Color3.new(0, 0, 0)
variableHeckerMenu.mainVariableHeckerFrame.BorderSizePixel = 2
variableHeckerMenu.mainVariableHeckerFrame.BorderColor3 = Color3.new(25, 255, 0)

variableHeckerMenu.heckVariableBox.Parent = variableHeckerMenu.mainVariableHeckerFrame
variableHeckerMenu.heckVariableBox.Name = ("heckVariableBox")
variableHeckerMenu.heckVariableBox.Size = UDim2.new(1, 0, 0.25, 0)
variableHeckerMenu.heckVariableBox.Position = UDim2.new(0, 0, 0.05, 0)
variableHeckerMenu.heckVariableBox.BackgroundTransparency = 0.5
variableHeckerMenu.heckVariableBox.BackgroundColor3 = Color3.new(0, 0, 0)
variableHeckerMenu.heckVariableBox.BorderSizePixel = 2
variableHeckerMenu.heckVariableBox.TextScaled = true
variableHeckerMenu.heckVariableBox.Font = Enum.Font.Code
variableHeckerMenu.heckVariableBox.PlaceholderText = ("Variable Name")
variableHeckerMenu.heckVariableBox.Text = ("Variable Name")
variableHeckerMenu.heckVariableBox.TextColor3 = Color3.new(25, 255, 0)
variableHeckerMenu.heckVariableBox.ZIndex = 2

variableHeckerMenu.newHeckValue.Parent = variableHeckerMenu.mainVariableHeckerFrame
variableHeckerMenu.newHeckValue.Name = ("newHeckValue")
variableHeckerMenu.newHeckValue.Size = UDim2.new(1, 0, 0.2, 0)
variableHeckerMenu.newHeckValue.Position = UDim2.new(0, 0, 0.4, 0)
variableHeckerMenu.newHeckValue.BackgroundTransparency = 0.5
variableHeckerMenu.newHeckValue.BackgroundColor3 = Color3.new(0, 0, 0)
variableHeckerMenu.newHeckValue.BorderSizePixel = 2
variableHeckerMenu.newHeckValue.TextScaled = true
variableHeckerMenu.newHeckValue.Font = Enum.Font.Code
variableHeckerMenu.newHeckValue.PlaceholderText = ("New Value")
variableHeckerMenu.newHeckValue.Text = ("New Value")
variableHeckerMenu.newHeckValue.TextColor3 = Color3.new(25, 255, 0)
variableHeckerMenu.newHeckValue.ZIndex = 2

variableHeckerMenu.heckButton.Parent = variableHeckerMenu.mainVariableHeckerFrame
variableHeckerMenu.heckButton.Name = ("heckButton")
variableHeckerMenu.heckButton.Size = UDim2.new(0.5, 0, 0.15, 0)
variableHeckerMenu.heckButton.AnchorPoint = Vector2.new(0.5, 0.5)
variableHeckerMenu.heckButton.Position = UDim2.new(0.5, 0, 0.75, 0)
variableHeckerMenu.heckButton.BackgroundTransparency = 0.5
variableHeckerMenu.heckButton.BackgroundColor3 = Color3.new(0, 0, 0)
variableHeckerMenu.heckButton.BorderSizePixel = 2
variableHeckerMenu.heckButton.TextScaled = true
variableHeckerMenu.heckButton.Font = Enum.Font.Code
variableHeckerMenu.heckButton.Text = ("Heck Variable")
variableHeckerMenu.heckButton.TextColor3 = Color3.new(25, 255, 0)
variableHeckerMenu.heckButton.ZIndex = 2


variableHeckerMenu.heckButton.MouseButton1Click:connect(function()
	clickSound:Play()

if (variableHeckerMenu.heckVariableBox.Text ~= "" and variableHeckerMenu.newHeckValue.Text ~= "") then

local changedValue = variableHeckerMenu.heckVariableBox.Text;
local valueAmount = nil;

if string.lower(variableHeckerMenu.newHeckValue.Text) == ("true") then
	
	valueAmount = true
elseif string.lower(variableHeckerMenu.newHeckValue.Text) == ("false") then

	valueAmount = false
elseif typeof(tonumber(variableHeckerMenu.newHeckValue.Text)) == ("number") then

	valueAmount = tonumber(variableHeckerMenu.newHeckValue.Text)
	elseif string.lower(valueAmount) == ("inf") then

	valueAmount = math.huge
else
	valueAmount = tostring(variableHeckerMenu.newHeckValue.Text)
end

for _k, _function in pairs(_REGISTRY) do 

if typeof(_function) == ("function") then 
	
	local upValued = debug.getupvalues(_function)
	for _k, _upValue in pairs(upValued) do
		if typeof(_upValue) == ("table") then

if _upValue[changedValue] ~= nil then
					warn("[shadoeHax] Changed " .. changedValue .. " to: " .. tostring(valueAmount))
			variableHeckerMenu.mainHeader.Text = ("Variable found, hecked!")
		spawn(function()
	while script and wait() do
		
		_upValue[changedValue] = valueAmount
	end
		end)
		wait(2)
		variableHeckerMenu.mainHeader.Text = ("shadoeHax Variable Hecker v" .. _variable_hecker_menu_version)

	break;
end
			elseif upValued[changedValue] ~= nil then
					debug.setupvalue(_function, changedValue, valueAmount)
		spawn(function()
	variableHeckerMenu.mainHeader.Text = ("Variable found, hecked!")
			wait(2)
		variableHeckerMenu.mainHeader.Text = ("shadoeHax Variable Hecker v" .. _variable_hecker_menu_version)
	end)
				break;
		 	end
end
					end
end
		end
	end)

for _k, v in pairs(variableHeckerMenu) do
		rainbow(v)
		end
		elseif (isVariableHecking == true) then
isVariableHecking = false

	mainGui:WaitForChild("mainVariableHeckerHeader"):Destroy()
	end
end)

viewPlayer.Parent = playerSpecificScripts
viewPlayer.Name = ("viewPlayer")
viewPlayer.BackgroundTransparency = 0
viewPlayer.BackgroundColor3 = Color3.new(math.random(255)/255, math.random(255)/255, math.random(255)/255)
viewPlayer.BorderSizePixel = 2
viewPlayer.Font = Enum.Font.Arial
viewPlayer.TextScaled = true
viewPlayer.TextColor3 = Color3.new(0, 0, 0)
viewPlayer.Text = ("View Player")
local isViewingPlayer = false

viewPlayer.MouseButton1Click:connect(function(viewSpecifiedPlayer)
					clickSound:Play()
pcall(function()
	if isViewingPlayer == false then
		isViewingPlayer = true
local playerString = tostring(playerFinder.Text)
		
			local viewedPlayer = game:GetService("Players")[playerString]

repeat wait() until viewedPlayer.Character
repeat wait() until viewedPlayer.Character:IsDescendantOf(game.Workspace)

			local viewedCharacter = viewedPlayer.Character
local viewedHumanoid = viewedCharacter["Humanoid"]

currentCamera.CameraSubject = viewedHumanoid

viewedHumanoid.Died:connect(function(reset)
		isViewingPlayer = false

	currentCamera.CameraSubject = character["Humanoid"]
end)
viewedPlayer.CharacterAdded:connect(function(resetCharacter)
		isViewingPlayer = false

	currentCamera.CameraSubject = character["Humanoid"]
end)

elseif isViewingPlayer == true then
	isViewingPlayer = false

	currentCamera.CameraSubject = character["Humanoid"]
		end
	end)
end)

teleportTo.Parent = playerSpecificScripts
teleportTo.Name = ("teleportToPlayer")
teleportTo.BackgroundTransparency = 0
teleportTo.BackgroundColor3 = Color3.new(math.random(255)/255, math.random(255)/255, math.random(255)/255)
teleportTo.BorderSizePixel = 2
teleportTo.Font = Enum.Font.Arial
teleportTo.TextScaled = true
teleportTo.TextColor3 = Color3.new(0, 0, 0)
teleportTo.Text = ("Teleport To Player")

teleportTo.MouseButton1Click:connect(function(teleportToPlayerlol)
						clickSound:Play()
	pcall(function()
local playerString = tostring(playerFinder.Text)
		
			local viewedPlayer = game:GetService("Players")[playerString]

repeat wait() until viewedPlayer.Character
repeat wait() until viewedPlayer.Character:IsDescendantOf(game.Workspace)

local viewedCharacter = viewedPlayer.Character
		character["HumanoidRootPart"].CFrame = viewedCharacter["HumanoidRootPart"].CFrame + Vector3.new(math.random(-5, 5), 0, math.random(-5, 5))
	end)
end)

shadoeHaxTerminal.Parent = mainFrame
shadoeHaxTerminal.Name = ("shadoeHaxTerminal")
shadoeHaxTerminal.BackgroundTransparency = 0.8
shadoeHaxTerminal.BackgroundColor3 = Color3.new(math.random(255)/255, math.random(255)/255, math.random(255)/255)
shadoeHaxTerminal.BorderSizePixel = 2
shadoeHaxTerminal.Font = Enum.Font.Arial
shadoeHaxTerminal.TextScaled = true
shadoeHaxTerminal.TextColor3 = Color3.new(math.random(255)/255, math.random(255)/255, math.random(255)/255)
shadoeHaxTerminal.Text = ("shadoe Terminal")
local terminalIsOpen = false

shadoeHaxTerminal.MouseButton1Click:connect(function(initializeTerminal)
if terminalIsOpen == false then
	terminalIsOpen = true

	local terminalData = {mainHeader = Instance.new("TextLabel"), terminalBox = Instance.new("TextBox"), executeButton = Instance.new("TextButton")}

terminalData.mainHeader.Parent = mainGui
terminalData.mainHeader.Name = ("terminalHeader")	
terminalData.mainHeader.Size = UDim2.new(0.375, 0, 0.02, 0)
terminalData.mainHeader.Position = UDim2.new(0.5, 0, 0.3, 0)
terminalData.mainHeader.AnchorPoint = Vector2.new(0.75, 0.75)
terminalData.mainHeader.BackgroundTransparency = 0.25
terminalData.mainHeader.BackgroundColor3 = Color3.new(0, 0, 0)
terminalData.mainHeader.BorderSizePixel = 2
terminalData.mainHeader.BorderColor3 = Color3.new(25, 255, 0)
terminalData.mainHeader.TextScaled = true
terminalData.mainHeader.Text = ("shadoeHax Terminal v" .. _shadoehax_terminal_version)
terminalData.mainHeader.Active = true
terminalData.mainHeader.Draggable = true

terminalData.terminalBox.Parent = terminalData.mainHeader
terminalData.terminalBox.Name = ("mainTerminalTextLine")
terminalData.terminalBox.Size = UDim2.new(1, 0, 20, 0)
terminalData.terminalBox.Position = UDim2.new(0, 0, 1.1, 0)
terminalData.terminalBox.BackgroundTransparency = 0.25
terminalData.terminalBox.BackgroundColor3 = Color3.new(0, 0, 0)
terminalData.terminalBox.BorderSizePixel = 2
terminalData.terminalBox.BorderColor3 = Color3.new(25, 255, 0)
terminalData.terminalBox.TextSize = 10
terminalData.terminalBox.TextWrapped = true
terminalData.terminalBox.TextColor3 = Color3.new(255, 25, 0)
terminalData.terminalBox.MultiLine = true
terminalData.terminalBox.ClearTextOnFocus = true
terminalData.terminalBox.TextXAlignment = Enum.TextXAlignment.Left
terminalData.terminalBox.TextYAlignment = Enum.TextYAlignment.Top
terminalData.terminalBox.PlaceholderText = (">>>")
terminalData.terminalBox.PlaceholderColor3 = Color3.new(255, 25, 0)
terminalData.terminalBox.Text = (">>>");

terminalData.executeButton.Parent = terminalData.mainHeader
terminalData.executeButton.Name = ("executeButton")
terminalData.executeButton.Size = UDim2.new(0.15, 0, 1, 0)
terminalData.executeButton.Position = UDim2.new(1, 0, 0, 0)
terminalData.executeButton.AnchorPoint = Vector2.new(1, 0)
terminalData.executeButton.BackgroundTransparency = 0.5
terminalData.executeButton.BackgroundColor3 = Color3.new(0, 0, 0)
terminalData.executeButton.BorderSizePixel = 2
terminalData.executeButton.BorderColor3 = Color3.new(25, 255, 0)
terminalData.executeButton.TextScaled = true
terminalData.executeButton.Text = ("Execute")

terminalData.executeButton.MouseButton1Click:connect(function(executeCmd)
local cmdExecuted = (terminalData.terminalBox.Text)

	local functionExecuted = ([[
		local shadoeHax = {};

--// PRE-MADE CONSTANTS & FUNCTIONS:

local players = game:GetService("Players")
local player = players.LocalPlayer

repeat wait() until player:IsDescendantOf(game:GetService("Players"))

repeat wait() until player.Character
repeat wait() until player.Character:IsDescendantOf(game.Workspace)

local character = player.Character

local humanoid = character:WaitForChild("Humanoid")
local mouse = player:GetMouse()
local currentCamera = game.Workspace.CurrentCamera

local function GetPlayerList()
	local playerList = game:GetService("Players"):GetPlayers();


	return (playerList);
end

local function GetCharacterList()
	local characterList = {};

	local playerList = game:GetService("Players"):GetPlayers();

	for _k, v in pairs(playerList) do

pcall(function()

		table.insert(characterList, v.Character)
end)
	end

	return (characterList);
end

--// MT-API

function shadoeHax:SpoofMTProperty(objectSpoofed, properySpoofed, ...)
	local fakeReturns = (...)
wait(0.4)
						warn("[shadoeHax] Spoof bypass: " .. properySpoofed)
	spawn(function()
			local spoofedMetaTable = getrawmetatable(objectSpoofed, true)
	setreadonly(spoofedMetaTable, false)

local spoofedMetaIndex = spoofedMetaTable.__index
	spoofedMetaTable.__index = newcclosure(function(object, propertyName)

			if  object == (objectSpoofed) and propertyName == (properySpoofed) then

	return (fakeReturns);
			end
			return spoofedMetaIndex(object, propertyName);
		end)
	setreadonly(spoofedMetaTable, true)
	end)
end

function shadoeHax:SpoofObjectFunction(objectSpoofed, functionName, ...)
					local spoofedReturns = (...)
local spoofedMetaTable = getrawmetatable(objectSpoofed, true)
setreadonly(spoofedMetaTable, false)

local nameCall = spoofedMetaTable.__namecall

spoofedMetaTable.__namecall = newcclosure(function(object, ...)
local tupleArgs = {...}

	local functionMethod = (getnamecallmethod());

if object == (objectSpoofed) and functionMethod == (functionName) then 

	return (spoofedReturns);
end
					return nameCall(object, ...);
	end)
		setreadonly(spoofedMetaTable, true)
end
function shadoeHax:SpoofNewTableIndex(objectSpoofed, spoofedValue, ...)
	local spoofedReturn = (...)
						local spoofedMetaTable = getrawmetatable(objectSpoofed, true)
setreadonly(spoofedMetaTable, false)

local newIndex = spoofedMetaTable.__newindex

	spoofedMetaTable.__newindex = newcclosure(function(object, valueName, realValue)

		if object == (objectSpoofed) and valueName == (spoofedValue) then 

	return (spoofedReturn);
		end

		return newIndex(object, valueName, realValue);
	end)
	setreadonly(spoofedMetaTable, true)
end

--// MT-API MODIFIED FUNCTIONS:

	local function initarsenalshadoeaim()
local normalHead = character:WaitForChild("Head")

local userInputService = game:GetService("UserInputService")
local currentCamera = workspace.CurrentCamera
local mouse = player:GetMouse()

local runService = game:GetService("RunService")

shadoeHax:SpoofMTProperty(character.Humanoid, "WalkSpeed", 16)
shadoeHax:SpoofMTProperty(character.Humanoid, "JumpPower", 50)

runService.RenderStepped:connect(function(index)

	character = player.Character
	character.Humanoid.WalkSpeed = 99
	character.Humanoid.JumpPower = 99
end)

local toucher, position = nil, nil

local aimBotConfig = {
 maxDistance = 350;
toggleKey = Enum.KeyCode.F;
}

local closestCharacterHead, distance, currentDistance = nil, nil, math.huge
local aimBotIsActivated = false

runService.RenderStepped:connect(function()
			character = player.Character
if aimBotIsActivated ~= false then


	 for _k, vplayer in pairs(players:GetChildren()) do
pcall(function()
--spawn(function()
		if vplayer ~= player then
if vplayer.TeamColor ~= player.TeamColor then
	
	local vcharacter = vplayer.Character
	local vnormalHead = vcharacter:WaitForChild("Head")
	
	if vcharacter:WaitForChild("Humanoid").Health > 0 then
	 distance = ((normalHead.CFrame.p - vnormalHead.CFrame.p).magnitude)
	
	if distance ~= nil then
						print(currentDistance)
			distance = math.floor(distance)
	if distance < currentDistance then
	if distance <= aimBotConfig.maxDistance then
		
		closestCharacterHead = vnormalHead;
		currentDistance = distance;
	end
end			end
	end
end
			end
	--	end)
	end)
end

	if closestCharacterHead ~= nil then
		local headToShootDuh = closestCharacterHead
		
		currentCamera.CFrame = CFrame.new(currentCamera.CFrame.p, headToShootDuh.CFrame.p)
	end
	closestCharacterHead, currentDistance = nil, math.huge
	end
end)
userInputService.InputBegan:connect(function(inputKey)
	if inputKey.KeyCode == (aimBotConfig.toggleKey) then
		if aimBotIsActivated == false then
			
	aimBotIsActivated = true
		elseif aimBotIsActivated == true then
			
	aimBotIsActivated = false
	end
	end
end)

			local mt = getrawmetatable(game, true)
setreadonly(mt, false)

local nameCall = mt.__namecall

mt.__namecall = function(object, ...)
	local tupleArgs = {...}

				local functionMethod = (getnamecallmethod());

	if object == (workspace) and functionMethod == ("FindPartOnRayWithIgnoreList") then 	
pcall(function()	
		--mouse.TargetFilter = (workspace)
			spawn(function()

local rayObject = Ray.new(character["Head"].CFrame.p, (mouse.Hit.p - character["Head"].CFrame.p).unit * 1000)

local whiteList = {};
for _k, v in pairs(game:GetService("Players"):GetPlayers()) do 
	if v ~= player then 
		
		if v.Character then 
local character = v.Character

table.insert(whiteList, character["Head"]);
		end
	end
end

		toucher, position = workspace:FindPartOnRayWithWhitelist(rayObject, whiteList)
	end)
end)
	wait(0.025)
		return (toucher), (position)
	end

	return nameCall(object, ...)
end
setreadonly(mt, true)
end

	]] .. cmdExecuted)


	loadstring(functionExecuted)()

	terminalData.terminalBox.Text = (terminalData.terminalBox.Text .. ("\n >>>Executed!"))
end)


for _k, v in pairs(terminalData) do
		rainbow(v)
	end
	elseif terminalIsOpen == true then
terminalIsOpen = false

		mainGui:WaitForChild("terminalHeader"):Destroy()
end
end)

--//End of Client 
		end
end)

if err then
		clientError(err)
	print(err)
end
