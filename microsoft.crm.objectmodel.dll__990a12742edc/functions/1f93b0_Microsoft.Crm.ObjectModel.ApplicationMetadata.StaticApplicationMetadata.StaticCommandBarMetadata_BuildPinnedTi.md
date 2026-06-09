# Microsoft.Crm.ObjectModel.ApplicationMetadata.StaticApplicationMetadata.StaticCommandBarMetadata::BuildPinnedTileCommands

- ea: `0x1f93b0`
- end: `0x1f9455`
- name: `Microsoft.Crm.ObjectModel.ApplicationMetadata.StaticApplicationMetadata.StaticCommandBarMetadata::BuildPinnedTileCommands`
- size: `165`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0xb77a0`

## callees

- `0x19b90`
- `0xbd040`
- `0x1fa2b0`

## string_xrefs

- `0x1f93ee`: `ControlCommand`
- `0x1f93d6`: `DeleteButton`
- `0x1f93e0`: `deleteCommand`
- `0x1f93b7`: `MobileClient.Commands.PinnedTile.Unpin`
- `0x1f93c3`: `MobileClient.Commands.PinnedTile.Smaller`
- `0x1f9422`: `ResizeTileCommand`
- `0x1f9449`: `PinnedTileCommands`

## pseudocode

```c

```

## disassembly

```asm
0x1f93b0  ldarg.0
0x1f93b1  newobj   instance void [mscorlib]System.Globalization.CultureInfo::.ctor(int32)
0x1f93b6  stloc.0
0x1f93b7  ldstr    aMobileclientCo_9// "MobileClient.Commands.PinnedTile.Unpin"
0x1f93bc  ldloc.0
0x1f93bd  call     string Microsoft.Crm.Resources.ObjectModelResourceManager::GetString(string name, class [mscorlib]System.Globalization.CultureInfo culture)
0x1f93c2  stloc.1
0x1f93c3  ldstr    aMobileclientCo_10// "MobileClient.Commands.PinnedTile.Smalle"...
0x1f93c8  ldloc.0
0x1f93c9  call     string Microsoft.Crm.Resources.ObjectModelResourceManager::GetString(string name, class [mscorlib]System.Globalization.CultureInfo culture)
0x1f93ce  stloc.2
0x1f93cf  newobj   instance void class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Framework.List`1<class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.CommandControlDescriptor>::.ctor()
0x1f93d4  stloc.3
0x1f93d5  ldloc.3
0x1f93d6  ldstr    aDeletebutton// "DeleteButton"
0x1f93db  ldstr    aButton// "Button"
0x1f93e0  ldstr    aDeletecommand// "deleteCommand"
0x1f93e5  ldloc.1
0x1f93e6  ldloc.3
0x1f93e7  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.CommandControlDescriptor>::get_Count()
0x1f93ec  ldc.i4.1
0x1f93ed  add
0x1f93ee  ldstr    aControlcommand// "ControlCommand"
0x1f93f3  ldstr    aUnpin// "Unpin"
0x1f93f8  ldstr    aSymbol// "Symbol"
0x1f93fd  ldnull
0x1f93fe  ldloca.s 4
0x1f9400  initobj  [mscorlib]System.Guid
0x1f9406  ldloc.s  4
0x1f9408  call     bool Microsoft.Crm.ObjectModel.ConverterUtilities::IsMocaOfflineFeatureAvailable([opt] valuetype [mscorlib]System.Guid organizationId)
0x1f940d  newobj   instance void [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.CommandControlDescriptor::.ctor(string, string, string, string, int32, string, string, string, class [Microsoft.Crm.Client.Shared]System.Dictionary, bool)
0x1f9412  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.CommandControlDescriptor>::Add(var<u1>)
0x1f9417  ldloc.3
0x1f9418  ldstr    aResizebutton// "ResizeButton"
0x1f941d  ldstr    aButton// "Button"
0x1f9422  ldstr    aResizetilecomm// "ResizeTileCommand"
0x1f9427  ldloc.2
0x1f9428  ldloc.3
0x1f9429  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.CommandControlDescriptor>::get_Count()
0x1f942e  ldc.i4.1
0x1f942f  add
0x1f9430  ldstr    aSystem_0// "System"
0x1f9435  ldstr    aReducetile// "ReduceTile"
0x1f943a  ldstr    aSymbol// "Symbol"
0x1f943f  newobj   instance void [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.CommandControlDescriptor::.ctor(string, string, string, string, int32, string, string, string)
0x1f9444  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.CommandControlDescriptor>::Add(var<u1>)
0x1f9449  ldstr    aPinnedtilecomm// "PinnedTileCommands"
0x1f944e  ldloc.3
0x1f944f  call     class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.CommandSet Microsoft.Crm.ObjectModel.ApplicationMetadata.StaticApplicationMetadata.StaticCommandBarMetadata::BuildCommandSetComponentDefinitionDescriptor(string commandSetId, class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Framework.List`1<class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.CommandControlDescriptor> controlList)
0x1f9454  ret
```
