# CrmConfigScopeKeySetting::LoadSettingsBag

- ea: `0x69290`
- end: `0x69378`
- name: `CrmConfigScopeKeySetting::LoadSettingsBag`
- size: `232`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callers

- `0x69250`

## callees

- `0x4650`
- `0x4c60`
- `0x3b950`
- `0x44400`
- `0x44510`
- `0x44840`
- `0x4d7b0`
- `0x64af0`
- `0x69200`
- `0x69290`
- `0x69380`

## string_xrefs

- `0x692f3`: `IsConfigurationRow`
- `0x69322`: `D:\a\1\s\src\Platform\Core\Security\Cryptography\CrmKeySetting.cs`
- `0x6934a`: `D:\a\1\s\src\Platform\Core\Security\Cryptography\CrmKeySetting.cs`

## pseudocode

```c

```

## disassembly

```asm
0x69290  ldc.i4.4
0x69291  newarr   [mscorlib]System.String
0x69296  dup
0x69297  ldc.i4.0
0x69298  ldstr    aId// "Id"
0x6929d  stelem.ref
0x6929e  dup
0x6929f  ldc.i4.1
0x692a0  ldstr    aKeytype// "KeyType"
0x692a5  stelem.ref
0x692a6  dup
0x692a7  ldc.i4.2
0x692a8  ldstr    aScalegroupid_0// "ScaleGroupId"
0x692ad  stelem.ref
0x692ae  dup
0x692af  ldc.i4.3
0x692b0  ldstr    aActivekeyid_1// "ActiveKeyId"
0x692b5  stelem.ref
0x692b6  stloc.0
0x692b7  newobj   instance void Microsoft.Crm.Data.PropertyBag::.ctor()
0x692bc  stloc.1
0x692bd  ldloc.1
0x692be  ldstr    aScalegroupid_0// "ScaleGroupId"
0x692c3  ldarg.0
0x692c4  ldfld    valuetype [mscorlib]System.Guid CrmConfigScopeKeySetting::_scaleGroupId
0x692c9  box      [mscorlib]System.Guid
0x692ce  callvirt instance void Microsoft.Crm.Data.PropertyBag::set_Item(string propertyName, object value)
0x692d3  ldloc.1
0x692d4  ldstr    aKeytype// "KeyType"
0x692d9  ldarg.0
0x692da  call     instance valuetype Microsoft.Crm.CrmKeyType CrmConfigScopeKeySetting::get_KeyType()
0x692df  stloc.3
0x692e0  ldloca.s 3
0x692e2  constrained. Microsoft.Crm.CrmKeyType
0x692e8  callvirt instance string [mscorlib]System.Object::ToString()
0x692ed  callvirt instance void Microsoft.Crm.Data.PropertyBag::set_Item(string propertyName, object value)
0x692f2  ldloc.1
0x692f3  ldstr    aIsconfiguratio// "IsConfigurationRow"
0x692f8  ldc.i4.0
0x692f9  box      [mscorlib]System.Boolean
0x692fe  callvirt instance void Microsoft.Crm.Data.PropertyBag::set_Item(string propertyName, object value)
0x69303  ldarg.0
0x69304  call     instance bool Microsoft.Crm.BaseAuditableConfigurationEntity::get_UseCachedValues()
0x69309  brfalse.s loc_6932F
0x6930b  ldarg.1
0x6930c  call     class Microsoft.Crm.LocatorService Microsoft.Crm.LocatorService::GetContextInstance(valuetype Microsoft.Crm.LocatorServiceContext locatorServiceContext)
0x69311  ldstr    aCrmkeysetting// "CrmKeySetting"
0x69316  ldloc.0
0x69317  ldloc.1
0x69318  ldc.i4   0x3AD
0x6931d  ldstr    aLoadsettingsba// "LoadSettingsBag"
0x69322  ldstr    aDA1SSrcPlatfor_20// "D:\\a\\1\\s\\src\\Platform\\Core\\Secur"...
0x69327  callvirt instance class Microsoft.Crm.Data.PropertyBag Microsoft.Crm.LocatorService::RetrieveSingleRow(string tableName, string[] columns, class Microsoft.Crm.Data.PropertyBag conditions, [opt] int32 sourceLineNumber, [opt] string memberName, [opt] string sourceFilePath)
0x6932c  stloc.2
0x6932d  br.s     loc_6936C
0x6932f  ldarg.1
0x69330  newobj   instance void Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::.ctor(valuetype Microsoft.Crm.LocatorServiceContext locatorServiceContext)
0x69335  stloc.s  4
0x69337  ldloc.s  4
0x69339  ldstr    aCrmkeysetting// "CrmKeySetting"
0x6933e  ldloc.0
0x6933f  ldloc.1
0x69340  ldc.i4   0x3B4
0x69345  ldstr    aLoadsettingsba// "LoadSettingsBag"
0x6934a  ldstr    aDA1SSrcPlatfor_20// "D:\\a\\1\\s\\src\\Platform\\Core\\Secur"...
0x6934f  callvirt instance class Microsoft.Crm.Data.PropertyBag Microsoft.Crm.SharedDatabase.IDatabaseService::RetrieveSingleItem(string tableName, string[] columns, class Microsoft.Crm.Data.PropertyBag conditions, [opt] int32 sourceLineNumber, [opt] string memberName, [opt] string sourceFilePath)
0x69354  stloc.2
0x69355  ldloc.2
0x69356  brfalse.s loc_6935E
0x69358  ldloc.2
0x69359  callvirt instance void Microsoft.Crm.Data.PropertyBag::ResetStates()
0x6935e  leave.s  loc_6936C
0x69360  ldloc.s  4
0x69362  brfalse.s loc_6936B
0x69364  ldloc.s  4
0x69366  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x6936b  endfinally
0x6936c  ldloc.2
0x6936d  brtrue.s loc_69376
0x6936f  ldarg.0
0x69370  call     instance class Microsoft.Crm.Data.PropertyBag CrmConfigScopeKeySetting::CreateDefaultSettingsBag()
0x69375  stloc.2
0x69376  ldloc.2
0x69377  ret
```
