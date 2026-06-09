# Microsoft.Crm.ServerLocatorService::GetChangeNotificationEventHubConnectionString

- ea: `0x80e0`
- end: `0x8186`
- name: `Microsoft.Crm.ServerLocatorService::GetChangeNotificationEventHubConnectionString`
- size: `166`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x80e0`
- `0x92c0`
- `0x1be90`
- `0x39050`
- `0x444f0`
- `0x44670`

## string_xrefs

- `0x8111`: `D:\a\1\s\src\Platform\Core\DataServices\Configuration\LocatorService\ServerLocatorService.cs`
- `0x8157`: `D:\a\1\s\src\Platform\Core\DataServices\Configuration\LocatorService\ServerLocatorService.cs`

## pseudocode

```c

```

## disassembly

```asm
0x80e0  ldarg.1
0x80e1  ldstr    aOrganizationid_0// "organizationId"
0x80e6  call     void Microsoft.Crm.Exceptions::ThrowIfGuidEmpty(valuetype [mscorlib]System.Guid parameter, string name)
0x80eb  ldstr    aChangenotifica// "ChangeNotificationEventHubId"
0x80f0  stloc.0
0x80f1  ldarg.0
0x80f2  ldstr    aOrganization// "Organization"
0x80f7  ldarg.1
0x80f8  box      [mscorlib]System.Guid
0x80fd  ldc.i4.1
0x80fe  newarr   [mscorlib]System.String
0x8103  dup
0x8104  ldc.i4.0
0x8105  ldloc.0
0x8106  stelem.ref
0x8107  ldc.i4   0x3FF
0x810c  ldstr    aGetchangenotif// "GetChangeNotificationEventHubConnection"...
0x8111  ldstr    aDA1SSrcPlatfor_1// "D:\\a\\1\\s\\src\\Platform\\Core\\DataS"...
0x8116  call     instance class Microsoft.Crm.Data.PropertyBag Microsoft.Crm.ServerLocatorService::RetrieveById(string tableName, object primaryKey, string[] columns, [opt] int32 sourceLineNumber, [opt] string memberName, [opt] string sourceFilePath)
0x811b  stloc.1
0x811c  ldloc.1
0x811d  brfalse.s loc_8180
0x811f  ldloc.1
0x8120  ldloc.0
0x8121  callvirt instance object Microsoft.Crm.Data.PropertyBag::get_Item(string propertyName)
0x8126  castclass [mscorlib]System.String
0x812b  stloc.2
0x812c  ldstr    aAzureresourcec// "AzureResourceConnectionString"
0x8131  stloc.0
0x8132  ldarg.0
0x8133  ldstr    aAzureresource// "AzureResource"
0x8138  ldloc.2
0x8139  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x813e  box      [mscorlib]System.Guid
0x8143  ldc.i4.1
0x8144  newarr   [mscorlib]System.String
0x8149  dup
0x814a  ldc.i4.0
0x814b  ldloc.0
0x814c  stelem.ref
0x814d  ldc.i4   0x405
0x8152  ldstr    aGetchangenotif// "GetChangeNotificationEventHubConnection"...
0x8157  ldstr    aDA1SSrcPlatfor_1// "D:\\a\\1\\s\\src\\Platform\\Core\\DataS"...
0x815c  call     instance class Microsoft.Crm.Data.PropertyBag Microsoft.Crm.ServerLocatorService::RetrieveById(string tableName, object primaryKey, string[] columns, [opt] int32 sourceLineNumber, [opt] string memberName, [opt] string sourceFilePath)
0x8161  stloc.1
0x8162  ldloc.1
0x8163  brfalse.s loc_8180
0x8165  ldloc.1
0x8166  ldloc.0
0x8167  callvirt instance bool Microsoft.Crm.Data.PropertyBag::Contains(string propertyName)
0x816c  brfalse.s loc_8180
0x816e  ldloc.1
0x816f  ldloc.0
0x8170  callvirt instance object Microsoft.Crm.Data.PropertyBag::get_Item(string propertyName)
0x8175  castclass [mscorlib]System.Security.SecureString
0x817a  call     string Microsoft.Crm.CrmKeyService::GetStringFromSecureString(class [mscorlib]System.Security.SecureString secureString)
0x817f  ret
0x8180  ldsfld   string [mscorlib]System.String::Empty
0x8185  ret
```
