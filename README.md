local OrionLib = loadstring(game:HttpGet(('https://raw.githubusercontent.com/shlexware/Orion/main/source')))()

local Window = OrionLib:MakeWindow({Name = "blackhub", HidePremium = false, lntroText = "Goldenhub", SaveConfig = true, ConfigFolder = "OrionTest"})

local Tab = Window:MakeTab({

	Name = "Vehicle Legends",

	Icon = "rbxassetid://4483345998",

	PremiumOnly = false

})

OrionLib:MakeNotification({

	Name = "👍",

	Content = "ขอให้สนุก🥰",

	Image = "rbxassetid://4483345998",

	Time = 5

})

Tab:AddButton({

	Name = "บูสรถ🏍️🏍️",

	Callback = function()

      		

function getcar()

    for i, v in pairs(game:GetService("Workspace").Vehicles:GetChildren()) do 

        if v.Name == game:GetService("Players").LocalPlayer.Name.."'s Car" then

            return v 

        end

    end

end

 

 

tuneNew = {

	MaxSteerRadius = 40, 

    SteerSpeed = 5, 

    SteerSpeedReturn = 10, 

    RelaxTorque = 2000, 

    BrakeTorque = 10000, 

    HandbrakeTorque = 40000, 

    MaxRPM = 10000, 

    IdleRPM = 1000, 

    NoThrottleSoundMultiplier = 0.7, 

    ThrottleSoundMultiplier = 1.2, 

    MinVolume = 3, 

    MaxVolume = 6, 

    UpShiftTime = 0.0001, 

    DownShiftTime = 0.0001, 

    DownShiftVolumeMultiplier = 1.2, 

    UpShiftVolumeMultiplier = 0.7, 

    MidShiftTorque = 1000, 

    FrontFriction = 1, 

    RearFriction = 1.2, 

    BurnoutFriction = 0.4, 

    BurnoutTorque = 30000, 

    WorldSteerForce = 20000, 

    LaunchControlEnabled = true, 

    LaunchControlRPMHoldMulti = 0.8, 

    Gears = { 

  {-120, 4500}, -- Reverse gear

  {0, 4500}, -- Neutral gear

  {111, 2700}, -- 1st gear

  {183, 2300}, -- 2nd gear

  {276, 2000}, -- 3rd gear

  {381, 1700}, -- 4th gear

  {474, 1300}, -- 5th gear

  {567, 1000}, -- 6th gear

}

};

 

 

local MyForce = getcar().Weight.boostForce:Clone()

MyForce.Name = "MyBoost"

MyForce.Parent = getcar().Weight.boostForce.Parent

 

local tune = require(getcar().Tune)

 

for i, v in pairs(tuneNew) do 

    tune[i] = v

end

 

function boost()

    if getcar() then 

        getcar().Weight.MyBoost.Force = getcar().Weight.CFrame.LookVector * 20000

    end

end

 

 

uis.InputBegan:Connect(function(inpt)

	if inpt.KeyCode == Enum.KeyCode.W then

		holdingw = true

	end

end)

 

uis.InputEnded:Connect(function(inpt)

	if inpt.KeyCode == Enum.KeyCode.W then

		holdingw = false

	end

end)

 

while task.wait() do 

	if holdingw then

		boost()

	end

end

  	end    

})

OrionLib:Init()...
