# Microsoft.Crm.ObjectModel.ApplicationMetadata.StaticApplicationMetadata.StaticCommandBarMetadata::BuildWorkspaceCommands

- ea: `0x1f9530`
- end: `0x1f96be`
- name: `Microsoft.Crm.ObjectModel.ApplicationMetadata.StaticApplicationMetadata.StaticCommandBarMetadata::BuildWorkspaceCommands`
- size: `398`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0xb77a0`

## callees

- `0x19b90`
- `0xbd040`
- `0x1f9530`
- `0x1f96c0`
- `0x1f9760`
- `0x1f99b0`
- `0x1fa2b0`
- `0x1fa2c0`

## string_xrefs

- `0x1f958b`: `MobileClient.Commands.Workspace.SnapShot`
- `0x1f95a2`: `MemorySnapshotCommand`
- `0x1f95cb`: `MobileClient.Commands.Workspace.Diagnostics`
- `0x1f95e3`: `ShowDiagnosticsReportCommand`
- `0x1f9562`: `ControlCommand`
- `0x1f953d`: `MobileClient.Commands.Refresh`
- `0x1f9554`: `refreshCommand`
- `0x1f9618`: `MobileClient.Commands.Workspace.LearningPath`
- `0x1f9630`: `GuidedHelpCommand`
- `0x1f9659`: `MobileClient.Commands.Workspace.LearningPath_ContentLibrary`
- `0x1f9671`: `ContentLibraryCommand`
- `0x1f969c`: `WorkspaceCommands`
- `0x1f96a8`: `WorkspaceCommands`

## pseudocode

```c

```

## disassembly

```asm
0x1f9530  newobj   instance void class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Framework.List`1<class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.CommandControlDescriptor>::.ctor()
0x1f9535  stloc.0
0x1f9536  ldarg.0
0x1f9537  newobj   instance void [mscorlib]System.Globalization.CultureInfo::.ctor(int32)
0x1f953c  stloc.1
0x1f953d  ldstr    aMobileclientCo_3// "MobileClient.Commands.Refresh"
0x1f9542  ldloc.1
0x1f9543  call     string Microsoft.Crm.Resources.ObjectModelResourceManager::GetString(string name, class [mscorlib]System.Globalization.CultureInfo culture)
0x1f9548  stloc.2
0x1f9549  ldloc.0
0x1f954a  ldstr    aRefreshbutton// "RefreshButton"
0x1f954f  ldstr    aButton// "Button"
0x1f9554  ldstr    aRefreshcommand// "refreshCommand"
0x1f9559  ldloc.2
0x1f955a  ldloc.0
0x1f955b  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.CommandControlDescriptor>::get_Count()
0x1f9560  ldc.i4.1
0x1f9561  add
0x1f9562  ldstr    aControlcommand// "ControlCommand"
0x1f9567  ldstr    aRefresh// "Refresh"
0x1f956c  ldstr    aSymbol// "Symbol"
0x1f9571  ldnull
0x1f9572  ldloca.s 5
0x1f9574  initobj  [mscorlib]System.Guid
0x1f957a  ldloc.s  5
0x1f957c  call     bool Microsoft.Crm.ObjectModel.ConverterUtilities::IsMocaOfflineFeatureAvailable([opt] valuetype [mscorlib]System.Guid organizationId)
0x1f9581  newobj   instance void [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.CommandControlDescriptor::.ctor(string, string, string, string, int32, string, string, string, class [Microsoft.Crm.Client.Shared]System.Dictionary, bool)
0x1f9586  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.CommandControlDescriptor>::Add(var<u1>)
0x1f958b  ldstr    aMobileclientCo_1// "MobileClient.Commands.Workspace.SnapSho"...
0x1f9590  ldloc.1
0x1f9591  call     string Microsoft.Crm.Resources.ObjectModelResourceManager::GetString(string name, class [mscorlib]System.Globalization.CultureInfo culture)
0x1f9596  stloc.3
0x1f9597  ldloc.0
0x1f9598  ldstr    aSnapshotbutton// "SnapshotButton"
0x1f959d  ldstr    aButton// "Button"
0x1f95a2  ldstr    aMemorysnapshot_0// "MemorySnapshotCommand"
0x1f95a7  ldloc.3
0x1f95a8  ldloc.0
0x1f95a9  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.CommandControlDescriptor>::get_Count()
0x1f95ae  ldc.i4.1
0x1f95af  add
0x1f95b0  ldstr    aSystem_0// "System"
0x1f95b5  ldstr    aDefault// "Default"
0x1f95ba  ldstr    aSymbol// "Symbol"
0x1f95bf  ldnull
0x1f95c0  ldc.i4.1
0x1f95c1  newobj   instance void [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.CommandControlDescriptor::.ctor(string, string, string, string, int32, string, string, string, class [Microsoft.Crm.Client.Shared]System.Dictionary, bool)
0x1f95c6  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.CommandControlDescriptor>::Add(var<u1>)
0x1f95cb  ldstr    aMobileclientCo_2// "MobileClient.Commands.Workspace.Diagnos"...
0x1f95d0  ldloc.1
0x1f95d1  call     string Microsoft.Crm.Resources.ObjectModelResourceManager::GetString(string name, class [mscorlib]System.Globalization.CultureInfo culture)
0x1f95d6  stloc.s  4
0x1f95d8  ldloc.0
0x1f95d9  ldstr    aDiagnosticsrep// "DiagnosticsReportButton"
0x1f95de  ldstr    aButton// "Button"
0x1f95e3  ldstr    aShowdiagnostic// "ShowDiagnosticsReportCommand"
0x1f95e8  ldloc.s  4
0x1f95ea  ldloc.0
0x1f95eb  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.CommandControlDescriptor>::get_Count()
0x1f95f0  ldc.i4.1
0x1f95f1  add
0x1f95f2  ldstr    aSystem_0// "System"
0x1f95f7  ldstr    aDefault// "Default"
0x1f95fc  ldstr    aSymbol// "Symbol"
0x1f9601  ldnull
0x1f9602  ldc.i4.1
0x1f9603  newobj   instance void [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.CommandControlDescriptor::.ctor(string, string, string, string, int32, string, string, string, class [Microsoft.Crm.Client.Shared]System.Dictionary, bool)
0x1f9608  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.CommandControlDescriptor>::Add(var<u1>)
0x1f960d  call     bool Microsoft.Crm.ObjectModel.ApplicationMetadata.StaticApplicationMetadata.StaticCommandBarMetadata::IsGuidedHelpSoultionInstalled()
0x1f9612  dup
0x1f9613  brfalse  loc_1F969A
0x1f9618  ldstr    aMobileclientCo_13// "MobileClient.Commands.Workspace.Learnin"...
0x1f961d  ldloc.1
0x1f961e  call     string Microsoft.Crm.Resources.ObjectModelResourceManager::GetString(string name, class [mscorlib]System.Globalization.CultureInfo culture)
0x1f9623  stloc.s  6
0x1f9625  ldloc.0
0x1f9626  ldstr    aGuidedhelpbutt// "GuidedHelpButton"
0x1f962b  ldstr    aButton// "Button"
0x1f9630  ldstr    aGuidedhelpcomm// "GuidedHelpCommand"
0x1f9635  ldloc.s  6
0x1f9637  ldloc.0
0x1f9638  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.CommandControlDescriptor>::get_Count()
0x1f963d  ldc.i4.1
0x1f963e  add
0x1f963f  ldstr    aWebresource// "WebResource"
0x1f9644  ldstr    aDefault// "Default"
0x1f9649  ldstr    aSymbol// "Symbol"
0x1f964e  ldnull
0x1f964f  newobj   instance void [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.CommandControlDescriptor::.ctor(string, string, string, string, int32, string, string, string, class [Microsoft.Crm.Client.Shared]System.Dictionary)
0x1f9654  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.CommandControlDescriptor>::Add(var<u1>)
0x1f9659  ldstr    aMobileclientCo_14// "MobileClient.Commands.Workspace.Learnin"...
0x1f965e  ldloc.1
0x1f965f  call     string Microsoft.Crm.Resources.ObjectModelResourceManager::GetString(string name, class [mscorlib]System.Globalization.CultureInfo culture)
0x1f9664  stloc.s  7
0x1f9666  ldloc.0
0x1f9667  ldstr    aContentlibrary// "ContentLibraryButton"
0x1f966c  ldstr    aButton// "Button"
0x1f9671  ldstr    aContentlibrary_0// "ContentLibraryCommand"
0x1f9676  ldloc.s  7
0x1f9678  ldloc.0
0x1f9679  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.CommandControlDescriptor>::get_Count()
0x1f967e  ldc.i4.1
0x1f967f  add
0x1f9680  ldstr    aWebresource// "WebResource"
0x1f9685  ldstr    aDefault// "Default"
0x1f968a  ldstr    aSymbol// "Symbol"
0x1f968f  ldnull
0x1f9690  newobj   instance void [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.CommandControlDescriptor::.ctor(string, string, string, string, int32, string, string, string, class [Microsoft.Crm.Client.Shared]System.Dictionary)
0x1f9695  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.CommandControlDescriptor>::Add(var<u1>)
0x1f969a  brtrue.s loc_1F96A8
0x1f969c  ldstr    aWorkspacecomma// "WorkspaceCommands"
0x1f96a1  ldloc.0
0x1f96a2  call     class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.CommandSet Microsoft.Crm.ObjectModel.ApplicationMetadata.StaticApplicationMetadata.StaticCommandBarMetadata::BuildCommandSetComponentDefinitionDescriptor(string commandSetId, class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Framework.List`1<class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.CommandControlDescriptor> controlList)
0x1f96a7  ret
0x1f96a8  ldstr    aWorkspacecomma// "WorkspaceCommands"
0x1f96ad  ldloc.0
0x1f96ae  call     class [Microsoft.Crm.Client.Shared]System.Dictionary Microsoft.Crm.ObjectModel.ApplicationMetadata.StaticApplicationMetadata.StaticCommandBarMetadata::BuildGuidedHelpCommand()
0x1f96b3  call     class [Microsoft.Crm.Client.Shared]System.Dictionary Microsoft.Crm.ObjectModel.ApplicationMetadata.StaticApplicationMetadata.StaticCommandBarMetadata::BuildGuidedHelpCommandRules()
0x1f96b8  call     class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.CommandSet Microsoft.Crm.ObjectModel.ApplicationMetadata.StaticApplicationMetadata.StaticCommandBarMetadata::BuildCommandSetComponentDefinitionDescriptor(string commandSetId, class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Framework.List`1<class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.CommandControlDescriptor> controlList, class [Microsoft.Crm.Client.Shared]System.Dictionary commandList, class [Microsoft.Crm.Client.Shared]System.Dictionary commandRules)
0x1f96bd  ret
```
