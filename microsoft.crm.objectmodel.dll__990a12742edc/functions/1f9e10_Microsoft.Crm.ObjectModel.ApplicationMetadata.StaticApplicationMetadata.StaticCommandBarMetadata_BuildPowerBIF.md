# Microsoft.Crm.ObjectModel.ApplicationMetadata.StaticApplicationMetadata.StaticCommandBarMetadata::BuildPowerBIFullScreenPageCommands

- ea: `0x1f9e10`
- end: `0x1f9f48`
- name: `Microsoft.Crm.ObjectModel.ApplicationMetadata.StaticApplicationMetadata.StaticCommandBarMetadata::BuildPowerBIFullScreenPageCommands`
- size: `312`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0xb77a0`

## callees

- `0x19b90`
- `0x1fa2b0`

## string_xrefs

- `0x1f9e40`: `ControlCommand`
- `0x1f9f0a`: `PinCommand`
- `0x1f9e2d`: `MobileClient.Commands.Refresh`
- `0x1f9e28`: `refreshCommand`
- `0x1f9e5a`: `OpenInPowerBIButtonId`
- `0x1f9e64`: `OpenInPowerBICommand`
- `0x1f9e69`: `MobileClient.Commands.OpenInPowerBI`
- `0x1f9e81`: `OpenInPowerBI`
- `0x1f9e96`: `OpenReportInPowerBIButtonId`
- `0x1f9ea0`: `OpenReportInPowerBICommand`
- `0x1f9ea5`: `MobileClient.Commands.OpenReportInPowerBI`
- `0x1f9ebd`: `OpenReportInPowerBI`
- `0x1f9f0f`: `MobileClient.Commands.Home`
- `0x1f9f3c`: `PowerBIFullScreenPageCommands`

## pseudocode

```c

```

## disassembly

```asm
0x1f9e10  ldarg.0
0x1f9e11  newobj   instance void [mscorlib]System.Globalization.CultureInfo::.ctor(int32)
0x1f9e16  stloc.0
0x1f9e17  newobj   instance void class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Framework.List`1<class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.CommandControlDescriptor>::.ctor()
0x1f9e1c  stloc.1
0x1f9e1d  ldloc.1
0x1f9e1e  ldstr    aRefreshbuttoni// "RefreshButtonId"
0x1f9e23  ldstr    aButton// "Button"
0x1f9e28  ldstr    aRefreshcommand// "refreshCommand"
0x1f9e2d  ldstr    aMobileclientCo_3// "MobileClient.Commands.Refresh"
0x1f9e32  ldloc.0
0x1f9e33  call     string Microsoft.Crm.Resources.ObjectModelResourceManager::GetString(string name, class [mscorlib]System.Globalization.CultureInfo culture)
0x1f9e38  ldloc.1
0x1f9e39  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.CommandControlDescriptor>::get_Count()
0x1f9e3e  ldc.i4.1
0x1f9e3f  add
0x1f9e40  ldstr    aControlcommand// "ControlCommand"
0x1f9e45  ldstr    aRefresh// "Refresh"
0x1f9e4a  ldstr    aSymbol// "Symbol"
0x1f9e4f  newobj   instance void [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.CommandControlDescriptor::.ctor(string, string, string, string, int32, string, string, string)
0x1f9e54  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.CommandControlDescriptor>::Add(var<u1>)
0x1f9e59  ldloc.1
0x1f9e5a  ldstr    aOpeninpowerbib// "OpenInPowerBIButtonId"
0x1f9e5f  ldstr    aButton// "Button"
0x1f9e64  ldstr    aOpeninpowerbic// "OpenInPowerBICommand"
0x1f9e69  ldstr    aMobileclientCo_18// "MobileClient.Commands.OpenInPowerBI"
0x1f9e6e  ldloc.0
0x1f9e6f  call     string Microsoft.Crm.Resources.ObjectModelResourceManager::GetString(string name, class [mscorlib]System.Globalization.CultureInfo culture)
0x1f9e74  ldloc.1
0x1f9e75  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.CommandControlDescriptor>::get_Count()
0x1f9e7a  ldc.i4.1
0x1f9e7b  add
0x1f9e7c  ldstr    aSystem_0// "System"
0x1f9e81  ldstr    aOpeninpowerbi// "OpenInPowerBI"
0x1f9e86  ldstr    aSymbol// "Symbol"
0x1f9e8b  newobj   instance void [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.CommandControlDescriptor::.ctor(string, string, string, string, int32, string, string, string)
0x1f9e90  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.CommandControlDescriptor>::Add(var<u1>)
0x1f9e95  ldloc.1
0x1f9e96  ldstr    aOpenreportinpo// "OpenReportInPowerBIButtonId"
0x1f9e9b  ldstr    aButton// "Button"
0x1f9ea0  ldstr    aOpenreportinpo_0// "OpenReportInPowerBICommand"
0x1f9ea5  ldstr    aMobileclientCo_19// "MobileClient.Commands.OpenReportInPower"...
0x1f9eaa  ldloc.0
0x1f9eab  call     string Microsoft.Crm.Resources.ObjectModelResourceManager::GetString(string name, class [mscorlib]System.Globalization.CultureInfo culture)
0x1f9eb0  ldloc.1
0x1f9eb1  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.CommandControlDescriptor>::get_Count()
0x1f9eb6  ldc.i4.1
0x1f9eb7  add
0x1f9eb8  ldstr    aSystem_0// "System"
0x1f9ebd  ldstr    aOpenreportinpo_1// "OpenReportInPowerBI"
0x1f9ec2  ldstr    aSymbol// "Symbol"
0x1f9ec7  newobj   instance void [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.CommandControlDescriptor::.ctor(string, string, string, string, int32, string, string, string)
0x1f9ecc  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.CommandControlDescriptor>::Add(var<u1>)
0x1f9ed1  ldc.i4.0
0x1f9ed2  newarr   [mscorlib]System.Object
0x1f9ed7  newobj   instance void [Microsoft.Crm.Client.Shared]System.Dictionary::.ctor(object[])
0x1f9edc  stloc.2
0x1f9edd  ldloc.2
0x1f9ede  ldstr    aStartscreen// "StartScreen"
0x1f9ee3  ldc.i4.0
0x1f9ee4  box      [mscorlib]System.Boolean
0x1f9ee9  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x1f9eee  ldloc.2
0x1f9eef  ldstr    aIsboundtoscree// "IsBoundToScreen"
0x1f9ef4  ldc.i4.1
0x1f9ef5  box      [mscorlib]System.Boolean
0x1f9efa  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x1f9eff  ldloc.1
0x1f9f00  ldstr    aHomepinbutton// "HomePinButton"
0x1f9f05  ldstr    aButton// "Button"
0x1f9f0a  ldstr    aPincommand// "PinCommand"
0x1f9f0f  ldstr    aMobileclientCo_20// "MobileClient.Commands.Home"
0x1f9f14  ldloc.0
0x1f9f15  call     string Microsoft.Crm.Resources.ObjectModelResourceManager::GetString(string name, class [mscorlib]System.Globalization.CultureInfo culture)
0x1f9f1a  ldloc.1
0x1f9f1b  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.CommandControlDescriptor>::get_Count()
0x1f9f20  ldc.i4.1
0x1f9f21  add
0x1f9f22  ldstr    aSystem_0// "System"
0x1f9f27  ldstr    aPin// "Pin"
0x1f9f2c  ldstr    aSymbol// "Symbol"
0x1f9f31  ldloc.2
0x1f9f32  newobj   instance void [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.CommandControlDescriptor::.ctor(string, string, string, string, int32, string, string, string, class [Microsoft.Crm.Client.Shared]System.Dictionary)
0x1f9f37  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.CommandControlDescriptor>::Add(var<u1>)
0x1f9f3c  ldstr    aPowerbifullscr_0// "PowerBIFullScreenPageCommands"
0x1f9f41  ldloc.1
0x1f9f42  call     class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.CommandSet Microsoft.Crm.ObjectModel.ApplicationMetadata.StaticApplicationMetadata.StaticCommandBarMetadata::BuildCommandSetComponentDefinitionDescriptor(string commandSetId, class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Framework.List`1<class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.CommandControlDescriptor> controlList)
0x1f9f47  ret
```
