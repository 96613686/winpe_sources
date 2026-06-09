# Microsoft.Crm.ObjectModel.ApplicationMetadata.StaticApplicationMetadata.StaticCommandBarMetadata::BuildNoteListItemCommands

- ea: `0x1f92b0`
- end: `0x1f93aa`
- name: `Microsoft.Crm.ObjectModel.ApplicationMetadata.StaticApplicationMetadata.StaticCommandBarMetadata::BuildNoteListItemCommands`
- size: `250`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0xb5d90`

## callees

- `0x19b90`
- `0x1fa2b0`

## string_xrefs

- `0x1f92f3`: `Delete`
- `0x1f92ee`: `ControlCommand`
- `0x1f9312`: `OpenCreateForm`
- `0x1f939e`: `ListItemCommands`
- `0x1f92b7`: `MobileClient.Commands.Delete`
- `0x1f92c3`: `MobileClient.Commands.EditNote`
- `0x1f92d6`: `DeleteButton`
- `0x1f92e0`: `deleteCommand`
- `0x1f9348`: `CreateFormType`

## pseudocode

```c

```

## disassembly

```asm
0x1f92b0  ldarg.0
0x1f92b1  newobj   instance void [mscorlib]System.Globalization.CultureInfo::.ctor(int32)
0x1f92b6  stloc.0
0x1f92b7  ldstr    aMobileclientCo_7// "MobileClient.Commands.Delete"
0x1f92bc  ldloc.0
0x1f92bd  call     string Microsoft.Crm.Resources.ObjectModelResourceManager::GetString(string name, class [mscorlib]System.Globalization.CultureInfo culture)
0x1f92c2  stloc.1
0x1f92c3  ldstr    aMobileclientCo_8// "MobileClient.Commands.EditNote"
0x1f92c8  ldloc.0
0x1f92c9  call     string Microsoft.Crm.Resources.ObjectModelResourceManager::GetString(string name, class [mscorlib]System.Globalization.CultureInfo culture)
0x1f92ce  stloc.2
0x1f92cf  newobj   instance void class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Framework.List`1<class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.CommandControlDescriptor>::.ctor()
0x1f92d4  stloc.3
0x1f92d5  ldloc.3
0x1f92d6  ldstr    aDeletebutton// "DeleteButton"
0x1f92db  ldstr    aButton// "Button"
0x1f92e0  ldstr    aDeletecommand// "deleteCommand"
0x1f92e5  ldloc.1
0x1f92e6  ldloc.3
0x1f92e7  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.CommandControlDescriptor>::get_Count()
0x1f92ec  ldc.i4.1
0x1f92ed  add
0x1f92ee  ldstr    aControlcommand// "ControlCommand"
0x1f92f3  ldstr    aDelete// "Delete"
0x1f92f8  ldstr    aSymbol// "Symbol"
0x1f92fd  newobj   instance void [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.CommandControlDescriptor::.ctor(string, string, string, string, int32, string, string, string)
0x1f9302  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.CommandControlDescriptor>::Add(var<u1>)
0x1f9307  ldloc.3
0x1f9308  ldstr    aEditnotebutton// "EditNoteButton"
0x1f930d  ldstr    aButton// "Button"
0x1f9312  ldstr    aOpencreateform// "OpenCreateForm"
0x1f9317  ldloc.2
0x1f9318  ldc.i4.1
0x1f9319  ldstr    aSystem_0// "System"
0x1f931e  ldstr    aEdit_1// "Edit"
0x1f9323  ldstr    aSymbol// "Symbol"
0x1f9328  ldc.i4.0
0x1f9329  newarr   [mscorlib]System.Object
0x1f932e  newobj   instance void [Microsoft.Crm.Client.Shared]System.Dictionary::.ctor(object[])
0x1f9333  stloc.s  4
0x1f9335  ldloc.s  4
0x1f9337  ldstr    aPrimarymodelna// "PrimaryModelName"
0x1f933c  ldstr    aAnnotation// "annotation"
0x1f9341  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x1f9346  ldloc.s  4
0x1f9348  ldstr    aCreateformtype// "CreateFormType"
0x1f934d  ldc.i4.s 0x16
0x1f934f  box      [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Framework.MetadataType
0x1f9354  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x1f9359  ldloc.s  4
0x1f935b  ldstr    aExternalparame// "externalParameters"
0x1f9360  ldc.i4.0
0x1f9361  newarr   [mscorlib]System.Object
0x1f9366  newobj   instance void [Microsoft.Crm.Client.Shared]System.Dictionary::.ctor(object[])
0x1f936b  dup
0x1f936c  ldstr    aInitializefrom_1// "InitializeFrom"
0x1f9371  ldc.i4.3
0x1f9372  box      [mscorlib]System.Int32
0x1f9377  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x1f937c  dup
0x1f937d  ldstr    aIssaveandeditb// "IsSaveAndEditButtonHidden"
0x1f9382  ldc.i4.1
0x1f9383  box      [mscorlib]System.Boolean
0x1f9388  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x1f938d  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x1f9392  ldloc.s  4
0x1f9394  newobj   instance void [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.CommandControlDescriptor::.ctor(string, string, string, string, int32, string, string, string, class [Microsoft.Crm.Client.Shared]System.Dictionary)
0x1f9399  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.CommandControlDescriptor>::Add(var<u1>)
0x1f939e  ldstr    aListitemcomman// "ListItemCommands"
0x1f93a3  ldloc.3
0x1f93a4  call     class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.CommandSet Microsoft.Crm.ObjectModel.ApplicationMetadata.StaticApplicationMetadata.StaticCommandBarMetadata::BuildCommandSetComponentDefinitionDescriptor(string commandSetId, class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Framework.List`1<class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.CommandControlDescriptor> controlList)
0x1f93a9  ret
```
