# Microsoft.Crm.CrmKey::LoadExistingKey

- ea: `0x37760`
- end: `0x3789a`
- name: `Microsoft.Crm.CrmKey::LoadExistingKey`
- size: `314`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x37740`

## callees

- `0x3080`
- `0x4650`
- `0x4c00`
- `0x2d930`
- `0x37760`
- `0x3b920`
- `0x3b930`
- `0x3b940`
- `0x3b950`
- `0x444f0`
- `0x4d7b0`
- `0x613c0`

## string_xrefs

- `0x37798`: `CreatedOn`
- `0x377cc`: `D:\a\1\s\src\Platform\Core\Security\Cryptography\CrmKey.cs`
- `0x377fc`: `D:\a\1\s\src\Platform\Core\Security\Cryptography\CrmKey.cs`

## pseudocode

```c

```

## disassembly

```asm
0x37760  ldc.i4.8
0x37761  newarr   [mscorlib]System.String
0x37766  dup
0x37767  ldc.i4.0
0x37768  ldstr    aId// "Id"
0x3776d  stelem.ref
0x3776e  dup
0x3776f  ldc.i4.1
0x37770  ldstr    aScalegroupid_0// "ScaleGroupId"
0x37775  stelem.ref
0x37776  dup
0x37777  ldc.i4.2
0x37778  ldstr    aKeytype// "KeyType"
0x3777d  stelem.ref
0x3777e  dup
0x3777f  ldc.i4.3
0x37780  ldstr    aKeyvalue// "KeyValue"
0x37785  stelem.ref
0x37786  dup
0x37787  ldc.i4.4
0x37788  ldstr    aValidon// "ValidOn"
0x3778d  stelem.ref
0x3778e  dup
0x3778f  ldc.i4.5
0x37790  ldstr    aExpireson// "ExpiresOn"
0x37795  stelem.ref
0x37796  dup
0x37797  ldc.i4.6
0x37798  ldstr    aCreatedon// "CreatedOn"
0x3779d  stelem.ref
0x3779e  dup
0x3779f  ldc.i4.7
0x377a0  ldstr    aEnabled// "Enabled"
0x377a5  stelem.ref
0x377a6  stloc.0
0x377a7  ldarg.0
0x377a8  call     instance bool Microsoft.Crm.BaseAuditableConfigurationEntity::get_UseCachedValues()
0x377ad  brfalse.s loc_377DD
0x377af  ldarg.0
0x377b0  ldarg.2
0x377b1  call     class Microsoft.Crm.LocatorService Microsoft.Crm.LocatorService::GetContextInstance(valuetype Microsoft.Crm.LocatorServiceContext locatorServiceContext)
0x377b6  ldstr    aCrmkey// "CrmKey"
0x377bb  ldarg.1
0x377bc  box      [mscorlib]System.Guid
0x377c1  ldloc.0
0x377c2  ldc.i4   0x18D
0x377c7  ldstr    aLoadexistingke// "LoadExistingKey"
0x377cc  ldstr    aDA1SSrcPlatfor_16// "D:\\a\\1\\s\\src\\Platform\\Core\\Secur"...
0x377d1  callvirt instance class Microsoft.Crm.Data.PropertyBag Microsoft.Crm.LocatorService::RetrieveById(string tableName, object primaryKey, string[] columns, [opt] int32 sourceLineNumber, [opt] string memberName, [opt] string sourceFilePath)
0x377d6  call     instance void Microsoft.Crm.BaseAuditableConfigurationEntity::set_SettingsBag(class Microsoft.Crm.Data.PropertyBag value)
0x377db  br.s     loc_37817
0x377dd  ldarg.2
0x377de  newobj   instance void Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::.ctor(valuetype Microsoft.Crm.LocatorServiceContext locatorServiceContext)
0x377e3  stloc.1
0x377e4  ldarg.0
0x377e5  ldloc.1
0x377e6  ldstr    aCrmkey// "CrmKey"
0x377eb  ldarg.1
0x377ec  box      [mscorlib]System.Guid
0x377f1  ldloc.0
0x377f2  ldc.i4   0x193
0x377f7  ldstr    aLoadexistingke// "LoadExistingKey"
0x377fc  ldstr    aDA1SSrcPlatfor_16// "D:\\a\\1\\s\\src\\Platform\\Core\\Secur"...
0x37801  callvirt instance class Microsoft.Crm.Data.PropertyBag Microsoft.Crm.SharedDatabase.DatabaseService::RetrieveById(string tableName, object id, string[] columns, [opt] int32 sourceLineNumber, [opt] string memberName, [opt] string sourceFilePath)
0x37806  call     instance void Microsoft.Crm.BaseAuditableConfigurationEntity::set_SettingsBag(class Microsoft.Crm.Data.PropertyBag value)
0x3780b  leave.s  loc_37817
0x3780d  ldloc.1
0x3780e  brfalse.s loc_37816
0x37810  ldloc.1
0x37811  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x37816  endfinally
0x37817  ldarg.0
0x37818  call     instance class Microsoft.Crm.Data.PropertyBag Microsoft.Crm.BaseAuditableConfigurationEntity::get_SettingsBag()
0x3781d  brtrue.s loc_37836
0x3781f  ldarg.0
0x37820  call     instance string Microsoft.Crm.BaseAuditableConfigurationEntity::get_TableName()
0x37825  ldstr    aId// "Id"
0x3782a  ldarg.1
0x3782b  box      [mscorlib]System.Guid
0x37830  newobj   instance void Microsoft.Crm.CrmConfigObjectNotFoundException::.ctor(string tableName, string columnName, object id)
0x37835  throw
0x37836  ldarg.0
0x37837  ldtoken  Microsoft.Crm.CrmKeyType
0x3783c  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x37841  ldarg.0
0x37842  call     instance class Microsoft.Crm.Data.PropertyBag Microsoft.Crm.BaseAuditableConfigurationEntity::get_SettingsBag()
0x37847  ldstr    aKeytype// "KeyType"
0x3784c  callvirt instance object Microsoft.Crm.Data.PropertyBag::get_Item(string propertyName)
0x37851  castclass [mscorlib]System.String
0x37856  call     object Microsoft.Crm.CrmEnumUtility::ParseSingleValue(class [mscorlib]System.Type enumType, string value)
0x3785b  unbox.any Microsoft.Crm.CrmKeyType
0x37860  stfld    valuetype Microsoft.Crm.CrmKeyType Microsoft.Crm.CrmKey::_keyType
0x37865  ldarg.0
0x37866  ldarg.0
0x37867  call     instance class Microsoft.Crm.Data.PropertyBag Microsoft.Crm.BaseAuditableConfigurationEntity::get_SettingsBag()
0x3786c  ldstr    aKeyvalue// "KeyValue"
0x37871  callvirt instance object Microsoft.Crm.Data.PropertyBag::get_Item(string propertyName)
0x37876  castclass [mscorlib]System.Security.SecureString
0x3787b  stfld    class [mscorlib]System.Security.SecureString Microsoft.Crm.CrmKey::_keyValue
0x37880  ldarg.0
0x37881  ldfld    class [mscorlib]System.Security.SecureString Microsoft.Crm.CrmKey::_keyValue
0x37886  brfalse.s loc_37899
0x37888  ldarg.0
0x37889  ldarg.0
0x3788a  ldfld    class [mscorlib]System.Security.SecureString Microsoft.Crm.CrmKey::_keyValue
0x3788f  callvirt instance class [mscorlib]System.Security.SecureString [mscorlib]System.Security.SecureString::Copy()
0x37894  stfld    class [mscorlib]System.Security.SecureString Microsoft.Crm.CrmKey::_keyValue
0x37899  ret
```
