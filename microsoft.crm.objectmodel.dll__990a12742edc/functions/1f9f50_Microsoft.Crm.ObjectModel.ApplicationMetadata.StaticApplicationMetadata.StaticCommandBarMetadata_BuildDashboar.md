# Microsoft.Crm.ObjectModel.ApplicationMetadata.StaticApplicationMetadata.StaticCommandBarMetadata::BuildDashboardCommands

- ea: `0x1f9f50`
- end: `0x1fa2ad`
- name: `Microsoft.Crm.ObjectModel.ApplicationMetadata.StaticApplicationMetadata.StaticCommandBarMetadata::BuildDashboardCommands`
- size: `861`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0xb77a0`

## callees

- `0x19b90`
- `0xbd040`
- `0x1f96c0`
- `0x1f9760`
- `0x1f99b0`
- `0x1f9f50`
- `0x1fa2b0`
- `0x1fa2c0`
- `0x1fa480`

## string_xrefs

- `0x1fa114`: `OpenInBrowserCommand`
- `0x1fa200`: `MobileClient.Commands.Workspace.SnapShot`
- `0x1fa218`: `MemorySnapshotCommand`
- `0x1fa242`: `MobileClient.Commands.Workspace.Diagnostics`
- `0x1fa25a`: `ShowDiagnosticsReportCommand`
- `0x1fa0b5`: `ControlCommand`
- `0x1fa08e`: `MobileClient.Commands.Refresh`
- `0x1fa0a6`: `refreshCommand`
- `0x1fa065`: `MobileClient.Commands.Start`
- `0x1f9f67`: `MobileClient.Commands.Workspace.LearningPath`
- `0x1f9f7f`: `GuidedHelpCommand`
- `0x1f9fa8`: `MobileClient.Commands.Workspace.LearningPath_ContentLibrary`
- `0x1f9fc0`: `ContentLibraryCommand`
- `0x1fa14c`: `OpenInPowerBIButtonId`
- `0x1fa156`: `OpenInPowerBICommand`
- `0x1fa13e`: `MobileClient.Commands.OpenInPowerBI`
- `0x1fa16a`: `OpenInPowerBI`
- `0x1fa03c`: `MobileClient.Commands.Home`
- `0x1f9fe9`: `MobileClient.Commands.SelectDashboard`
- `0x1fa0fc`: `MobileClient.Commands.OpenInBrowser`
- `0x1fa10a`: `OpenInBrowserButton`
- `0x1fa128`: `OpenInBrowser`
- `0x1fa180`: `MobileClient.Commands.EmailLink`
- `0x1fa18e`: `EmailLinkButton`
- `0x1fa198`: `EmailLinkCommand`
- `0x1fa1c0`: `MobileClient.Commands.SetAsHome`
- `0x1fa1d8`: `SetHomepageCommand`
- `0x1fa28b`: `DashboardCommands`
- `0x1fa297`: `DashboardCommands`

## pseudocode

```c

```

## disassembly

```asm
0x1f9f50  newobj   instance void class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Framework.List`1<class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.CommandControlDescriptor>::.ctor()
0x1f9f55  stloc.0
0x1f9f56  ldarg.0
0x1f9f57  newobj   instance void [mscorlib]System.Globalization.CultureInfo::.ctor(int32)
0x1f9f5c  stloc.1
0x1f9f5d  call     bool Microsoft.Crm.ObjectModel.ApplicationMetadata.StaticApplicationMetadata.StaticCommandBarMetadata::IsGuidedHelpSoultionInstalled()
0x1f9f62  brfalse  loc_1F9FE9
0x1f9f67  ldstr    aMobileclientCo_13// "MobileClient.Commands.Workspace.Learnin"...
0x1f9f6c  ldloc.1
0x1f9f6d  call     string Microsoft.Crm.Resources.ObjectModelResourceManager::GetString(string name, class [mscorlib]System.Globalization.CultureInfo culture)
0x1f9f72  stloc.s  0xE
0x1f9f74  ldloc.0
0x1f9f75  ldstr    aGuidedhelpbutt// "GuidedHelpButton"
0x1f9f7a  ldstr    aButton// "Button"
0x1f9f7f  ldstr    aGuidedhelpcomm// "GuidedHelpCommand"
0x1f9f84  ldloc.s  0xE
0x1f9f86  ldloc.0
0x1f9f87  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.CommandControlDescriptor>::get_Count()
0x1f9f8c  ldc.i4.1
0x1f9f8d  add
0x1f9f8e  ldstr    aWebresource// "WebResource"
0x1f9f93  ldstr    aDefault// "Default"
0x1f9f98  ldstr    aSymbol// "Symbol"
0x1f9f9d  ldnull
0x1f9f9e  newobj   instance void [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.CommandControlDescriptor::.ctor(string, string, string, string, int32, string, string, string, class [Microsoft.Crm.Client.Shared]System.Dictionary)
0x1f9fa3  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.CommandControlDescriptor>::Add(var<u1>)
0x1f9fa8  ldstr    aMobileclientCo_14// "MobileClient.Commands.Workspace.Learnin"...
0x1f9fad  ldloc.1
0x1f9fae  call     string Microsoft.Crm.Resources.ObjectModelResourceManager::GetString(string name, class [mscorlib]System.Globalization.CultureInfo culture)
0x1f9fb3  stloc.s  0xF
0x1f9fb5  ldloc.0
0x1f9fb6  ldstr    aContentlibrary// "ContentLibraryButton"
0x1f9fbb  ldstr    aButton// "Button"
0x1f9fc0  ldstr    aContentlibrary_0// "ContentLibraryCommand"
0x1f9fc5  ldloc.s  0xF
0x1f9fc7  ldloc.0
0x1f9fc8  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.CommandControlDescriptor>::get_Count()
0x1f9fcd  ldc.i4.1
0x1f9fce  add
0x1f9fcf  ldstr    aWebresource// "WebResource"
0x1f9fd4  ldstr    aDefault// "Default"
0x1f9fd9  ldstr    aSymbol// "Symbol"
0x1f9fde  ldnull
0x1f9fdf  newobj   instance void [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.CommandControlDescriptor::.ctor(string, string, string, string, int32, string, string, string, class [Microsoft.Crm.Client.Shared]System.Dictionary)
0x1f9fe4  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.CommandControlDescriptor>::Add(var<u1>)
0x1f9fe9  ldstr    aMobileclientCo_21// "MobileClient.Commands.SelectDashboard"
0x1f9fee  ldloc.1
0x1f9fef  call     string Microsoft.Crm.Resources.ObjectModelResourceManager::GetString(string name, class [mscorlib]System.Globalization.CultureInfo culture)
0x1f9ff4  stloc.2
0x1f9ff5  ldc.i4.0
0x1f9ff6  newarr   [mscorlib]System.Object
0x1f9ffb  newobj   instance void [Microsoft.Crm.Client.Shared]System.Dictionary::.ctor(object[])
0x1fa000  stloc.3
0x1fa001  ldloc.3
0x1fa002  ldstr    aRetrievalactio// "RetrievalAction"
0x1fa007  ldstr    aRetrievedashbo_0// "RetrieveDashboardSelector"
0x1fa00c  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x1fa011  ldloc.0
0x1fa012  ldstr    aSelectdashboar// "SelectDashboard"
0x1fa017  ldstr    aFlyoutanchor// "FlyoutAnchor"
0x1fa01c  ldnull
0x1fa01d  ldloc.2
0x1fa01e  ldloc.0
0x1fa01f  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.CommandControlDescriptor>::get_Count()
0x1fa024  ldc.i4.1
0x1fa025  add
0x1fa026  ldnull
0x1fa027  ldstr    aSelectview// "SelectView"
0x1fa02c  ldstr    aSymbol// "Symbol"
0x1fa031  ldloc.3
0x1fa032  newobj   instance void [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.CommandControlDescriptor::.ctor(string, string, string, string, int32, string, string, string, class [Microsoft.Crm.Client.Shared]System.Dictionary)
0x1fa037  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.CommandControlDescriptor>::Add(var<u1>)
0x1fa03c  ldstr    aMobileclientCo_20// "MobileClient.Commands.Home"
0x1fa041  ldloc.1
0x1fa042  call     string Microsoft.Crm.Resources.ObjectModelResourceManager::GetString(string name, class [mscorlib]System.Globalization.CultureInfo culture)
0x1fa047  stloc.s  4
0x1fa049  ldloc.0
0x1fa04a  ldstr    aHomepinbutton// "HomePinButton"
0x1fa04f  ldloc.s  4
0x1fa051  ldloc.0
0x1fa052  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.CommandControlDescriptor>::get_Count()
0x1fa057  ldc.i4.1
0x1fa058  add
0x1fa059  ldc.i4.0
0x1fa05a  ldc.i4.0
0x1fa05b  call     class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.CommandControlDescriptor Microsoft.Crm.ObjectModel.ApplicationMetadata.StaticApplicationMetadata.StaticCommandBarMetadata::BuildPinCommandButtonDescriptor(string id, string label, int32 sequence, bool startScreen, bool isBoundToScreen)
0x1fa060  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.CommandControlDescriptor>::Add(var<u1>)
0x1fa065  ldstr    aMobileclientCo_6// "MobileClient.Commands.Start"
0x1fa06a  ldloc.1
0x1fa06b  call     string Microsoft.Crm.Resources.ObjectModelResourceManager::GetString(string name, class [mscorlib]System.Globalization.CultureInfo culture)
0x1fa070  stloc.s  5
0x1fa072  ldloc.0
0x1fa073  ldstr    aWin8pinbutton// "Win8PinButton"
0x1fa078  ldloc.s  5
0x1fa07a  ldloc.0
0x1fa07b  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.CommandControlDescriptor>::get_Count()
0x1fa080  ldc.i4.1
0x1fa081  add
0x1fa082  ldc.i4.1
0x1fa083  ldc.i4.0
0x1fa084  call     class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.CommandControlDescriptor Microsoft.Crm.ObjectModel.ApplicationMetadata.StaticApplicationMetadata.StaticCommandBarMetadata::BuildPinCommandButtonDescriptor(string id, string label, int32 sequence, bool startScreen, bool isBoundToScreen)
0x1fa089  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.CommandControlDescriptor>::Add(var<u1>)
0x1fa08e  ldstr    aMobileclientCo_3// "MobileClient.Commands.Refresh"
0x1fa093  ldloc.1
0x1fa094  call     string Microsoft.Crm.Resources.ObjectModelResourceManager::GetString(string name, class [mscorlib]System.Globalization.CultureInfo culture)
0x1fa099  stloc.s  6
0x1fa09b  ldloc.0
0x1fa09c  ldstr    aRefreshbutton// "RefreshButton"
0x1fa0a1  ldstr    aButton// "Button"
0x1fa0a6  ldstr    aRefreshcommand// "refreshCommand"
0x1fa0ab  ldloc.s  6
0x1fa0ad  ldloc.0
0x1fa0ae  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.CommandControlDescriptor>::get_Count()
0x1fa0b3  ldc.i4.1
0x1fa0b4  add
0x1fa0b5  ldstr    aControlcommand// "ControlCommand"
0x1fa0ba  ldstr    aRefresh// "Refresh"
0x1fa0bf  ldstr    aSymbol// "Symbol"
0x1fa0c4  ldnull
0x1fa0c5  ldloca.s 0x10
0x1fa0c7  initobj  [mscorlib]System.Guid
0x1fa0cd  ldloc.s  0x10
0x1fa0cf  call     bool Microsoft.Crm.ObjectModel.ConverterUtilities::IsMocaOfflineFeatureAvailable([opt] valuetype [mscorlib]System.Guid organizationId)
0x1fa0d4  newobj   instance void [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.CommandControlDescriptor::.ctor(string, string, string, string, int32, string, string, string, class [Microsoft.Crm.Client.Shared]System.Dictionary, bool)
0x1fa0d9  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.CommandControlDescriptor>::Add(var<u1>)
0x1fa0de  ldc.i4.0
0x1fa0df  newarr   [mscorlib]System.Object
0x1fa0e4  newobj   instance void [Microsoft.Crm.Client.Shared]System.Dictionary::.ctor(object[])
0x1fa0e9  stloc.s  7
0x1fa0eb  ldloc.s  7
0x1fa0ed  ldstr    aHideonphone// "HideOnPhone"
0x1fa0f2  ldstr    aMscrmHideonpho// "Mscrm.HideOnPhone"
0x1fa0f7  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x1fa0fc  ldstr    aMobileclientCo_22// "MobileClient.Commands.OpenInBrowser"
0x1fa101  ldloc.1
0x1fa102  call     string Microsoft.Crm.Resources.ObjectModelResourceManager::GetString(string name, class [mscorlib]System.Globalization.CultureInfo culture)
0x1fa107  stloc.s  8
0x1fa109  ldloc.0
0x1fa10a  ldstr    aOpeninbrowserb// "OpenInBrowserButton"
0x1fa10f  ldstr    aButton// "Button"
0x1fa114  ldstr    aOpeninbrowserc// "OpenInBrowserCommand"
0x1fa119  ldloc.s  8
0x1fa11b  ldloc.0
0x1fa11c  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.CommandControlDescriptor>::get_Count()
0x1fa121  ldc.i4.1
0x1fa122  add
0x1fa123  ldstr    aSystem_0// "System"
0x1fa128  ldstr    aOpeninbrowser// "OpenInBrowser"
0x1fa12d  ldstr    aSymbol// "Symbol"
0x1fa132  ldloc.s  7
0x1fa134  newobj   instance void [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.CommandControlDescriptor::.ctor(string, string, string, string, int32, string, string, string, class [Microsoft.Crm.Client.Shared]System.Dictionary)
0x1fa139  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.CommandControlDescriptor>::Add(var<u1>)
0x1fa13e  ldstr    aMobileclientCo_18// "MobileClient.Commands.OpenInPowerBI"
0x1fa143  ldloc.1
0x1fa144  call     string Microsoft.Crm.Resources.ObjectModelResourceManager::GetString(string name, class [mscorlib]System.Globalization.CultureInfo culture)
0x1fa149  stloc.s  9
0x1fa14b  ldloc.0
0x1fa14c  ldstr    aOpeninpowerbib// "OpenInPowerBIButtonId"
0x1fa151  ldstr    aButton// "Button"
0x1fa156  ldstr    aOpeninpowerbic// "OpenInPowerBICommand"
0x1fa15b  ldloc.s  9
0x1fa15d  ldloc.0
0x1fa15e  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.CommandControlDescriptor>::get_Count()
0x1fa163  ldc.i4.1
0x1fa164  add
0x1fa165  ldstr    aSystem_0// "System"
0x1fa16a  ldstr    aOpeninpowerbi// "OpenInPowerBI"
0x1fa16f  ldstr    aSymbol// "Symbol"
0x1fa174  ldnull
0x1fa175  ldc.i4.1
0x1fa176  newobj   instance void [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.CommandControlDescriptor::.ctor(string, string, string, string, int32, string, string, string, class [Microsoft.Crm.Client.Shared]System.Dictionary, bool)
0x1fa17b  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.CommandControlDescriptor>::Add(var<u1>)
0x1fa180  ldstr    aMobileclientCo_23// "MobileClient.Commands.EmailLink"
0x1fa185  ldloc.1
0x1fa186  call     string Microsoft.Crm.Resources.ObjectModelResourceManager::GetString(string name, class [mscorlib]System.Globalization.CultureInfo culture)
0x1fa18b  stloc.s  0xA
0x1fa18d  ldloc.0
0x1fa18e  ldstr    aEmaillinkbutto// "EmailLinkButton"
0x1fa193  ldstr    aButton// "Button"
0x1fa198  ldstr    aEmaillinkcomma// "EmailLinkCommand"
0x1fa19d  ldloc.s  0xA
0x1fa19f  ldloc.0
0x1fa1a0  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.CommandControlDescriptor>::get_Count()
0x1fa1a5  ldc.i4.1
0x1fa1a6  add
0x1fa1a7  ldstr    aSystem_0// "System"
0x1fa1ac  ldstr    aMail// "Mail"
0x1fa1b1  ldstr    aSymbol// "Symbol"
0x1fa1b6  newobj   instance void [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.CommandControlDescriptor::.ctor(string, string, string, string, int32, string, string, string)
0x1fa1bb  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.CommandControlDescriptor>::Add(var<u1>)
0x1fa1c0  ldstr    aMobileclientCo_24// "MobileClient.Commands.SetAsHome"
0x1fa1c5  ldloc.1
0x1fa1c6  call     string Microsoft.Crm.Resources.ObjectModelResourceManager::GetString(string name, class [mscorlib]System.Globalization.CultureInfo culture)
0x1fa1cb  stloc.s  0xB
0x1fa1cd  ldloc.0
0x1fa1ce  ldstr    aSetashome// "SetAsHome"
0x1fa1d3  ldstr    aButton// "Button"
0x1fa1d8  ldstr    aSethomepagecom// "SetHomepageCommand"
0x1fa1dd  ldloc.s  0xB
0x1fa1df  ldloc.0
0x1fa1e0  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.CommandControlDescriptor>::get_Count()
0x1fa1e5  ldc.i4.1
0x1fa1e6  add
0x1fa1e7  ldstr    aSystem_0// "System"
0x1fa1ec  ldstr    aSetashome// "SetAsHome"
0x1fa1f1  ldstr    aSymbol// "Symbol"
0x1fa1f6  newobj   instance void [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.CommandControlDescriptor::.ctor(string, string, string, string, int32, string, string, string)
0x1fa1fb  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.CommandControlDescriptor>::Add(var<u1>)
0x1fa200  ldstr    aMobileclientCo_1// "MobileClient.Commands.Workspace.SnapSho"...
0x1fa205  ldloc.1
0x1fa206  call     string Microsoft.Crm.Resources.ObjectModelResourceManager::GetString(string name, class [mscorlib]System.Globalization.CultureInfo culture)
0x1fa20b  stloc.s  0xC
0x1fa20d  ldloc.0
0x1fa20e  ldstr    aSnapshotbutton// "SnapshotButton"
0x1fa213  ldstr    aButton// "Button"
0x1fa218  ldstr    aMemorysnapshot_0// "MemorySnapshotCommand"
0x1fa21d  ldloc.s  0xC
0x1fa21f  ldloc.0
0x1fa220  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.CommandControlDescriptor>::get_Count()
0x1fa225  ldc.i4.1
0x1fa226  add
0x1fa227  ldstr    aSystem_0// "System"
0x1fa22c  ldstr    aDefault// "Default"
0x1fa231  ldstr    aSymbol// "Symbol"
0x1fa236  ldnull
0x1fa237  ldc.i4.1
0x1fa238  newobj   instance void [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.CommandControlDescriptor::.ctor(string, string, string, string, int32, string, string, string, class [Microsoft.Crm.Client.Shared]System.Dictionary, bool)
0x1fa23d  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.CommandControlDescriptor>::Add(var<u1>)
0x1fa242  ldstr    aMobileclientCo_2// "MobileClient.Commands.Workspace.Diagnos"...
0x1fa247  ldloc.1
0x1fa248  call     string Microsoft.Crm.Resources.ObjectModelResourceManager::GetString(string name, class [mscorlib]System.Globalization.CultureInfo culture)
0x1fa24d  stloc.s  0xD
0x1fa24f  ldloc.0
0x1fa250  ldstr    aDiagnosticsrep// "DiagnosticsReportButton"
0x1fa255  ldstr    aButton// "Button"
0x1fa25a  ldstr    aShowdiagnostic// "ShowDiagnosticsReportCommand"
0x1fa25f  ldloc.s  0xD
0x1fa261  ldloc.0
0x1fa262  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.CommandControlDescriptor>::get_Count()
0x1fa267  ldc.i4.1
0x1fa268  add
0x1fa269  ldstr    aSystem_0// "System"
0x1fa26e  ldstr    aDefault// "Default"
0x1fa273  ldstr    aSymbol// "Symbol"
0x1fa278  ldnull
0x1fa279  ldc.i4.1
0x1fa27a  newobj   instance void [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.CommandControlDescriptor::.ctor(string, string, string, string, int32, string, string, string, class [Microsoft.Crm.Client.Shared]System.Dictionary, bool)
0x1fa27f  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.CommandControlDescriptor>::Add(var<u1>)
0x1fa284  call     bool Microsoft.Crm.ObjectModel.ApplicationMetadata.StaticApplicationMetadata.StaticCommandBarMetadata::IsGuidedHelpSoultionInstalled()
0x1fa289  brtrue.s loc_1FA297
0x1fa28b  ldstr    aDashboardcomma// "DashboardCommands"
0x1fa290  ldloc.0
0x1fa291  call     class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.CommandSet Microsoft.Crm.ObjectModel.ApplicationMetadata.StaticApplicationMetadata.StaticCommandBarMetadata::BuildCommandSetComponentDefinitionDescriptor(string commandSetId, class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Framework.List`1<class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.CommandControlDescriptor> controlList)
0x1fa296  ret
0x1fa297  ldstr    aDashboardcomma// "DashboardCommands"
0x1fa29c  ldloc.0
0x1fa29d  call     class [Microsoft.Crm.Client.Shared]System.Dictionary Microsoft.Crm.ObjectModel.ApplicationMetadata.StaticApplicationMetadata.StaticCommandBarMetadata::BuildGuidedHelpCommand()
0x1fa2a2  call     class [Microsoft.Crm.Client.Shared]System.Dictionary Microsoft.Crm.ObjectModel.ApplicationMetadata.StaticApplicationMetadata.StaticCommandBarMetadata::BuildGuidedHelpCommandRules()
0x1fa2a7  call     class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.CommandSet Microsoft.Crm.ObjectModel.ApplicationMetadata.StaticApplicationMetadata.StaticCommandBarMetadata::BuildCommandSetComponentDefinitionDescriptor(string commandSetId, class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Framework.List`1<class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.CommandControlDescriptor> controlList, class [Microsoft.Crm.Client.Shared]System.Dictionary commandList, class [Microsoft.Crm.Client.Shared]System.Dictionary commandRules)
0x1fa2ac  ret
```
