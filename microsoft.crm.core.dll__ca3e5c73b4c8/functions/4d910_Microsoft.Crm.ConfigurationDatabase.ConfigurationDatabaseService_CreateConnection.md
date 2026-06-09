# Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::CreateConnection

- ea: `0x4d910`
- end: `0x4d9a1`
- name: `Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::CreateConnection`
- size: `145`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x4640`
- `0x4c00`
- `0x100b0`
- `0x1b5d0`
- `0x444f0`
- `0x4a700`
- `0x4a830`
- `0x4d910`
- `0x4dcb0`
- `0x4dda0`

## string_xrefs

- `0x4d97d`: `CreateConnection`
- `0x4d982`: `D:\a\1\s\src\Platform\Core\DataServices\Configuration\ObjectModel\ConfigurationDatabase.cs`

## pseudocode

```c

```

## disassembly

```asm
0x4d910  ldarg.1
0x4d911  call     valuetype Microsoft.Crm.SharedDatabase.ConfigScope Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::GetScope(valuetype Microsoft.Crm.SharedDatabase.ConfigScope scope)
0x4d916  stloc.0
0x4d917  ldarg.0
0x4d918  ldfld    class Microsoft.Crm.CrmDbConnection Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::_connection
0x4d91d  brfalse.s loc_4D93A
0x4d91f  ldloc.0
0x4d920  ldarg.0
0x4d921  ldfld    valuetype Microsoft.Crm.SharedDatabase.ConfigScope Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::_connectionScope
0x4d926  beq.s    loc_4D933
0x4d928  ldstr    aCannotInteract// "Cannot interact with tables in differen"...
0x4d92d  newobj   instance void Microsoft.Crm.CrmInvalidOperationException::.ctor(string message)
0x4d932  throw
0x4d933  ldarg.0
0x4d934  ldfld    class Microsoft.Crm.CrmDbConnection Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::_connection
0x4d939  ret
0x4d93a  ldloc.0
0x4d93b  brtrue.s loc_4D949
0x4d93d  ldarg.0
0x4d93e  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::_datacenterId
0x4d943  call     class Microsoft.Crm.CrmDbConnection Microsoft.Crm.ConfigurationDatabase.ConfigurationMetadata::GetSiteConfigDBConnection(valuetype [mscorlib]System.Guid datacenterId)
0x4d948  ret
0x4d949  ldc.i4.2
0x4d94a  ldloc.0
0x4d94b  bne.un.s loc_4D953
0x4d94d  call     class Microsoft.Crm.CrmDbConnection Microsoft.Crm.ConfigurationDatabase.ConfigurationMetadata::GetGeoConfigDBConnection()
0x4d952  ret
0x4d953  ldarg.0
0x4d954  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::get_ScaleGroupId()
0x4d959  stloc.1
0x4d95a  call     class Microsoft.Crm.LocatorService Microsoft.Crm.LocatorService::get_Instance()
0x4d95f  ldstr    aScalegroup// "ScaleGroup"
0x4d964  ldloc.1
0x4d965  box      [mscorlib]System.Guid
0x4d96a  ldc.i4.1
0x4d96b  newarr   [mscorlib]System.String
0x4d970  dup
0x4d971  ldc.i4.0
0x4d972  ldstr    aConnectionstri_0// "ConnectionString"
0x4d977  stelem.ref
0x4d978  ldc.i4   0xAB
0x4d97d  ldstr    aCreateconnecti// "CreateConnection"
0x4d982  ldstr    aDA1SSrcPlatfor_36// "D:\\a\\1\\s\\src\\Platform\\Core\\DataS"...
0x4d987  callvirt instance class Microsoft.Crm.Data.PropertyBag Microsoft.Crm.LocatorService::RetrieveById(string tableName, object primaryKey, string[] columns, [opt] int32 sourceLineNumber, [opt] string memberName, [opt] string sourceFilePath)
0x4d98c  ldstr    aConnectionstri_0// "ConnectionString"
0x4d991  callvirt instance object Microsoft.Crm.Data.PropertyBag::get_Item(string propertyName)
0x4d996  castclass [mscorlib]System.String
0x4d99b  newobj   instance void Microsoft.Crm.CrmScaleGroupConfigDBConnection::.ctor(string connectionString)
0x4d9a0  ret
```
