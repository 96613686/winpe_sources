# Microsoft.Crm.CrmLive.Services.DirectoryObjectStateService::GetDirectoryObjectState

- ea: `0xf870`
- end: `0xf915`
- name: `Microsoft.Crm.CrmLive.Services.DirectoryObjectStateService::GetDirectoryObjectState`
- size: `165`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0xe710`
- `0xe7c0`

## callees

- `0xf870`

## string_xrefs

- `0xf8b7`: `DirectoryObjectState`
- `0xf900`: `D:\a\1\s\src\CrmLive\Admin\MicrosoftOnline\DirectoryObjectStateService.cs`
- `0xf871`: `configDbService`
- `0xf8fb`: `GetDirectoryObjectState`

## pseudocode

```c

```

## disassembly

```asm
0xf870  ldarg.0
0xf871  ldstr    aConfigdbservic// "configDbService"
0xf876  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0xf87b  ldarg.1
0xf87c  ldstr    aObjectid// "objectId"
0xf881  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfGuidEmpty(valuetype [mscorlib]System.Guid, string)
0xf886  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0xf88b  stloc.0
0xf88c  ldloc.0
0xf88d  ldstr    aObjectid_0// "ObjectId"
0xf892  ldc.i4.0
0xf893  ldarg.1
0xf894  box      [mscorlib]System.Guid
0xf899  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyComparison::.ctor(valuetype [Microsoft.Crm.Core]Microsoft.Crm.Data.ConditionalOperator, object)
0xf89e  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0xf8a3  ldarg.2
0xf8a4  brfalse.s loc_F8B7
0xf8a6  ldloc.0
0xf8a7  ldstr    aIstobeapplied// "IsToBeApplied"
0xf8ac  ldc.i4.1
0xf8ad  box      [mscorlib]System.Boolean
0xf8b2  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0xf8b7  ldstr    aDirectoryobjec// "DirectoryObjectState"
0xf8bc  ldnull
0xf8bd  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.StructuredQuery::.ctor(string, string[])
0xf8c2  stloc.1
0xf8c3  ldloc.1
0xf8c4  ldc.i4.1
0xf8c5  newobj   instance void valuetype [mscorlib]System.Nullable`1<int32>::.ctor(var<u1>)
0xf8ca  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.StructuredQuery::set_Top(valuetype [mscorlib]System.Nullable`1<int32>)
0xf8cf  ldloc.1
0xf8d0  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<class [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.QueryOrdering> [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.StructuredQuery::get_OrderBy()
0xf8d5  ldstr    aRevision// "Revision"
0xf8da  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.QueryOrdering::.ctor(string)
0xf8df  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<class [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.QueryOrdering>::Add(var<u1>)
0xf8e4  ldloc.1
0xf8e5  ldc.i4.1
0xf8e6  newarr   [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag
0xf8eb  dup
0xf8ec  ldc.i4.0
0xf8ed  ldloc.0
0xf8ee  stelem.ref
0xf8ef  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.StructuredQuery::SetConditions(class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag[])
0xf8f4  ldarg.0
0xf8f5  ldloc.1
0xf8f6  ldc.i4   0x230
0xf8fb  ldstr    aGetdirectoryob// "GetDirectoryObjectState"
0xf900  ldstr    aDA1SSrcCrmlive_20// "D:\\a\\1\\s\\src\\CrmLive\\Admin\\Micro"...
0xf905  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.OrderedPropertyBagCollection [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::Retrieve(class [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.StructuredQuery, int32, string, string)
0xf90a  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag> [Microsoft.Crm.Core]Microsoft.Crm.Data.OrderedPropertyBagCollection::RetrievePropertyBags()
0xf90f  call     T0x2B00004A
0xf914  ret
```
