# Microsoft.Crm.ServerLocatorService::GetOrgApplicationMapSettingSkipCache

- ea: `0xb750`
- end: `0xb892`
- name: `Microsoft.Crm.ServerLocatorService::GetOrgApplicationMapSettingSkipCache`
- size: `322`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0xae80`

## callees

- `0xb750`
- `0x1be90`
- `0x1c060`
- `0x39050`
- `0x44400`
- `0x444f0`
- `0x44510`
- `0x44670`
- `0x4d750`
- `0x61420`

## string_xrefs

- `0xb7b5`: `D:\a\1\s\src\Platform\Core\DataServices\Configuration\LocatorService\ServerLocatorService.cs`
- `0xb823`: `D:\a\1\s\src\Platform\Core\DataServices\Configuration\LocatorService\ServerLocatorService.cs`
- `0xb7b0`: `GetOrgApplicationMapSettingSkipCache`
- `0xb81e`: `GetOrgApplicationMapSettingSkipCache`

## pseudocode

```c

```

## disassembly

```asm
0xb750  ldarg.1
0xb751  ldstr    aOrganizationid_0// "organizationId"
0xb756  call     void Microsoft.Crm.Exceptions::ThrowIfGuidEmpty(valuetype [mscorlib]System.Guid parameter, string name)
0xb75b  ldarg.3
0xb75c  ldstr    aSettingname// "settingName"
0xb761  call     void Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string parameter, string name)
0xb766  ldnull
0xb767  stloc.0
0xb768  newobj   instance void Microsoft.Crm.Data.PropertyBag::.ctor()
0xb76d  stloc.1
0xb76e  ldloc.1
0xb76f  ldstr    aOrganizationid_1// "OrganizationId"
0xb774  ldarg.1
0xb775  box      [mscorlib]System.Guid
0xb77a  callvirt instance void Microsoft.Crm.Data.PropertyBag::set_Item(string propertyName, object value)
0xb77f  ldloc.1
0xb780  ldstr    aOrgapplication// "OrgApplicationType"
0xb785  ldarg.2
0xb786  box      [mscorlib]System.Int32
0xb78b  callvirt instance void Microsoft.Crm.Data.PropertyBag::set_Item(string propertyName, object value)
0xb790  newobj   instance void Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::.ctor()
0xb795  stloc.2
0xb796  ldloc.2
0xb797  ldstr    aOrgapplication_0// "OrgApplicationMap"
0xb79c  ldc.i4.1
0xb79d  newarr   [mscorlib]System.String
0xb7a2  dup
0xb7a3  ldc.i4.0
0xb7a4  ldstr    aId// "Id"
0xb7a9  stelem.ref
0xb7aa  ldloc.1
0xb7ab  ldc.i4   0xC4D
0xb7b0  ldstr    aGetorgapplicat_0// "GetOrgApplicationMapSettingSkipCache"
0xb7b5  ldstr    aDA1SSrcPlatfor_1// "D:\\a\\1\\s\\src\\Platform\\Core\\DataS"...
0xb7ba  callvirt instance class Microsoft.Crm.Data.PropertyBag Microsoft.Crm.SharedDatabase.DatabaseService::RetrieveSingleItem(string tableName, string[] columns, class Microsoft.Crm.Data.PropertyBag conditions, [opt] int32 sourceLineNumber, [opt] string memberName, [opt] string sourceFilePath)
0xb7bf  stloc.3
0xb7c0  ldloc.3
0xb7c1  brfalse  loc_B884
0xb7c6  ldloc.3
0xb7c7  ldstr    aId// "Id"
0xb7cc  callvirt instance object Microsoft.Crm.Data.PropertyBag::get_Item(string propertyName)
0xb7d1  brfalse  loc_B884
0xb7d6  ldloca.s 4
0xb7d8  ldloc.3
0xb7d9  ldstr    aId// "Id"
0xb7de  callvirt instance object Microsoft.Crm.Data.PropertyBag::get_Item(string propertyName)
0xb7e3  callvirt instance string [mscorlib]System.Object::ToString()
0xb7e8  call     instance void [mscorlib]System.Guid::.ctor(string)
0xb7ed  newobj   instance void Microsoft.Crm.Data.PropertyBag::.ctor()
0xb7f2  stloc.s  5
0xb7f4  ldloc.s  5
0xb7f6  ldstr    aId// "Id"
0xb7fb  ldloc.s  4
0xb7fd  box      [mscorlib]System.Guid
0xb802  callvirt instance void Microsoft.Crm.Data.PropertyBag::set_Item(string propertyName, object value)
0xb807  ldloc.2
0xb808  ldstr    aOrgapplication_0// "OrgApplicationMap"
0xb80d  ldc.i4.1
0xb80e  newarr   [mscorlib]System.String
0xb813  dup
0xb814  ldc.i4.0
0xb815  ldarg.3
0xb816  stelem.ref
0xb817  ldloc.s  5
0xb819  ldc.i4   0xC57
0xb81e  ldstr    aGetorgapplicat_0// "GetOrgApplicationMapSettingSkipCache"
0xb823  ldstr    aDA1SSrcPlatfor_1// "D:\\a\\1\\s\\src\\Platform\\Core\\DataS"...
0xb828  callvirt instance class Microsoft.Crm.Data.PropertyBag Microsoft.Crm.SharedDatabase.DatabaseService::RetrieveSingleItem(string tableName, string[] columns, class Microsoft.Crm.Data.PropertyBag conditions, [opt] int32 sourceLineNumber, [opt] string memberName, [opt] string sourceFilePath)
0xb82d  stloc.s  6
0xb82f  ldloc.s  6
0xb831  brfalse.s loc_B884
0xb833  ldloc.s  6
0xb835  ldarg.3
0xb836  callvirt instance bool Microsoft.Crm.Data.PropertyBag::Contains(string propertyName)
0xb83b  brfalse.s loc_B884
0xb83d  ldloc.s  6
0xb83f  ldarg.3
0xb840  callvirt instance object Microsoft.Crm.Data.PropertyBag::get_Item(string propertyName)
0xb845  stloc.s  7
0xb847  ldloc.s  7
0xb849  brfalse.s loc_B884
0xb84b  ldloc.s  7
0xb84d  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0xb852  beq.s    loc_B884
0xb854  ldarg.3
0xb855  ldstr    aStagingdbconne// "StagingDbConnectionString"
0xb85a  call     bool [mscorlib]System.String::op_Equality(string, string)
0xb85f  brfalse.s loc_B876
0xb861  ldloc.s  6
0xb863  ldarg.3
0xb864  callvirt instance object Microsoft.Crm.Data.PropertyBag::get_Item(string propertyName)
0xb869  castclass [mscorlib]System.Security.SecureString
0xb86e  call     string Microsoft.Crm.CrmKeyService::GetStringFromSecureString(class [mscorlib]System.Security.SecureString secureString)
0xb873  stloc.0
0xb874  leave.s  loc_B890
0xb876  ldloc.s  6
0xb878  ldarg.3
0xb879  callvirt instance object Microsoft.Crm.Data.PropertyBag::get_Item(string propertyName)
0xb87e  callvirt instance string [mscorlib]System.Object::ToString()
0xb883  stloc.0
0xb884  leave.s  loc_B890
0xb886  ldloc.2
0xb887  brfalse.s loc_B88F
0xb889  ldloc.2
0xb88a  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xb88f  endfinally
0xb890  ldloc.0
0xb891  ret
```
