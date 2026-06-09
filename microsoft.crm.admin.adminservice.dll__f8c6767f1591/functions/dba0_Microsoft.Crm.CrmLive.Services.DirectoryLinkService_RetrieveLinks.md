# Microsoft.Crm.CrmLive.Services.DirectoryLinkService::RetrieveLinks

- ea: `0xdba0`
- end: `0xdc6b`
- name: `Microsoft.Crm.CrmLive.Services.DirectoryLinkService::RetrieveLinks`
- size: `203`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0xdac0`
- `0xdb70`

## callees

- `0xdba0`

## string_xrefs

- `0xdc60`: `D:\a\1\s\src\CrmLive\Admin\MicrosoftOnline\DirectoryLinkService.cs`
- `0xdc4f`: `DirectoryLink`
- `0xdc5b`: `RetrieveLinks`

## pseudocode

```c

```

## disassembly

```asm
0xdba0  ldarg.1
0xdba1  ldstr    aContextid_0// "contextId"
0xdba6  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfGuidEmpty(valuetype [mscorlib]System.Guid, string)
0xdbab  ldarg.3
0xdbac  ldlen
0xdbad  conv.i4
0xdbae  newarr   [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag
0xdbb3  stloc.0
0xdbb4  ldc.i4.0
0xdbb5  stloc.1
0xdbb6  ldarg.3
0xdbb7  stloc.2
0xdbb8  ldc.i4.0
0xdbb9  stloc.3
0xdbba  br       loc_DC45
0xdbbf  ldloc.2
0xdbc0  ldloc.3
0xdbc1  ldelem   [mscorlib]System.Guid
0xdbc6  stloc.s  4
0xdbc8  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0xdbcd  stloc.s  5
0xdbcf  ldloc.s  5
0xdbd1  ldstr    aContextid// "ContextId"
0xdbd6  ldarg.1
0xdbd7  box      [mscorlib]System.Guid
0xdbdc  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0xdbe1  ldloc.s  5
0xdbe3  ldstr    aSourceclass// "SourceClass"
0xdbe8  ldtoken  [Microsoft.Crm.CrmLive.MicrosoftOnline.Client]Microsoft.Crm.CrmLive.MicrosoftOnline.Client.Group
0xdbed  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xdbf2  call     string [Microsoft.Crm.CrmLive.MicrosoftOnline.Client]Microsoft.Crm.CrmLive.MicrosoftOnline.Client.DirectoryObjectSerializer::GetStringFromType(class [mscorlib]System.Type)
0xdbf7  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0xdbfc  ldloc.s  5
0xdbfe  ldstr    aTargetclass// "TargetClass"
0xdc03  ldtoken  [Microsoft.Crm.CrmLive.MicrosoftOnline.Client]Microsoft.Crm.CrmLive.MicrosoftOnline.Client.User
0xdc08  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xdc0d  call     string [Microsoft.Crm.CrmLive.MicrosoftOnline.Client]Microsoft.Crm.CrmLive.MicrosoftOnline.Client.DirectoryObjectSerializer::GetStringFromType(class [mscorlib]System.Type)
0xdc12  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0xdc17  ldloc.s  4
0xdc19  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0xdc1e  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0xdc23  brfalse.s loc_DC38
0xdc25  ldloc.s  5
0xdc27  ldstr    aSourceid// "SourceId"
0xdc2c  ldloc.s  4
0xdc2e  box      [mscorlib]System.Guid
0xdc33  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0xdc38  ldloc.0
0xdc39  ldloc.1
0xdc3a  dup
0xdc3b  ldc.i4.1
0xdc3c  add
0xdc3d  stloc.1
0xdc3e  ldloc.s  5
0xdc40  stelem.ref
0xdc41  ldloc.3
0xdc42  ldc.i4.1
0xdc43  add
0xdc44  stloc.3
0xdc45  ldloc.3
0xdc46  ldloc.2
0xdc47  ldlen
0xdc48  conv.i4
0xdc49  blt      loc_DBBF
0xdc4e  ldarg.0
0xdc4f  ldstr    aDirectorylink// "DirectoryLink"
0xdc54  ldarg.2
0xdc55  ldloc.0
0xdc56  ldc.i4   0xA7
0xdc5b  ldstr    aRetrievelinks// "RetrieveLinks"
0xdc60  ldstr    aDA1SSrcCrmlive_18// "D:\\a\\1\\s\\src\\CrmLive\\Admin\\Micro"...
0xdc65  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBagCollection [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::Retrieve(string, string[], class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag[], int32, string, string)
0xdc6a  ret
```
