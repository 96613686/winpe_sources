# Microsoft.Crm.ServerLocatorService::GetConnectionString

- ea: `0x8380`
- end: `0x8493`
- name: `Microsoft.Crm.ServerLocatorService::GetConnectionString`
- size: `275`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x3080`
- `0x8380`
- `0x92c0`
- `0x1be90`
- `0x444f0`

## string_xrefs

- `0x83c1`: `D:\a\1\s\src\Platform\Core\DataServices\Configuration\LocatorService\ServerLocatorService.cs`
- `0x840f`: `D:\a\1\s\src\Platform\Core\DataServices\Configuration\LocatorService\ServerLocatorService.cs`
- `0x8454`: `D:\a\1\s\src\Platform\Core\DataServices\Configuration\LocatorService\ServerLocatorService.cs`
- `0x83b1`: `ConnectionStringReadOnly`
- `0x83d0`: `ConnectionStringReadOnly`

## pseudocode

```c

```

## disassembly

```asm
0x8380  ldarg.1
0x8381  ldstr    aOrganizationid_0// "organizationId"
0x8386  call     void Microsoft.Crm.Exceptions::ThrowIfGuidEmpty(valuetype [mscorlib]System.Guid parameter, string name)
0x838b  ldsfld   string [mscorlib]System.String::Empty
0x8390  stloc.0
0x8391  ldarg.2
0x8392  brfalse  loc_8430
0x8397  ldarg.3
0x8398  brfalse  loc_8430
0x839d  ldarg.0
0x839e  ldstr    aOrganization// "Organization"
0x83a3  ldarg.1
0x83a4  box      [mscorlib]System.Guid
0x83a9  ldc.i4.1
0x83aa  newarr   [mscorlib]System.String
0x83af  dup
0x83b0  ldc.i4.0
0x83b1  ldstr    aConnectionstri_1// "ConnectionStringReadOnly"
0x83b6  stelem.ref
0x83b7  ldc.i4   0x45E
0x83bc  ldstr    aGetconnections// "GetConnectionString"
0x83c1  ldstr    aDA1SSrcPlatfor_1// "D:\\a\\1\\s\\src\\Platform\\Core\\DataS"...
0x83c6  call     instance class Microsoft.Crm.Data.PropertyBag Microsoft.Crm.ServerLocatorService::RetrieveById(string tableName, object primaryKey, string[] columns, [opt] int32 sourceLineNumber, [opt] string memberName, [opt] string sourceFilePath)
0x83cb  stloc.1
0x83cc  ldloc.1
0x83cd  brfalse.s loc_83E0
0x83cf  ldloc.1
0x83d0  ldstr    aConnectionstri_1// "ConnectionStringReadOnly"
0x83d5  callvirt instance object Microsoft.Crm.Data.PropertyBag::get_Item(string propertyName)
0x83da  castclass [mscorlib]System.String
0x83df  stloc.0
0x83e0  ldloc.0
0x83e1  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x83e6  brfalse  loc_8473
0x83eb  ldarg.0
0x83ec  ldstr    aOrganization// "Organization"
0x83f1  ldarg.1
0x83f2  box      [mscorlib]System.Guid
0x83f7  ldc.i4.1
0x83f8  newarr   [mscorlib]System.String
0x83fd  dup
0x83fe  ldc.i4.0
0x83ff  ldstr    aConnectionstri_0// "ConnectionString"
0x8404  stelem.ref
0x8405  ldc.i4   0x469
0x840a  ldstr    aGetconnections// "GetConnectionString"
0x840f  ldstr    aDA1SSrcPlatfor_1// "D:\\a\\1\\s\\src\\Platform\\Core\\DataS"...
0x8414  call     instance class Microsoft.Crm.Data.PropertyBag Microsoft.Crm.ServerLocatorService::RetrieveById(string tableName, object primaryKey, string[] columns, [opt] int32 sourceLineNumber, [opt] string memberName, [opt] string sourceFilePath)
0x8419  stloc.2
0x841a  ldloc.2
0x841b  brfalse.s loc_8473
0x841d  ldloc.2
0x841e  ldstr    aConnectionstri_0// "ConnectionString"
0x8423  callvirt instance object Microsoft.Crm.Data.PropertyBag::get_Item(string propertyName)
0x8428  castclass [mscorlib]System.String
0x842d  stloc.0
0x842e  br.s     loc_8473
0x8430  ldarg.0
0x8431  ldstr    aOrganization// "Organization"
0x8436  ldarg.1
0x8437  box      [mscorlib]System.Guid
0x843c  ldc.i4.1
0x843d  newarr   [mscorlib]System.String
0x8442  dup
0x8443  ldc.i4.0
0x8444  ldstr    aConnectionstri_0// "ConnectionString"
0x8449  stelem.ref
0x844a  ldc.i4   0x473
0x844f  ldstr    aGetconnections// "GetConnectionString"
0x8454  ldstr    aDA1SSrcPlatfor_1// "D:\\a\\1\\s\\src\\Platform\\Core\\DataS"...
0x8459  call     instance class Microsoft.Crm.Data.PropertyBag Microsoft.Crm.ServerLocatorService::RetrieveById(string tableName, object primaryKey, string[] columns, [opt] int32 sourceLineNumber, [opt] string memberName, [opt] string sourceFilePath)
0x845e  stloc.3
0x845f  ldloc.3
0x8460  brfalse.s loc_8473
0x8462  ldloc.3
0x8463  ldstr    aConnectionstri_0// "ConnectionString"
0x8468  callvirt instance object Microsoft.Crm.Data.PropertyBag::get_Item(string propertyName)
0x846d  castclass [mscorlib]System.String
0x8472  stloc.0
0x8473  ldloc.0
0x8474  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x8479  brtrue.s loc_847D
0x847b  ldloc.0
0x847c  ret
0x847d  ldstr    aOrganization// "Organization"
0x8482  ldstr    aId// "Id"
0x8487  ldarg.1
0x8488  box      [mscorlib]System.Guid
0x848d  newobj   instance void Microsoft.Crm.CrmConfigObjectNotFoundException::.ctor(string tableName, string columnName, object id)
0x8492  throw
```
