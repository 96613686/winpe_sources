# Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ProcessControl::GenerateClientStrings

- ea: `0x38c0`
- end: `0x3ce8`
- name: `Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ProcessControl::GenerateClientStrings`
- size: `1064`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x3620`
- `0x37a0`

## string_xrefs

- `0x38c5`: `{{"inProgress":{0},"locked":{1},"completed":{2},"error":{3},"advance":{4},"back":{5},"slider":{6},"entity":{7},"stage":{8},"status":{9},"active":{10},"noRecords":{11},"available":{12},"selectChild":{13},"untitled":{14},"fillRequiredWarning":{15},"processChangedWarning":{16},"createNew":{17},"finish":{18},"finished":{19},"activeFor":{20},"completedIn":{21},"abortedIn":{22},"lessThanOneMinute":{23},"lessThanOneHour":{24},"lessThanOneDay":{25},"daysWithNoHours":{26},"moreThanOneDay":{27},"minute":{`
- `0x3918`: `ProcessControl.CompletedStage`
- `0x3ad4`: `ProcessControl.CreateNew`
- `0x3b4c`: `ProcessControl.Progress.CompletedIn`

## pseudocode

```c

```

## disassembly

```asm
0x38c0  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x38c5  ldstr    aInprogress0Loc// "{{\"inProgress\":{0},\"locked\":{1},\"c"...
0x38ca  ldc.i4.s 0x23
0x38cc  newarr   [mscorlib]System.Object
0x38d1  dup
0x38d2  ldc.i4.0
0x38d3  ldarg.0
0x38d4  ldfld    class [System.Web.Extensions]System.Web.Script.Serialization.JavaScriptSerializer Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ProcessControl::_serializer
0x38d9  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x38de  ldstr    aProcesscontrol_0// "ProcessControl.InProgressStage"
0x38e3  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x38e8  callvirt instance string [System.Web.Extensions]System.Web.Script.Serialization.JavaScriptSerializer::Serialize(object)
0x38ed  stelem.ref
0x38ee  dup
0x38ef  ldc.i4.1
0x38f0  ldarg.0
0x38f1  ldfld    class [System.Web.Extensions]System.Web.Script.Serialization.JavaScriptSerializer Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ProcessControl::_serializer
0x38f6  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x38fb  ldstr    aProcesscontrol_1// "ProcessControl.LockedStage"
0x3900  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x3905  callvirt instance string [System.Web.Extensions]System.Web.Script.Serialization.JavaScriptSerializer::Serialize(object)
0x390a  stelem.ref
0x390b  dup
0x390c  ldc.i4.2
0x390d  ldarg.0
0x390e  ldfld    class [System.Web.Extensions]System.Web.Script.Serialization.JavaScriptSerializer Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ProcessControl::_serializer
0x3913  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x3918  ldstr    aProcesscontrol_2// "ProcessControl.CompletedStage"
0x391d  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x3922  callvirt instance string [System.Web.Extensions]System.Web.Script.Serialization.JavaScriptSerializer::Serialize(object)
0x3927  stelem.ref
0x3928  dup
0x3929  ldc.i4.3
0x392a  ldarg.0
0x392b  ldfld    class [System.Web.Extensions]System.Web.Script.Serialization.JavaScriptSerializer Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ProcessControl::_serializer
0x3930  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x3935  ldstr    aProcesscontrol_3// "ProcessControl.Error"
0x393a  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x393f  callvirt instance string [System.Web.Extensions]System.Web.Script.Serialization.JavaScriptSerializer::Serialize(object)
0x3944  stelem.ref
0x3945  dup
0x3946  ldc.i4.4
0x3947  ldarg.0
0x3948  ldfld    class [System.Web.Extensions]System.Web.Script.Serialization.JavaScriptSerializer Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ProcessControl::_serializer
0x394d  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x3952  ldstr    aProcesscontrol_4// "ProcessControl.AdvanceTooltip"
0x3957  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x395c  callvirt instance string [System.Web.Extensions]System.Web.Script.Serialization.JavaScriptSerializer::Serialize(object)
0x3961  stelem.ref
0x3962  dup
0x3963  ldc.i4.5
0x3964  ldarg.0
0x3965  ldfld    class [System.Web.Extensions]System.Web.Script.Serialization.JavaScriptSerializer Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ProcessControl::_serializer
0x396a  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x396f  ldstr    aProcesscontrol_5// "ProcessControl.BackTooltip"
0x3974  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x3979  callvirt instance string [System.Web.Extensions]System.Web.Script.Serialization.JavaScriptSerializer::Serialize(object)
0x397e  stelem.ref
0x397f  dup
0x3980  ldc.i4.6
0x3981  ldarg.0
0x3982  ldfld    class [System.Web.Extensions]System.Web.Script.Serialization.JavaScriptSerializer Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ProcessControl::_serializer
0x3987  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x398c  ldstr    aProcesscontrol_6// "ProcessControl.Scroll"
0x3991  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x3996  callvirt instance string [System.Web.Extensions]System.Web.Script.Serialization.JavaScriptSerializer::Serialize(object)
0x399b  stelem.ref
0x399c  dup
0x399d  ldc.i4.7
0x399e  ldarg.0
0x399f  ldfld    class [System.Web.Extensions]System.Web.Script.Serialization.JavaScriptSerializer Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ProcessControl::_serializer
0x39a4  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x39a9  ldstr    aSalesProcessco// "Sales.ProcessControl.Entity"
0x39ae  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x39b3  callvirt instance string [System.Web.Extensions]System.Web.Script.Serialization.JavaScriptSerializer::Serialize(object)
0x39b8  stelem.ref
0x39b9  dup
0x39ba  ldc.i4.8
0x39bb  ldarg.0
0x39bc  ldfld    class [System.Web.Extensions]System.Web.Script.Serialization.JavaScriptSerializer Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ProcessControl::_serializer
0x39c1  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x39c6  ldstr    aSalesProcessco_0// "Sales.ProcessControl.Stage"
0x39cb  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x39d0  callvirt instance string [System.Web.Extensions]System.Web.Script.Serialization.JavaScriptSerializer::Serialize(object)
0x39d5  stelem.ref
0x39d6  dup
0x39d7  ldc.i4.s 9
0x39d9  ldarg.0
0x39da  ldfld    class [System.Web.Extensions]System.Web.Script.Serialization.JavaScriptSerializer Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ProcessControl::_serializer
0x39df  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x39e4  ldstr    aSalesProcessco_1// "Sales.ProcessControl.Status"
0x39e9  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x39ee  callvirt instance string [System.Web.Extensions]System.Web.Script.Serialization.JavaScriptSerializer::Serialize(object)
0x39f3  stelem.ref
0x39f4  dup
0x39f5  ldc.i4.s 0xA
0x39f7  ldarg.0
0x39f8  ldfld    class [System.Web.Extensions]System.Web.Script.Serialization.JavaScriptSerializer Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ProcessControl::_serializer
0x39fd  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x3a02  ldstr    aSalesProcessco_2// "Sales.ProcessControl.Active"
0x3a07  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x3a0c  callvirt instance string [System.Web.Extensions]System.Web.Script.Serialization.JavaScriptSerializer::Serialize(object)
0x3a11  stelem.ref
0x3a12  dup
0x3a13  ldc.i4.s 0xB
0x3a15  ldarg.0
0x3a16  ldfld    class [System.Web.Extensions]System.Web.Script.Serialization.JavaScriptSerializer Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ProcessControl::_serializer
0x3a1b  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x3a20  ldstr    aSalesProcessco_3// "Sales.ProcessControl.NoRecords"
0x3a25  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x3a2a  callvirt instance string [System.Web.Extensions]System.Web.Script.Serialization.JavaScriptSerializer::Serialize(object)
0x3a2f  stelem.ref
0x3a30  dup
0x3a31  ldc.i4.s 0xC
0x3a33  ldarg.0
0x3a34  ldfld    class [System.Web.Extensions]System.Web.Script.Serialization.JavaScriptSerializer Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ProcessControl::_serializer
0x3a39  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x3a3e  ldstr    aSalesProcessco_4// "Sales.ProcessControl.Available"
0x3a43  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x3a48  callvirt instance string [System.Web.Extensions]System.Web.Script.Serialization.JavaScriptSerializer::Serialize(object)
0x3a4d  stelem.ref
0x3a4e  dup
0x3a4f  ldc.i4.s 0xD
0x3a51  ldarg.0
0x3a52  ldfld    class [System.Web.Extensions]System.Web.Script.Serialization.JavaScriptSerializer Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ProcessControl::_serializer
0x3a57  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x3a5c  ldstr    aSalesProcessco_5// "Sales.ProcessControl.SelectChild"
0x3a61  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x3a66  callvirt instance string [System.Web.Extensions]System.Web.Script.Serialization.JavaScriptSerializer::Serialize(object)
0x3a6b  stelem.ref
0x3a6c  dup
0x3a6d  ldc.i4.s 0xE
0x3a6f  ldarg.0
0x3a70  ldfld    class [System.Web.Extensions]System.Web.Script.Serialization.JavaScriptSerializer Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ProcessControl::_serializer
0x3a75  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x3a7a  ldstr    aSalesProcessco_6// "Sales.ProcessControl.Untitled"
0x3a7f  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x3a84  callvirt instance string [System.Web.Extensions]System.Web.Script.Serialization.JavaScriptSerializer::Serialize(object)
0x3a89  stelem.ref
0x3a8a  dup
0x3a8b  ldc.i4.s 0xF
0x3a8d  ldarg.0
0x3a8e  ldfld    class [System.Web.Extensions]System.Web.Script.Serialization.JavaScriptSerializer Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ProcessControl::_serializer
0x3a93  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x3a98  ldstr    aProcesscontrol_7// "ProcessControl.RequiredStepWarningBar"
0x3a9d  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x3aa2  callvirt instance string [System.Web.Extensions]System.Web.Script.Serialization.JavaScriptSerializer::Serialize(object)
0x3aa7  stelem.ref
0x3aa8  dup
0x3aa9  ldc.i4.s 0x10
0x3aab  ldarg.0
0x3aac  ldfld    class [System.Web.Extensions]System.Web.Script.Serialization.JavaScriptSerializer Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ProcessControl::_serializer
0x3ab1  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x3ab6  ldstr    aProcesscontrol_8// "ProcessControl.Warnings.ProcessWasChang"...
0x3abb  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x3ac0  callvirt instance string [System.Web.Extensions]System.Web.Script.Serialization.JavaScriptSerializer::Serialize(object)
0x3ac5  stelem.ref
0x3ac6  dup
0x3ac7  ldc.i4.s 0x11
0x3ac9  ldarg.0
0x3aca  ldfld    class [System.Web.Extensions]System.Web.Script.Serialization.JavaScriptSerializer Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ProcessControl::_serializer
0x3acf  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x3ad4  ldstr    aProcesscontrol_9// "ProcessControl.CreateNew"
0x3ad9  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x3ade  callvirt instance string [System.Web.Extensions]System.Web.Script.Serialization.JavaScriptSerializer::Serialize(object)
0x3ae3  stelem.ref
0x3ae4  dup
0x3ae5  ldc.i4.s 0x12
0x3ae7  ldarg.0
0x3ae8  ldfld    class [System.Web.Extensions]System.Web.Script.Serialization.JavaScriptSerializer Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ProcessControl::_serializer
0x3aed  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x3af2  ldstr    aProcesscontrol_10// "ProcessControl.FinishTooltip"
0x3af7  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x3afc  callvirt instance string [System.Web.Extensions]System.Web.Script.Serialization.JavaScriptSerializer::Serialize(object)
0x3b01  stelem.ref
0x3b02  dup
0x3b03  ldc.i4.s 0x13
0x3b05  ldarg.0
0x3b06  ldfld    class [System.Web.Extensions]System.Web.Script.Serialization.JavaScriptSerializer Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ProcessControl::_serializer
0x3b0b  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x3b10  ldstr    aProcesscontrol_11// "ProcessControl.FinishedTooltip"
0x3b15  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x3b1a  callvirt instance string [System.Web.Extensions]System.Web.Script.Serialization.JavaScriptSerializer::Serialize(object)
0x3b1f  stelem.ref
0x3b20  dup
0x3b21  ldc.i4.s 0x14
0x3b23  ldarg.0
0x3b24  ldfld    class [System.Web.Extensions]System.Web.Script.Serialization.JavaScriptSerializer Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ProcessControl::_serializer
0x3b29  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x3b2e  ldstr    aProcesscontrol_12// "ProcessControl.Progress.ActiveFor"
0x3b33  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x3b38  callvirt instance string [System.Web.Extensions]System.Web.Script.Serialization.JavaScriptSerializer::Serialize(object)
0x3b3d  stelem.ref
0x3b3e  dup
0x3b3f  ldc.i4.s 0x15
0x3b41  ldarg.0
0x3b42  ldfld    class [System.Web.Extensions]System.Web.Script.Serialization.JavaScriptSerializer Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ProcessControl::_serializer
0x3b47  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x3b4c  ldstr    aProcesscontrol_13// "ProcessControl.Progress.CompletedIn"
0x3b51  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x3b56  callvirt instance string [System.Web.Extensions]System.Web.Script.Serialization.JavaScriptSerializer::Serialize(object)
0x3b5b  stelem.ref
0x3b5c  dup
0x3b5d  ldc.i4.s 0x16
0x3b5f  ldarg.0
0x3b60  ldfld    class [System.Web.Extensions]System.Web.Script.Serialization.JavaScriptSerializer Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ProcessControl::_serializer
0x3b65  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x3b6a  ldstr    aProcesscontrol_14// "ProcessControl.Progress.AbortedIn"
0x3b6f  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x3b74  callvirt instance string [System.Web.Extensions]System.Web.Script.Serialization.JavaScriptSerializer::Serialize(object)
0x3b79  stelem.ref
0x3b7a  dup
0x3b7b  ldc.i4.s 0x17
0x3b7d  ldarg.0
0x3b7e  ldfld    class [System.Web.Extensions]System.Web.Script.Serialization.JavaScriptSerializer Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ProcessControl::_serializer
0x3b83  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x3b88  ldstr    aProcesscontrol_15// "ProcessControl.Progress.LessThanOneMinu"...
0x3b8d  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x3b92  callvirt instance string [System.Web.Extensions]System.Web.Script.Serialization.JavaScriptSerializer::Serialize(object)
0x3b97  stelem.ref
0x3b98  dup
0x3b99  ldc.i4.s 0x18
0x3b9b  ldarg.0
0x3b9c  ldfld    class [System.Web.Extensions]System.Web.Script.Serialization.JavaScriptSerializer Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ProcessControl::_serializer
0x3ba1  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x3ba6  ldstr    aProcesscontrol_16// "ProcessControl.Progress.LessThanOneHour"
0x3bab  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x3bb0  callvirt instance string [System.Web.Extensions]System.Web.Script.Serialization.JavaScriptSerializer::Serialize(object)
0x3bb5  stelem.ref
0x3bb6  dup
0x3bb7  ldc.i4.s 0x19
0x3bb9  ldarg.0
0x3bba  ldfld    class [System.Web.Extensions]System.Web.Script.Serialization.JavaScriptSerializer Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ProcessControl::_serializer
0x3bbf  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x3bc4  ldstr    aProcesscontrol_17// "ProcessControl.Progress.LessThanOneDay"
0x3bc9  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x3bce  callvirt instance string [System.Web.Extensions]System.Web.Script.Serialization.JavaScriptSerializer::Serialize(object)
0x3bd3  stelem.ref
0x3bd4  dup
0x3bd5  ldc.i4.s 0x1A
0x3bd7  ldarg.0
0x3bd8  ldfld    class [System.Web.Extensions]System.Web.Script.Serialization.JavaScriptSerializer Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ProcessControl::_serializer
0x3bdd  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x3be2  ldstr    aProcesscontrol_18// "ProcessControl.Progress.DaysWithNoHours"
0x3be7  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x3bec  callvirt instance string [System.Web.Extensions]System.Web.Script.Serialization.JavaScriptSerializer::Serialize(object)
0x3bf1  stelem.ref
0x3bf2  dup
0x3bf3  ldc.i4.s 0x1B
0x3bf5  ldarg.0
0x3bf6  ldfld    class [System.Web.Extensions]System.Web.Script.Serialization.JavaScriptSerializer Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ProcessControl::_serializer
0x3bfb  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x3c00  ldstr    aProcesscontrol_19// "ProcessControl.Progress.MoreThanOneDay"
0x3c05  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x3c0a  callvirt instance string [System.Web.Extensions]System.Web.Script.Serialization.JavaScriptSerializer::Serialize(object)
0x3c0f  stelem.ref
0x3c10  dup
0x3c11  ldc.i4.s 0x1C
0x3c13  ldarg.0
0x3c14  ldfld    class [System.Web.Extensions]System.Web.Script.Serialization.JavaScriptSerializer Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ProcessControl::_serializer
0x3c19  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x3c1e  ldstr    aProcesscontrol_20// "ProcessControl.Progress.Minute"
0x3c23  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x3c28  callvirt instance string [System.Web.Extensions]System.Web.Script.Serialization.JavaScriptSerializer::Serialize(object)
0x3c2d  stelem.ref
0x3c2e  dup
0x3c2f  ldc.i4.s 0x1D
0x3c31  ldarg.0
0x3c32  ldfld    class [System.Web.Extensions]System.Web.Script.Serialization.JavaScriptSerializer Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ProcessControl::_serializer
0x3c37  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x3c3c  ldstr    aProcesscontrol_21// "ProcessControl.Progress.Minutes"
0x3c41  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x3c46  callvirt instance string [System.Web.Extensions]System.Web.Script.Serialization.JavaScriptSerializer::Serialize(object)
0x3c4b  stelem.ref
0x3c4c  dup
0x3c4d  ldc.i4.s 0x1E
0x3c4f  ldarg.0
0x3c50  ldfld    class [System.Web.Extensions]System.Web.Script.Serialization.JavaScriptSerializer Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ProcessControl::_serializer
0x3c55  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x3c5a  ldstr    aProcesscontrol_22// "ProcessControl.Progress.Hour"
0x3c5f  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x3c64  callvirt instance string [System.Web.Extensions]System.Web.Script.Serialization.JavaScriptSerializer::Serialize(object)
0x3c69  stelem.ref
0x3c6a  dup
0x3c6b  ldc.i4.s 0x1F
0x3c6d  ldarg.0
0x3c6e  ldfld    class [System.Web.Extensions]System.Web.Script.Serialization.JavaScriptSerializer Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ProcessControl::_serializer
0x3c73  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x3c78  ldstr    aProcesscontrol_23// "ProcessControl.Progress.Hours"
0x3c7d  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x3c82  callvirt instance string [System.Web.Extensions]System.Web.Script.Serialization.JavaScriptSerializer::Serialize(object)
0x3c87  stelem.ref
0x3c88  dup
0x3c89  ldc.i4.s 0x20
0x3c8b  ldarg.0
0x3c8c  ldfld    class [System.Web.Extensions]System.Web.Script.Serialization.JavaScriptSerializer Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ProcessControl::_serializer
0x3c91  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x3c96  ldstr    aProcesscontrol_24// "ProcessControl.Progress.Day"
0x3c9b  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x3ca0  callvirt instance string [System.Web.Extensions]System.Web.Script.Serialization.JavaScriptSerializer::Serialize(object)
  ... truncated ...
```
