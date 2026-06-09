# Microsoft.Crm.CrmLive.Services.DirectoryLinkService::RetrieveDirectoryUserLinksFromGroupByContext

- ea: `0xd9a0`
- end: `0xdabb`
- name: `Microsoft.Crm.CrmLive.Services.DirectoryLinkService::RetrieveDirectoryUserLinksFromGroupByContext`
- size: `283`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0xd960`

## callees

- `0xd9a0`
- `0xdb20`
- `0xf1b0`
- `0xf7e0`
- `0xf950`

## string_xrefs

- `0xda0b`: `D:\a\1\s\src\CrmLive\Admin\MicrosoftOnline\DirectoryLinkService.cs`
- `0xd9f4`: `DirectoryObjectState`
- `0xda06`: `RetrieveDirectoryUserLinksFromGroupByContext`

## pseudocode

```c

```

## disassembly

```asm
0xd9a0  ldarg.1
0xd9a1  ldstr    aContextid_0// "contextId"
0xd9a6  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfGuidEmpty(valuetype [mscorlib]System.Guid, string)
0xd9ab  ldarg.2
0xd9ac  ldstr    aGroupName// "Group Name"
0xd9b1  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string, string)
0xd9b6  newobj   instance void Microsoft.Crm.CrmLive.Services.DirectoryObjectStateService::.ctor()
0xd9bb  stloc.0
0xd9bc  call     class [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::NewService()
0xd9c1  stloc.1
0xd9c2  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0xd9c7  stloc.2
0xd9c8  ldloc.2
0xd9c9  ldstr    aContextid// "ContextId"
0xd9ce  ldarg.1
0xd9cf  box      [mscorlib]System.Guid
0xd9d4  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0xd9d9  ldloc.2
0xd9da  ldstr    aType// "Type"
0xd9df  ldtoken  [Microsoft.Crm.CrmLive.MicrosoftOnline.Client]Microsoft.Crm.CrmLive.MicrosoftOnline.Client.Group
0xd9e4  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xd9e9  call     string [Microsoft.Crm.CrmLive.MicrosoftOnline.Client]Microsoft.Crm.CrmLive.MicrosoftOnline.Client.DirectoryObjectSerializer::GetStringFromType(class [mscorlib]System.Type)
0xd9ee  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0xd9f3  ldloc.1
0xd9f4  ldstr    aDirectoryobjec// "DirectoryObjectState"
0xd9f9  ldnull
0xd9fa  ldc.i4.1
0xd9fb  newarr   [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag
0xda00  dup
0xda01  ldc.i4.0
0xda02  ldloc.2
0xda03  stelem.ref
0xda04  ldc.i4.s 0x46
0xda06  ldstr    aRetrievedirect// "RetrieveDirectoryUserLinksFromGroupByCo"...
0xda0b  ldstr    aDA1SSrcCrmlive_18// "D:\\a\\1\\s\\src\\CrmLive\\Admin\\Micro"...
0xda10  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBagCollection [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::Retrieve(string, string[], class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag[], int32, string, string)
0xda15  stloc.3
0xda16  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0xda1b  stloc.s  4
0xda1d  ldloc.3
0xda1e  call     bool [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBagCollection::IsNullOrEmpty(class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBagCollection)
0xda23  brtrue.s loc_DA8B
0xda25  ldloc.3
0xda26  callvirt instance class [System]System.Collections.Generic.SortedDictionary`2/ValueCollection<var<u1>, !!T0> class [System]System.Collections.Generic.SortedDictionary`2<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::get_Values()
0xda2b  callvirt instance valuetype [System]System.Collections.Generic.SortedDictionary`2/ValueCollection/Enumerator<var<u1>, !!T0> class [System]System.Collections.Generic.SortedDictionary`2/ValueCollection<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::GetEnumerator()
0xda30  stloc.s  5
0xda32  br.s     loc_DA72
0xda34  ldloca.s 5
0xda36  call     instance var<u1> valuetype [System]System.Collections.Generic.SortedDictionary`2/ValueCollection/Enumerator<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::get_Current()
0xda3b  stloc.s  6
0xda3d  ldloc.0
0xda3e  ldloc.s  6
0xda40  callvirt instance class [Microsoft.Crm.CrmLive.MicrosoftOnline.Client]Microsoft.Crm.CrmLive.MicrosoftOnline.Client.DirectoryObject Microsoft.Crm.CrmLive.Services.DirectoryObjectStateService::ConvertToDirectoryObject(class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag bag)
0xda45  castclass [Microsoft.Crm.CrmLive.MicrosoftOnline.Client]Microsoft.Crm.CrmLive.MicrosoftOnline.Client.Group
0xda4a  stloc.s  7
0xda4c  ldloc.0
0xda4d  ldloc.s  7
0xda4f  ldstr    aWellknownobjec// "WellKnownObject"
0xda54  callvirt instance string Microsoft.Crm.CrmLive.Services.DirectoryObjectStateService::RetrieveStringPropertyValue(class [Microsoft.Crm.CrmLive.MicrosoftOnline.Client]Microsoft.Crm.CrmLive.MicrosoftOnline.Client.DirectoryObject directoryObject, string propertyName)
0xda59  ldarg.2
0xda5a  ldc.i4.5
0xda5b  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0xda60  brfalse.s loc_DA72
0xda62  ldloc.s  7
0xda64  callvirt instance string [Microsoft.Crm.CrmLive.MicrosoftOnline.Client]Microsoft.Crm.CrmLive.MicrosoftOnline.Client.DirectoryObject::get_ObjectId()
0xda69  call     valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Parse(string)
0xda6e  stloc.s  4
0xda70  leave.s  loc_DA8B
0xda72  ldloca.s 5
0xda74  call     instance bool valuetype [System]System.Collections.Generic.SortedDictionary`2/ValueCollection/Enumerator<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::MoveNext()
0xda79  brtrue.s loc_DA34
0xda7b  leave.s  loc_DA8B
0xda7d  ldloca.s 5
0xda7f  constrained. valuetype [System]System.Collections.Generic.SortedDictionary`2/ValueCollection/Enumerator<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>
0xda85  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xda8a  endfinally
0xda8b  ldloc.s  4
0xda8d  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0xda92  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0xda97  brfalse.s loc_DAA6
0xda99  ldarg.1
0xda9a  ldloc.s  4
0xda9c  ldnull
0xda9d  call     class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag> Microsoft.Crm.CrmLive.Services.DirectoryLinkService::RetrieveDirectoryUserLinksFromGroupByContextAsPropertyBags(valuetype [mscorlib]System.Guid contextId, valuetype [mscorlib]System.Guid securityGroupId, string[] columns)
0xdaa2  stloc.s  8
0xdaa4  leave.s  loc_DAB8
0xdaa6  leave.s  loc_DAB2
0xdaa8  ldloc.1
0xdaa9  brfalse.s loc_DAB1
0xdaab  ldloc.1
0xdaac  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xdab1  endfinally
0xdab2  call     T0x2B00003D
0xdab7  ret
0xdab8  ldloc.s  8
0xdaba  ret
```
