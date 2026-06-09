# Microsoft.Crm.CrmLive.Services.DirectoryObjectStateService::RetrieveCompanyObjectByContext

- ea: `0xf690`
- end: `0xf71f`
- name: `Microsoft.Crm.CrmLive.Services.DirectoryObjectStateService::RetrieveCompanyObjectByContext`
- size: `143`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0xf5f0`

## callees

- `0xf690`
- `0xf7e0`

## string_xrefs

- `0xf6d3`: `DirectoryObjectState`
- `0xf6f9`: `D:\a\1\s\src\CrmLive\Admin\MicrosoftOnline\DirectoryObjectStateService.cs`
- `0xf6f4`: `RetrieveCompanyObjectByContext`

## pseudocode

```c

```

## disassembly

```asm
0xf690  ldarg.1
0xf691  ldstr    aContextid_0// "contextId"
0xf696  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfGuidEmpty(valuetype [mscorlib]System.Guid, string)
0xf69b  call     class [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::NewService()
0xf6a0  stloc.0
0xf6a1  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0xf6a6  stloc.1
0xf6a7  ldloc.1
0xf6a8  ldstr    aContextid// "ContextId"
0xf6ad  ldarg.1
0xf6ae  box      [mscorlib]System.Guid
0xf6b3  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0xf6b8  ldloc.1
0xf6b9  ldstr    aType// "Type"
0xf6be  ldtoken  [Microsoft.Crm.CrmLive.MicrosoftOnline.Client]Microsoft.Crm.CrmLive.MicrosoftOnline.Client.Company
0xf6c3  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xf6c8  call     string [Microsoft.Crm.CrmLive.MicrosoftOnline.Client]Microsoft.Crm.CrmLive.MicrosoftOnline.Client.DirectoryObjectSerializer::GetStringFromType(class [mscorlib]System.Type)
0xf6cd  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0xf6d2  ldloc.0
0xf6d3  ldstr    aDirectoryobjec// "DirectoryObjectState"
0xf6d8  ldc.i4.2
0xf6d9  newarr   [mscorlib]System.String
0xf6de  dup
0xf6df  ldc.i4.0
0xf6e0  ldstr    aData// "Data"
0xf6e5  stelem.ref
0xf6e6  dup
0xf6e7  ldc.i4.1
0xf6e8  ldstr    aType// "Type"
0xf6ed  stelem.ref
0xf6ee  ldloc.1
0xf6ef  ldc.i4   0x1E9
0xf6f4  ldstr    aRetrievecompan_0// "RetrieveCompanyObjectByContext"
0xf6f9  ldstr    aDA1SSrcCrmlive_20// "D:\\a\\1\\s\\src\\CrmLive\\Admin\\Micro"...
0xf6fe  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::RetrieveSingleItem(string, string[], class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag, int32, string, string)
0xf703  stloc.2
0xf704  ldarg.0
0xf705  ldloc.2
0xf706  call     instance class [Microsoft.Crm.CrmLive.MicrosoftOnline.Client]Microsoft.Crm.CrmLive.MicrosoftOnline.Client.DirectoryObject Microsoft.Crm.CrmLive.Services.DirectoryObjectStateService::ConvertToDirectoryObject(class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag bag)
0xf70b  castclass [Microsoft.Crm.CrmLive.MicrosoftOnline.Client]Microsoft.Crm.CrmLive.MicrosoftOnline.Client.Company
0xf710  stloc.3
0xf711  leave.s  loc_F71D
0xf713  ldloc.0
0xf714  brfalse.s loc_F71C
0xf716  ldloc.0
0xf717  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xf71c  endfinally
0xf71d  ldloc.3
0xf71e  ret
```
