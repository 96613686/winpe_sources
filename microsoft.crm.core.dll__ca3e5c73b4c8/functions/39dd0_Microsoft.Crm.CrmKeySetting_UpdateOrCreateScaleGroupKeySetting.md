# Microsoft.Crm.CrmKeySetting::UpdateOrCreateScaleGroupKeySetting

- ea: `0x39dd0`
- end: `0x39e98`
- name: `Microsoft.Crm.CrmKeySetting::UpdateOrCreateScaleGroupKeySetting`
- size: `200`
- prototype: ``
- caller_count: `2`
- callee_count: `11`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x39cb0`
- `0x39d50`

## callees

- `0x4640`
- `0x4c60`
- `0x38c10`
- `0x38c30`
- `0x38c70`
- `0x39850`
- `0x39dd0`
- `0x44400`
- `0x44510`
- `0x4d300`
- `0x69210`

## string_xrefs

- `0x39e31`: `IsConfigurationRow`
- `0x39e5e`: `UpdateOrCreateScaleGroupKeySetting`
- `0x39e63`: `D:\a\1\s\src\Platform\Core\Security\Cryptography\CrmKeySetting.cs`

## pseudocode

```c

```

## disassembly

```asm
0x39dd0  newobj   instance void Microsoft.Crm.CrmKeyService::.ctor()
0x39dd5  stloc.0
0x39dd6  ldarg.0
0x39dd7  ldfld    class CrmConfigScopeKeySetting Microsoft.Crm.CrmKeySetting::_configScopeKeySetting
0x39ddc  brfalse  loc_39E97
0x39de1  ldc.i4.1
0x39de2  newarr   [mscorlib]System.String
0x39de7  dup
0x39de8  ldc.i4.0
0x39de9  ldstr    aId// "Id"
0x39dee  stelem.ref
0x39def  stloc.1
0x39df0  newobj   instance void Microsoft.Crm.Data.PropertyBag::.ctor()
0x39df5  stloc.2
0x39df6  ldloc.2
0x39df7  ldstr    aScalegroupid_0// "ScaleGroupId"
0x39dfc  ldarg.0
0x39dfd  ldfld    class CrmConfigScopeKeySetting Microsoft.Crm.CrmKeySetting::_configScopeKeySetting
0x39e02  callvirt instance valuetype [mscorlib]System.Guid CrmConfigScopeKeySetting::get_ScaleGroupId()
0x39e07  box      [mscorlib]System.Guid
0x39e0c  callvirt instance void Microsoft.Crm.Data.PropertyBag::set_Item(string propertyName, object value)
0x39e11  ldloc.2
0x39e12  ldstr    aKeytype// "KeyType"
0x39e17  ldarg.0
0x39e18  call     instance valuetype Microsoft.Crm.CrmKeyType Microsoft.Crm.CrmKeySetting::get_KeyType()
0x39e1d  stloc.3
0x39e1e  ldloca.s 3
0x39e20  constrained. Microsoft.Crm.CrmKeyType
0x39e26  callvirt instance string [mscorlib]System.Object::ToString()
0x39e2b  callvirt instance void Microsoft.Crm.Data.PropertyBag::set_Item(string propertyName, object value)
0x39e30  ldloc.2
0x39e31  ldstr    aIsconfiguratio// "IsConfigurationRow"
0x39e36  ldc.i4.0
0x39e37  box      [mscorlib]System.Boolean
0x39e3c  callvirt instance void Microsoft.Crm.Data.PropertyBag::set_Item(string propertyName, object value)
0x39e41  ldstr    aCrmkeysetting// "CrmKeySetting"
0x39e46  newobj   instance void Microsoft.Crm.ConfigurationDatabase.ConfigDBLock::.ctor(string lockName)
0x39e4b  stloc.s  4
0x39e4d  call     class Microsoft.Crm.LocatorService Microsoft.Crm.LocatorService::get_Instance()
0x39e52  ldstr    aCrmkeysetting// "CrmKeySetting"
0x39e57  ldloc.1
0x39e58  ldloc.2
0x39e59  ldc.i4   0x238
0x39e5e  ldstr    aUpdateorcreate// "UpdateOrCreateScaleGroupKeySetting"
0x39e63  ldstr    aDA1SSrcPlatfor_20// "D:\\a\\1\\s\\src\\Platform\\Core\\Secur"...
0x39e68  callvirt instance class Microsoft.Crm.Data.PropertyBag Microsoft.Crm.LocatorService::RetrieveSingleRow(string tableName, string[] columns, class Microsoft.Crm.Data.PropertyBag conditions, [opt] int32 sourceLineNumber, [opt] string memberName, [opt] string sourceFilePath)
0x39e6d  brtrue.s loc_39E7D
0x39e6f  ldloc.0
0x39e70  ldarg.0
0x39e71  ldfld    class CrmConfigScopeKeySetting Microsoft.Crm.CrmKeySetting::_configScopeKeySetting
0x39e76  callvirt instance void Microsoft.Crm.CrmKeyService::Create(class Microsoft.Crm.IAuditableConfigurationEntity entity)
0x39e7b  leave.s  loc_39E97
0x39e7d  ldloc.0
0x39e7e  ldarg.0
0x39e7f  ldfld    class CrmConfigScopeKeySetting Microsoft.Crm.CrmKeySetting::_configScopeKeySetting
0x39e84  callvirt instance void Microsoft.Crm.CrmKeyService::Update(class Microsoft.Crm.IAuditableConfigurationEntity entity)
0x39e89  leave.s  loc_39E97
0x39e8b  ldloc.s  4
0x39e8d  brfalse.s loc_39E96
0x39e8f  ldloc.s  4
0x39e91  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x39e96  endfinally
0x39e97  ret
```
