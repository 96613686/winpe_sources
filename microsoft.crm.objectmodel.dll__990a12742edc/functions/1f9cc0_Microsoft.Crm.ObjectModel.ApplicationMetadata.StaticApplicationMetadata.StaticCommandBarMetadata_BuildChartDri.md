# Microsoft.Crm.ObjectModel.ApplicationMetadata.StaticApplicationMetadata.StaticCommandBarMetadata::BuildChartDrilldownCommands

- ea: `0x1f9cc0`
- end: `0x1f9e0d`
- name: `Microsoft.Crm.ObjectModel.ApplicationMetadata.StaticApplicationMetadata.StaticCommandBarMetadata::BuildChartDrilldownCommands`
- size: `333`
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

- `0x1f9db2`: `ControlCommand`
- `0x1f9de7`: `ControlCommand`
- `0x1f9da3`: `resizeHandlesCommand`
- `0x1f9ceb`: `MobileClient.Commands.Refresh`
- `0x1f9dd7`: `refreshCommand`
- `0x1f9cc7`: `MobileClient.Commands.SelectChart`
- `0x1f9cd3`: `MobileClient.Commands.SelectView`
- `0x1f9cdf`: `MobileClient.Commands.ResizeColumns`
- `0x1f9d99`: `ResizeHandlesCommand`
- `0x1f9e00`: `CrmChartDrilldownCommands`

## pseudocode

```c

```

## disassembly

```asm
0x1f9cc0  ldarg.0
0x1f9cc1  newobj   instance void [mscorlib]System.Globalization.CultureInfo::.ctor(int32)
0x1f9cc6  stloc.0
0x1f9cc7  ldstr    aMobileclientCo_15// "MobileClient.Commands.SelectChart"
0x1f9ccc  ldloc.0
0x1f9ccd  call     string Microsoft.Crm.Resources.ObjectModelResourceManager::GetString(string name, class [mscorlib]System.Globalization.CultureInfo culture)
0x1f9cd2  stloc.1
0x1f9cd3  ldstr    aMobileclientCo_16// "MobileClient.Commands.SelectView"
0x1f9cd8  ldloc.0
0x1f9cd9  call     string Microsoft.Crm.Resources.ObjectModelResourceManager::GetString(string name, class [mscorlib]System.Globalization.CultureInfo culture)
0x1f9cde  stloc.2
0x1f9cdf  ldstr    aMobileclientCo_17// "MobileClient.Commands.ResizeColumns"
0x1f9ce4  ldloc.0
0x1f9ce5  call     string Microsoft.Crm.Resources.ObjectModelResourceManager::GetString(string name, class [mscorlib]System.Globalization.CultureInfo culture)
0x1f9cea  stloc.3
0x1f9ceb  ldstr    aMobileclientCo_3// "MobileClient.Commands.Refresh"
0x1f9cf0  ldloc.0
0x1f9cf1  call     string Microsoft.Crm.Resources.ObjectModelResourceManager::GetString(string name, class [mscorlib]System.Globalization.CultureInfo culture)
0x1f9cf6  stloc.s  4
0x1f9cf8  newobj   instance void class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Framework.List`1<class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.CommandControlDescriptor>::.ctor()
0x1f9cfd  stloc.s  5
0x1f9cff  ldc.i4.0
0x1f9d00  newarr   [mscorlib]System.Object
0x1f9d05  newobj   instance void [Microsoft.Crm.Client.Shared]System.Dictionary::.ctor(object[])
0x1f9d0a  stloc.s  6
0x1f9d0c  ldloc.s  6
0x1f9d0e  ldstr    aRetrievalactio// "RetrievalAction"
0x1f9d13  ldstr    aRetrievechartv// "RetrieveChartViewSelector"
0x1f9d18  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x1f9d1d  ldloc.s  5
0x1f9d1f  ldstr    aChangelistview// "ChangeListViewButton"
0x1f9d24  ldstr    aFlyoutanchor// "FlyoutAnchor"
0x1f9d29  ldnull
0x1f9d2a  ldloc.2
0x1f9d2b  ldloc.s  5
0x1f9d2d  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.CommandControlDescriptor>::get_Count()
0x1f9d32  ldc.i4.1
0x1f9d33  add
0x1f9d34  ldnull
0x1f9d35  ldstr    aSelectview// "SelectView"
0x1f9d3a  ldstr    aSymbol// "Symbol"
0x1f9d3f  ldloc.s  6
0x1f9d41  newobj   instance void [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.CommandControlDescriptor::.ctor(string, string, string, string, int32, string, string, string, class [Microsoft.Crm.Client.Shared]System.Dictionary)
0x1f9d46  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.CommandControlDescriptor>::Add(var<u1>)
0x1f9d4b  ldc.i4.0
0x1f9d4c  newarr   [mscorlib]System.Object
0x1f9d51  newobj   instance void [Microsoft.Crm.Client.Shared]System.Dictionary::.ctor(object[])
0x1f9d56  stloc.s  6
0x1f9d58  ldloc.s  6
0x1f9d5a  ldstr    aRetrievalactio// "RetrievalAction"
0x1f9d5f  ldstr    aRetrievecharts// "RetrieveChartSelector"
0x1f9d64  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x1f9d69  ldloc.s  5
0x1f9d6b  ldstr    aSelectchartsbu// "SelectChartsButton"
0x1f9d70  ldstr    aFlyoutanchor// "FlyoutAnchor"
0x1f9d75  ldnull
0x1f9d76  ldloc.1
0x1f9d77  ldloc.s  5
0x1f9d79  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.CommandControlDescriptor>::get_Count()
0x1f9d7e  ldc.i4.1
0x1f9d7f  add
0x1f9d80  ldnull
0x1f9d81  ldstr    aSelectchart// "SelectChart"
0x1f9d86  ldstr    aSymbol// "Symbol"
0x1f9d8b  ldloc.s  6
0x1f9d8d  newobj   instance void [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.CommandControlDescriptor::.ctor(string, string, string, string, int32, string, string, string, class [Microsoft.Crm.Client.Shared]System.Dictionary)
0x1f9d92  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.CommandControlDescriptor>::Add(var<u1>)
0x1f9d97  ldloc.s  5
0x1f9d99  ldstr    aResizehandlesc_0// "ResizeHandlesCommand"
0x1f9d9e  ldstr    aButton// "Button"
0x1f9da3  ldstr    aResizehandlesc// "resizeHandlesCommand"
0x1f9da8  ldloc.3
0x1f9da9  ldloc.s  5
0x1f9dab  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.CommandControlDescriptor>::get_Count()
0x1f9db0  ldc.i4.1
0x1f9db1  add
0x1f9db2  ldstr    aControlcommand// "ControlCommand"
0x1f9db7  ldstr    aExpandtile// "ExpandTile"
0x1f9dbc  ldstr    aSymbol// "Symbol"
0x1f9dc1  newobj   instance void [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.CommandControlDescriptor::.ctor(string, string, string, string, int32, string, string, string)
0x1f9dc6  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.CommandControlDescriptor>::Add(var<u1>)
0x1f9dcb  ldloc.s  5
0x1f9dcd  ldstr    aRefreshbutton// "RefreshButton"
0x1f9dd2  ldstr    aButton// "Button"
0x1f9dd7  ldstr    aRefreshcommand// "refreshCommand"
0x1f9ddc  ldloc.s  4
0x1f9dde  ldloc.s  5
0x1f9de0  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.CommandControlDescriptor>::get_Count()
0x1f9de5  ldc.i4.1
0x1f9de6  add
0x1f9de7  ldstr    aControlcommand// "ControlCommand"
0x1f9dec  ldstr    aRefresh// "Refresh"
0x1f9df1  ldstr    aSymbol// "Symbol"
0x1f9df6  newobj   instance void [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.CommandControlDescriptor::.ctor(string, string, string, string, int32, string, string, string)
0x1f9dfb  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.CommandControlDescriptor>::Add(var<u1>)
0x1f9e00  ldstr    aCrmchartdrilld_0// "CrmChartDrilldownCommands"
0x1f9e05  ldloc.s  5
0x1f9e07  call     class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.CommandSet Microsoft.Crm.ObjectModel.ApplicationMetadata.StaticApplicationMetadata.StaticCommandBarMetadata::BuildCommandSetComponentDefinitionDescriptor(string commandSetId, class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Framework.List`1<class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.CommandControlDescriptor> controlList)
0x1f9e0c  ret
```
