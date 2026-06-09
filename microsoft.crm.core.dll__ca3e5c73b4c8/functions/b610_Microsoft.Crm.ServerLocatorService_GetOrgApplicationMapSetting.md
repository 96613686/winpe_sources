# Microsoft.Crm.ServerLocatorService::GetOrgApplicationMapSetting

- ea: `0xb610`
- end: `0xb747`
- name: `Microsoft.Crm.ServerLocatorService::GetOrgApplicationMapSetting`
- size: `311`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x4640`
- `0x4c60`
- `0xb610`
- `0x1be90`
- `0x1c060`
- `0x39050`
- `0x44400`
- `0x444f0`
- `0x44510`
- `0x44670`

## string_xrefs

- `0xb673`: `D:\a\1\s\src\Platform\Core\DataServices\Configuration\LocatorService\ServerLocatorService.cs`
- `0xb6e4`: `D:\a\1\s\src\Platform\Core\DataServices\Configuration\LocatorService\ServerLocatorService.cs`

## pseudocode

```c

```

## disassembly

```asm
0xb610  ldarg.1
0xb611  ldstr    aOrganizationid_0// "organizationId"
0xb616  call     void Microsoft.Crm.Exceptions::ThrowIfGuidEmpty(valuetype [mscorlib]System.Guid parameter, string name)
0xb61b  ldarg.3
0xb61c  ldstr    aSettingname// "settingName"
0xb621  call     void Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string parameter, string name)
0xb626  ldnull
0xb627  stloc.0
0xb628  newobj   instance void Microsoft.Crm.Data.PropertyBag::.ctor()
0xb62d  stloc.1
0xb62e  ldloc.1
0xb62f  ldstr    aOrganizationid_1// "OrganizationId"
0xb634  ldarg.1
0xb635  box      [mscorlib]System.Guid
0xb63a  callvirt instance void Microsoft.Crm.Data.PropertyBag::set_Item(string propertyName, object value)
0xb63f  ldloc.1
0xb640  ldstr    aOrgapplication// "OrgApplicationType"
0xb645  ldarg.2
0xb646  box      [mscorlib]System.Int32
0xb64b  callvirt instance void Microsoft.Crm.Data.PropertyBag::set_Item(string propertyName, object value)
0xb650  call     class Microsoft.Crm.LocatorService Microsoft.Crm.LocatorService::get_Instance()
0xb655  ldstr    aOrgapplication_0// "OrgApplicationMap"
0xb65a  ldc.i4.1
0xb65b  newarr   [mscorlib]System.String
0xb660  dup
0xb661  ldc.i4.0
0xb662  ldstr    aId// "Id"
0xb667  stelem.ref
0xb668  ldloc.1
0xb669  ldc.i4   0xC18
0xb66e  ldstr    aGetorgapplicat// "GetOrgApplicationMapSetting"
0xb673  ldstr    aDA1SSrcPlatfor_1// "D:\\a\\1\\s\\src\\Platform\\Core\\DataS"...
0xb678  callvirt instance class Microsoft.Crm.Data.PropertyBag Microsoft.Crm.LocatorService::RetrieveSingleRow(string tableName, string[] columns, class Microsoft.Crm.Data.PropertyBag conditions, [opt] int32 sourceLineNumber, [opt] string memberName, [opt] string sourceFilePath)
0xb67d  stloc.2
0xb67e  ldloc.2
0xb67f  brfalse  loc_B745
0xb684  ldloc.2
0xb685  ldstr    aId// "Id"
0xb68a  callvirt instance object Microsoft.Crm.Data.PropertyBag::get_Item(string propertyName)
0xb68f  brfalse  loc_B745
0xb694  ldloca.s 3
0xb696  ldloc.2
0xb697  ldstr    aId// "Id"
0xb69c  callvirt instance object Microsoft.Crm.Data.PropertyBag::get_Item(string propertyName)
0xb6a1  callvirt instance string [mscorlib]System.Object::ToString()
0xb6a6  call     instance void [mscorlib]System.Guid::.ctor(string)
0xb6ab  newobj   instance void Microsoft.Crm.Data.PropertyBag::.ctor()
0xb6b0  stloc.s  4
0xb6b2  ldloc.s  4
0xb6b4  ldstr    aId// "Id"
0xb6b9  ldloc.3
0xb6ba  box      [mscorlib]System.Guid
0xb6bf  callvirt instance void Microsoft.Crm.Data.PropertyBag::set_Item(string propertyName, object value)
0xb6c4  call     class Microsoft.Crm.LocatorService Microsoft.Crm.LocatorService::get_Instance()
0xb6c9  ldstr    aOrgapplication_0// "OrgApplicationMap"
0xb6ce  ldc.i4.1
0xb6cf  newarr   [mscorlib]System.String
0xb6d4  dup
0xb6d5  ldc.i4.0
0xb6d6  ldarg.3
0xb6d7  stelem.ref
0xb6d8  ldloc.s  4
0xb6da  ldc.i4   0xC22
0xb6df  ldstr    aGetorgapplicat// "GetOrgApplicationMapSetting"
0xb6e4  ldstr    aDA1SSrcPlatfor_1// "D:\\a\\1\\s\\src\\Platform\\Core\\DataS"...
0xb6e9  callvirt instance class Microsoft.Crm.Data.PropertyBag Microsoft.Crm.LocatorService::RetrieveSingleRow(string tableName, string[] columns, class Microsoft.Crm.Data.PropertyBag conditions, [opt] int32 sourceLineNumber, [opt] string memberName, [opt] string sourceFilePath)
0xb6ee  stloc.s  5
0xb6f0  ldloc.s  5
0xb6f2  brfalse.s loc_B745
0xb6f4  ldloc.s  5
0xb6f6  ldarg.3
0xb6f7  callvirt instance bool Microsoft.Crm.Data.PropertyBag::Contains(string propertyName)
0xb6fc  brfalse.s loc_B745
0xb6fe  ldloc.s  5
0xb700  ldarg.3
0xb701  callvirt instance object Microsoft.Crm.Data.PropertyBag::get_Item(string propertyName)
0xb706  stloc.s  6
0xb708  ldloc.s  6
0xb70a  brfalse.s loc_B745
0xb70c  ldloc.s  6
0xb70e  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0xb713  beq.s    loc_B745
0xb715  ldarg.3
0xb716  ldstr    aStagingdbconne// "StagingDbConnectionString"
0xb71b  call     bool [mscorlib]System.String::op_Equality(string, string)
0xb720  brfalse.s loc_B737
0xb722  ldloc.s  5
0xb724  ldarg.3
0xb725  callvirt instance object Microsoft.Crm.Data.PropertyBag::get_Item(string propertyName)
0xb72a  castclass [mscorlib]System.Security.SecureString
0xb72f  call     string Microsoft.Crm.CrmKeyService::GetStringFromSecureString(class [mscorlib]System.Security.SecureString secureString)
0xb734  stloc.0
0xb735  br.s     loc_B745
0xb737  ldloc.s  5
0xb739  ldarg.3
0xb73a  callvirt instance object Microsoft.Crm.Data.PropertyBag::get_Item(string propertyName)
0xb73f  callvirt instance string [mscorlib]System.Object::ToString()
0xb744  stloc.0
0xb745  ldloc.0
0xb746  ret
```
