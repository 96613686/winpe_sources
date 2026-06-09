# Microsoft.Crm.ObjectModel.ApplicationMetadata.StaticApplicationMetadata.StaticCommandBarMetadata::BuildProxyProcessControlCommands

- ea: `0x1fa4e0`
- end: `0x1fa681`
- name: `Microsoft.Crm.ObjectModel.ApplicationMetadata.StaticApplicationMetadata.StaticCommandBarMetadata::BuildProxyProcessControlCommands`
- size: `417`
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

- `0x1fa545`: `OpenSwitchProcessDialogCommand`
- `0x1fa4e7`: `MobileClient.Commands.SwitchProcess`
- `0x1fa4f3`: `MobileClient.Commands.SetActiveStage`
- `0x1fa4ff`: `MobileClient.Commands.BackStage`
- `0x1fa50b`: `MobileClient.Commands.AbandonProcess`
- `0x1fa518`: `MobileClient.Commands.FinishProcess`
- `0x1fa525`: `MobileClient.Commands.ReactivateProcess`
- `0x1fa579`: `BackProcessStageCommand`
- `0x1fa5ad`: `SetActiveStageCommand`
- `0x1fa5e1`: `AbandonProcessCommand`
- `0x1fa616`: `FinishProcessCommand`
- `0x1fa64b`: `ReactivateProcessCommand`
- `0x1fa674`: `ProxyProcessControlCommands`

## pseudocode

```c

```

## disassembly

```asm
0x1fa4e0  ldarg.0
0x1fa4e1  newobj   instance void [mscorlib]System.Globalization.CultureInfo::.ctor(int32)
0x1fa4e6  stloc.0
0x1fa4e7  ldstr    aMobileclientCo_25// "MobileClient.Commands.SwitchProcess"
0x1fa4ec  ldloc.0
0x1fa4ed  call     string Microsoft.Crm.Resources.ObjectModelResourceManager::GetString(string name, class [mscorlib]System.Globalization.CultureInfo culture)
0x1fa4f2  stloc.1
0x1fa4f3  ldstr    aMobileclientCo_26// "MobileClient.Commands.SetActiveStage"
0x1fa4f8  ldloc.0
0x1fa4f9  call     string Microsoft.Crm.Resources.ObjectModelResourceManager::GetString(string name, class [mscorlib]System.Globalization.CultureInfo culture)
0x1fa4fe  stloc.2
0x1fa4ff  ldstr    aMobileclientCo_27// "MobileClient.Commands.BackStage"
0x1fa504  ldloc.0
0x1fa505  call     string Microsoft.Crm.Resources.ObjectModelResourceManager::GetString(string name, class [mscorlib]System.Globalization.CultureInfo culture)
0x1fa50a  stloc.3
0x1fa50b  ldstr    aMobileclientCo_28// "MobileClient.Commands.AbandonProcess"
0x1fa510  ldloc.0
0x1fa511  call     string Microsoft.Crm.Resources.ObjectModelResourceManager::GetString(string name, class [mscorlib]System.Globalization.CultureInfo culture)
0x1fa516  stloc.s  4
0x1fa518  ldstr    aMobileclientCo_29// "MobileClient.Commands.FinishProcess"
0x1fa51d  ldloc.0
0x1fa51e  call     string Microsoft.Crm.Resources.ObjectModelResourceManager::GetString(string name, class [mscorlib]System.Globalization.CultureInfo culture)
0x1fa523  stloc.s  5
0x1fa525  ldstr    aMobileclientCo_30// "MobileClient.Commands.ReactivateProcess"
0x1fa52a  ldloc.0
0x1fa52b  call     string Microsoft.Crm.Resources.ObjectModelResourceManager::GetString(string name, class [mscorlib]System.Globalization.CultureInfo culture)
0x1fa530  stloc.s  6
0x1fa532  newobj   instance void class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Framework.List`1<class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.CommandControlDescriptor>::.ctor()
0x1fa537  stloc.s  7
0x1fa539  ldloc.s  7
0x1fa53b  ldstr    aProcesscontrol_4// "ProcessControlsButton"
0x1fa540  ldstr    aButton// "Button"
0x1fa545  ldstr    aOpenswitchproc// "OpenSwitchProcessDialogCommand"
0x1fa54a  ldloc.1
0x1fa54b  ldloc.s  7
0x1fa54d  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.CommandControlDescriptor>::get_Count()
0x1fa552  ldc.i4.1
0x1fa553  add
0x1fa554  ldstr    aSystem_0// "System"
0x1fa559  ldstr    aSwitchprocess// "SwitchProcess"
0x1fa55e  ldstr    aSymbol// "Symbol"
0x1fa563  newobj   instance void [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.CommandControlDescriptor::.ctor(string, string, string, string, int32, string, string, string)
0x1fa568  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.CommandControlDescriptor>::Add(var<u1>)
0x1fa56d  ldloc.s  7
0x1fa56f  ldstr    aBackprocesssta// "BackProcessStage"
0x1fa574  ldstr    aButton// "Button"
0x1fa579  ldstr    aBackprocesssta_0// "BackProcessStageCommand"
0x1fa57e  ldloc.3
0x1fa57f  ldloc.s  7
0x1fa581  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.CommandControlDescriptor>::get_Count()
0x1fa586  ldc.i4.1
0x1fa587  add
0x1fa588  ldstr    aSystem_0// "System"
0x1fa58d  ldstr    aBackbutton// "BackButton"
0x1fa592  ldstr    aSymbol// "Symbol"
0x1fa597  newobj   instance void [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.CommandControlDescriptor::.ctor(string, string, string, string, int32, string, string, string)
0x1fa59c  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.CommandControlDescriptor>::Add(var<u1>)
0x1fa5a1  ldloc.s  7
0x1fa5a3  ldstr    aSetactivestage// "SetActiveStage"
0x1fa5a8  ldstr    aButton// "Button"
0x1fa5ad  ldstr    aSetactivestage_0// "SetActiveStageCommand"
0x1fa5b2  ldloc.2
0x1fa5b3  ldloc.s  7
0x1fa5b5  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.CommandControlDescriptor>::get_Count()
0x1fa5ba  ldc.i4.1
0x1fa5bb  add
0x1fa5bc  ldstr    aSystem_0// "System"
0x1fa5c1  ldstr    aSetactivebutto// "SetActiveButton"
0x1fa5c6  ldstr    aSymbol// "Symbol"
0x1fa5cb  newobj   instance void [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.CommandControlDescriptor::.ctor(string, string, string, string, int32, string, string, string)
0x1fa5d0  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.CommandControlDescriptor>::Add(var<u1>)
0x1fa5d5  ldloc.s  7
0x1fa5d7  ldstr    aAbandon// "Abandon"
0x1fa5dc  ldstr    aButton// "Button"
0x1fa5e1  ldstr    aAbandonprocess// "AbandonProcessCommand"
0x1fa5e6  ldloc.s  4
0x1fa5e8  ldloc.s  7
0x1fa5ea  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.CommandControlDescriptor>::get_Count()
0x1fa5ef  ldc.i4.1
0x1fa5f0  add
0x1fa5f1  ldstr    aSystem_0// "System"
0x1fa5f6  ldstr    aAbandonprocess_0// "AbandonProcess"
0x1fa5fb  ldstr    aSymbol// "Symbol"
0x1fa600  newobj   instance void [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.CommandControlDescriptor::.ctor(string, string, string, string, int32, string, string, string)
0x1fa605  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.CommandControlDescriptor>::Add(var<u1>)
0x1fa60a  ldloc.s  7
0x1fa60c  ldstr    aFinish// "Finish"
0x1fa611  ldstr    aButton// "Button"
0x1fa616  ldstr    aFinishprocessc// "FinishProcessCommand"
0x1fa61b  ldloc.s  5
0x1fa61d  ldloc.s  7
0x1fa61f  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.CommandControlDescriptor>::get_Count()
0x1fa624  ldc.i4.1
0x1fa625  add
0x1fa626  ldstr    aSystem_0// "System"
0x1fa62b  ldstr    aFinishprocess// "FinishProcess"
0x1fa630  ldstr    aSymbol// "Symbol"
0x1fa635  newobj   instance void [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.CommandControlDescriptor::.ctor(string, string, string, string, int32, string, string, string)
0x1fa63a  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.CommandControlDescriptor>::Add(var<u1>)
0x1fa63f  ldloc.s  7
0x1fa641  ldstr    aReactivate// "Reactivate"
0x1fa646  ldstr    aButton// "Button"
0x1fa64b  ldstr    aReactivateproc// "ReactivateProcessCommand"
0x1fa650  ldloc.s  6
0x1fa652  ldloc.s  7
0x1fa654  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.CommandControlDescriptor>::get_Count()
0x1fa659  ldc.i4.1
0x1fa65a  add
0x1fa65b  ldstr    aSystem_0// "System"
0x1fa660  ldstr    aReactivateproc_0// "ReactivateProcess"
0x1fa665  ldstr    aSymbol// "Symbol"
0x1fa66a  newobj   instance void [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.CommandControlDescriptor::.ctor(string, string, string, string, int32, string, string, string)
0x1fa66f  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.CommandControlDescriptor>::Add(var<u1>)
0x1fa674  ldstr    aProxyprocessco_0// "ProxyProcessControlCommands"
0x1fa679  ldloc.s  7
0x1fa67b  call     class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.CommandSet Microsoft.Crm.ObjectModel.ApplicationMetadata.StaticApplicationMetadata.StaticCommandBarMetadata::BuildCommandSetComponentDefinitionDescriptor(string commandSetId, class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Framework.List`1<class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.CommandControlDescriptor> controlList)
0x1fa680  ret
```
