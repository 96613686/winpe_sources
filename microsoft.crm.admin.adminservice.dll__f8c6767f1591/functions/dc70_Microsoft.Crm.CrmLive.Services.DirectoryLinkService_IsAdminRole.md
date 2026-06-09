# Microsoft.Crm.CrmLive.Services.DirectoryLinkService::IsAdminRole

- ea: `0xdc70`
- end: `0xdd73`
- name: `Microsoft.Crm.CrmLive.Services.DirectoryLinkService::IsAdminRole`
- size: `259`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0xdc70`

## string_xrefs

- `0xdd09`: `D:\a\1\s\src\CrmLive\Admin\MicrosoftOnline\DirectoryLinkService.cs`
- `0xdcef`: `DirectoryLink`
- `0xdd35`: `DeletedOn`

## pseudocode

```c

```

## disassembly

```asm
0xdc70  ldarg.1
0xdc71  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0xdc76  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0xdc7b  brtrue.s loc_DC8A
0xdc7d  ldarg.2
0xdc7e  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0xdc83  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0xdc88  brfalse.s loc_DC8C
0xdc8a  ldc.i4.0
0xdc8b  ret
0xdc8c  call     class [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::NewService()
0xdc91  stloc.0
0xdc92  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0xdc97  stloc.1
0xdc98  ldloc.1
0xdc99  ldstr    aSourceclass// "SourceClass"
0xdc9e  ldtoken  [Microsoft.Crm.CrmLive.MicrosoftOnline.Client]Microsoft.Crm.CrmLive.MicrosoftOnline.Client.Group
0xdca3  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xdca8  call     string [Microsoft.Crm.CrmLive.MicrosoftOnline.Client]Microsoft.Crm.CrmLive.MicrosoftOnline.Client.DirectoryObjectSerializer::GetStringFromType(class [mscorlib]System.Type)
0xdcad  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0xdcb2  ldloc.1
0xdcb3  ldstr    aTargetclass// "TargetClass"
0xdcb8  ldtoken  [Microsoft.Crm.CrmLive.MicrosoftOnline.Client]Microsoft.Crm.CrmLive.MicrosoftOnline.Client.User
0xdcbd  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xdcc2  call     string [Microsoft.Crm.CrmLive.MicrosoftOnline.Client]Microsoft.Crm.CrmLive.MicrosoftOnline.Client.DirectoryObjectSerializer::GetStringFromType(class [mscorlib]System.Type)
0xdcc7  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0xdccc  ldloc.1
0xdccd  ldstr    aSourceid// "SourceId"
0xdcd2  ldarg.1
0xdcd3  box      [mscorlib]System.Guid
0xdcd8  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0xdcdd  ldloc.1
0xdcde  ldstr    aTargetid_0// "TargetId"
0xdce3  ldarg.2
0xdce4  box      [mscorlib]System.Guid
0xdce9  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0xdcee  ldloc.0
0xdcef  ldstr    aDirectorylink// "DirectoryLink"
0xdcf4  ldnull
0xdcf5  ldc.i4.1
0xdcf6  newarr   [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag
0xdcfb  dup
0xdcfc  ldc.i4.0
0xdcfd  ldloc.1
0xdcfe  stelem.ref
0xdcff  ldc.i4   0xBF
0xdd04  ldstr    aIsadminrole// "IsAdminRole"
0xdd09  ldstr    aDA1SSrcCrmlive_18// "D:\\a\\1\\s\\src\\CrmLive\\Admin\\Micro"...
0xdd0e  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBagCollection [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::Retrieve(string, string[], class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag[], int32, string, string)
0xdd13  stloc.2
0xdd14  ldloc.2
0xdd15  call     bool [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBagCollection::IsNullOrEmpty(class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBagCollection)
0xdd1a  brtrue.s loc_DD62
0xdd1c  ldloc.2
0xdd1d  callvirt instance valuetype [System]System.Collections.Generic.SortedDictionary`2/Enumerator<var<u1>, !!T0> class [System]System.Collections.Generic.SortedDictionary`2<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::GetEnumerator()
0xdd22  stloc.3
0xdd23  br.s     loc_DD49
0xdd25  ldloca.s 3
0xdd27  call     instance valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<var<u1>, !!T0> valuetype [System]System.Collections.Generic.SortedDictionary`2/Enumerator<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::get_Current()
0xdd2c  stloc.s  4
0xdd2e  ldloca.s 4
0xdd30  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::get_Value()
0xdd35  ldstr    aDeletedon// "DeletedOn"
0xdd3a  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0xdd3f  brfalse.s loc_DD44
0xdd41  ldc.i4.2
0xdd42  br.s     loc_DD45
0xdd44  ldc.i4.1
0xdd45  stloc.s  5
0xdd47  leave.s  loc_DD70
0xdd49  ldloca.s 3
0xdd4b  call     instance bool valuetype [System]System.Collections.Generic.SortedDictionary`2/Enumerator<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::MoveNext()
0xdd50  brtrue.s loc_DD25
0xdd52  leave.s  loc_DD6E
0xdd54  ldloca.s 3
0xdd56  constrained. valuetype [System]System.Collections.Generic.SortedDictionary`2/Enumerator<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>
0xdd5c  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xdd61  endfinally
0xdd62  leave.s  loc_DD6E
0xdd64  ldloc.0
0xdd65  brfalse.s loc_DD6D
0xdd67  ldloc.0
0xdd68  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xdd6d  endfinally
0xdd6e  ldc.i4.0
0xdd6f  ret
0xdd70  ldloc.s  5
0xdd72  ret
```
