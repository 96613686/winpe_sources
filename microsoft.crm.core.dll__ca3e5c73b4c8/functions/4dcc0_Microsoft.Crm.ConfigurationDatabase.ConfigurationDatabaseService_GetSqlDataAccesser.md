# Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::GetSqlDataAccesser

- ea: `0x4dcc0`
- end: `0x4dd6a`
- name: `Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::GetSqlDataAccesser`
- size: `170`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x4640`
- `0x4c00`
- `0x1b5d0`
- `0x444f0`
- `0x4a710`
- `0x4a840`
- `0x4dcb0`
- `0x4dcc0`
- `0x4dda0`
- `0x5b6e0`

## string_xrefs

- `0x4dd36`: `D:\a\1\s\src\Platform\Core\DataServices\Configuration\ObjectModel\ConfigurationDatabase.cs`
- `0x4dd31`: `GetSqlDataAccesser`

## pseudocode

```c

```

## disassembly

```asm
0x4dcc0  ldarg.1
0x4dcc1  call     valuetype Microsoft.Crm.SharedDatabase.ConfigScope Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::GetScope(valuetype Microsoft.Crm.SharedDatabase.ConfigScope scope)
0x4dcc6  stloc.0
0x4dcc7  call     class [System.Transactions]System.Transactions.Transaction [System.Transactions]System.Transactions.Transaction::get_Current()
0x4dccc  ldnull
0x4dccd  call     bool [System.Transactions]System.Transactions.Transaction::op_Inequality(class [System.Transactions]System.Transactions.Transaction, class [System.Transactions]System.Transactions.Transaction)
0x4dcd2  brfalse.s loc_4DCE8
0x4dcd4  ldloc.0
0x4dcd5  ldarg.0
0x4dcd6  ldfld    valuetype Microsoft.Crm.SharedDatabase.ConfigScope Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::_connectionScope
0x4dcdb  beq.s    loc_4DCE8
0x4dcdd  ldstr    aCannotInteract// "Cannot interact with tables in differen"...
0x4dce2  newobj   instance void Microsoft.Crm.CrmInvalidOperationException::.ctor(string message)
0x4dce7  throw
0x4dce8  ldnull
0x4dce9  stloc.1
0x4dcea  ldloc.0
0x4dceb  brtrue.s loc_4DCFB
0x4dced  ldarg.0
0x4dcee  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::_datacenterId
0x4dcf3  call     string Microsoft.Crm.ConfigurationDatabase.ConfigurationMetadata::GetSiteConfigDBConnectionString(valuetype [mscorlib]System.Guid datacenterId)
0x4dcf8  stloc.1
0x4dcf9  br.s     loc_4DD50
0x4dcfb  ldc.i4.2
0x4dcfc  ldloc.0
0x4dcfd  bne.un.s loc_4DD07
0x4dcff  call     string Microsoft.Crm.ConfigurationDatabase.ConfigurationMetadata::GetGeoConfigDBConnectionString()
0x4dd04  stloc.1
0x4dd05  br.s     loc_4DD50
0x4dd07  ldarg.0
0x4dd08  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::get_ScaleGroupId()
0x4dd0d  stloc.2
0x4dd0e  call     class Microsoft.Crm.LocatorService Microsoft.Crm.LocatorService::get_Instance()
0x4dd13  ldstr    aScalegroup// "ScaleGroup"
0x4dd18  ldloc.2
0x4dd19  box      [mscorlib]System.Guid
0x4dd1e  ldc.i4.1
0x4dd1f  newarr   [mscorlib]System.String
0x4dd24  dup
0x4dd25  ldc.i4.0
0x4dd26  ldstr    aConnectionstri_0// "ConnectionString"
0x4dd2b  stelem.ref
0x4dd2c  ldc.i4   0x1F0
0x4dd31  ldstr    aGetsqldataacce// "GetSqlDataAccesser"
0x4dd36  ldstr    aDA1SSrcPlatfor_36// "D:\\a\\1\\s\\src\\Platform\\Core\\DataS"...
0x4dd3b  callvirt instance class Microsoft.Crm.Data.PropertyBag Microsoft.Crm.LocatorService::RetrieveById(string tableName, object primaryKey, string[] columns, [opt] int32 sourceLineNumber, [opt] string memberName, [opt] string sourceFilePath)
0x4dd40  ldstr    aConnectionstri_0// "ConnectionString"
0x4dd45  callvirt instance object Microsoft.Crm.Data.PropertyBag::get_Item(string propertyName)
0x4dd4a  castclass [mscorlib]System.String
0x4dd4f  stloc.1
0x4dd50  ldsfld   class Microsoft.Crm.Core.DataServices.Connection.CrmSqlAccesserFactory Microsoft.Crm.Core.DataServices.Connection.CrmSqlAccesserFactory::DefaultInstance
0x4dd55  ldloc.1
0x4dd56  ldloca.s 3
0x4dd58  initobj  valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>
0x4dd5e  ldloc.3
0x4dd5f  ldc.i4.0
0x4dd60  ldc.i4.0
0x4dd61  ldnull
0x4dd62  ldc.i4.0
0x4dd63  ldc.i4.0
0x4dd64  callvirt instance class Microsoft.Crm.Core.SqlAccess.ISqlDataAccess Microsoft.Crm.Core.DataServices.Connection.CrmSqlAccesserFactory::Get(string connectionString, [opt] valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> organizationId, [opt] valuetype Microsoft.Crm.ConnectionAccessType accessType, [opt] int32 sqlMaxPoolSize, [opt] string workloadGroup, [opt] bool enableMars, [opt] int32 defaultCommandTimeout)
0x4dd69  ret
```
