# Microsoft.Crm.CrmKeySetting::LoadSettingsBag

- ea: `0x39ec0`
- end: `0x39fdd`
- name: `Microsoft.Crm.CrmKeySetting::LoadSettingsBag`
- size: `285`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x39b30`

## callees

- `0x3090`
- `0x4650`
- `0x4c00`
- `0x39710`
- `0x39850`
- `0x39ec0`
- `0x3b950`
- `0x44840`
- `0x4d7b0`
- `0x64ae0`

## string_xrefs

- `0x39f15`: `CreatedOn`
- `0x39f64`: `D:\a\1\s\src\Platform\Core\Security\Cryptography\CrmKeySetting.cs`
- `0x39f8f`: `D:\a\1\s\src\Platform\Core\Security\Cryptography\CrmKeySetting.cs`
- `0x39f1e`: `CreatedBy`

## pseudocode

```c

```

## disassembly

```asm
0x39ec0  ldarg.0
0x39ec1  call     instance valuetype Microsoft.Crm.CrmKeyType Microsoft.Crm.CrmKeySetting::get_KeyType()
0x39ec6  call     valuetype [mscorlib]System.Guid Microsoft.Crm.CrmKeySetting::GetKeySettingGuid(valuetype Microsoft.Crm.CrmKeyType keyType)
0x39ecb  stloc.0
0x39ecc  ldc.i4.s 0xD
0x39ece  newarr   [mscorlib]System.String
0x39ed3  dup
0x39ed4  ldc.i4.0
0x39ed5  ldstr    aId// "Id"
0x39eda  stelem.ref
0x39edb  dup
0x39edc  ldc.i4.1
0x39edd  ldstr    aKeytype// "KeyType"
0x39ee2  stelem.ref
0x39ee3  dup
0x39ee4  ldc.i4.2
0x39ee5  ldstr    aKeylength// "KeyLength"
0x39eea  stelem.ref
0x39eeb  dup
0x39eec  ldc.i4.3
0x39eed  ldstr    aActivekeyid_1// "ActiveKeyId"
0x39ef2  stelem.ref
0x39ef3  dup
0x39ef4  ldc.i4.4
0x39ef5  ldstr    aArchivelength// "ArchiveLength"
0x39efa  stelem.ref
0x39efb  dup
0x39efc  ldc.i4.5
0x39efd  ldstr    aAlgorithm// "Algorithm"
0x39f02  stelem.ref
0x39f03  dup
0x39f04  ldc.i4.6
0x39f05  ldstr    aKeygenerationi_0// "KeyGenerationInterval"
0x39f0a  stelem.ref
0x39f0b  dup
0x39f0c  ldc.i4.7
0x39f0d  ldstr    aCryptotimetoli// "CryptoTimeToLive"
0x39f12  stelem.ref
0x39f13  dup
0x39f14  ldc.i4.8
0x39f15  ldstr    aCreatedon// "CreatedOn"
0x39f1a  stelem.ref
0x39f1b  dup
0x39f1c  ldc.i4.s 9
0x39f1e  ldstr    aCreatedby// "CreatedBy"
0x39f23  stelem.ref
0x39f24  dup
0x39f25  ldc.i4.s 0xA
0x39f27  ldstr    aModifiedon// "ModifiedOn"
0x39f2c  stelem.ref
0x39f2d  dup
0x39f2e  ldc.i4.s 0xB
0x39f30  ldstr    aModifiedby// "ModifiedBy"
0x39f35  stelem.ref
0x39f36  dup
0x39f37  ldc.i4.s 0xC
0x39f39  ldstr    aEnabled// "Enabled"
0x39f3e  stelem.ref
0x39f3f  stloc.1
0x39f40  ldarg.0
0x39f41  call     instance bool Microsoft.Crm.BaseAuditableConfigurationEntity::get_UseCachedValues()
0x39f46  brfalse.s loc_39F71
0x39f48  ldarg.1
0x39f49  call     class Microsoft.Crm.LocatorService Microsoft.Crm.LocatorService::GetContextInstance(valuetype Microsoft.Crm.LocatorServiceContext locatorServiceContext)
0x39f4e  ldstr    aCrmkeysetting// "CrmKeySetting"
0x39f53  ldloc.0
0x39f54  box      [mscorlib]System.Guid
0x39f59  ldloc.1
0x39f5a  ldc.i4   0x274
0x39f5f  ldstr    aLoadsettingsba// "LoadSettingsBag"
0x39f64  ldstr    aDA1SSrcPlatfor_20// "D:\\a\\1\\s\\src\\Platform\\Core\\Secur"...
0x39f69  callvirt instance class Microsoft.Crm.Data.PropertyBag Microsoft.Crm.LocatorService::RetrieveById(string tableName, object primaryKey, string[] columns, [opt] int32 sourceLineNumber, [opt] string memberName, [opt] string sourceFilePath)
0x39f6e  stloc.2
0x39f6f  br.s     loc_39FAF
0x39f71  ldarg.1
0x39f72  newobj   instance void Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::.ctor(valuetype Microsoft.Crm.LocatorServiceContext locatorServiceContext)
0x39f77  stloc.3
0x39f78  ldloc.3
0x39f79  ldstr    aCrmkeysetting// "CrmKeySetting"
0x39f7e  ldloc.0
0x39f7f  box      [mscorlib]System.Guid
0x39f84  ldloc.1
0x39f85  ldc.i4   0x27A
0x39f8a  ldstr    aLoadsettingsba// "LoadSettingsBag"
0x39f8f  ldstr    aDA1SSrcPlatfor_20// "D:\\a\\1\\s\\src\\Platform\\Core\\Secur"...
0x39f94  callvirt instance class Microsoft.Crm.Data.PropertyBag Microsoft.Crm.SharedDatabase.IDatabaseService::RetrieveById(string tableName, object id, string[] columns, [opt] int32 sourceLineNumber, [opt] string memberName, [opt] string sourceFilePath)
0x39f99  stloc.2
0x39f9a  ldloc.2
0x39f9b  brfalse.s loc_39FA3
0x39f9d  ldloc.2
0x39f9e  callvirt instance void Microsoft.Crm.Data.PropertyBag::ResetStates()
0x39fa3  leave.s  loc_39FAF
0x39fa5  ldloc.3
0x39fa6  brfalse.s loc_39FAE
0x39fa8  ldloc.3
0x39fa9  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x39fae  endfinally
0x39faf  ldloc.2
0x39fb0  brtrue.s loc_39FDB
0x39fb2  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x39fb7  ldstr    aNoKeySettingsE// "No key settings exists for key type : {"...
0x39fbc  ldc.i4.1
0x39fbd  newarr   [mscorlib]System.Object
0x39fc2  dup
0x39fc3  ldc.i4.0
0x39fc4  ldarg.0
0x39fc5  call     instance valuetype Microsoft.Crm.CrmKeyType Microsoft.Crm.CrmKeySetting::get_KeyType()
0x39fca  box      Microsoft.Crm.CrmKeyType
0x39fcf  stelem.ref
0x39fd0  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x39fd5  newobj   instance void Microsoft.Crm.CrmConfigObjectNotFoundException::.ctor(string message)
0x39fda  throw
0x39fdb  ldloc.2
0x39fdc  ret
```
