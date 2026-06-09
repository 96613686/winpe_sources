# Microsoft.Crm.ConfigurationDatabase.StaticEncryptionConfigurationCache::LoadEncryptionConfiguration

- ea: `0x49e70`
- end: `0x49f09`
- name: `Microsoft.Crm.ConfigurationDatabase.StaticEncryptionConfigurationCache::LoadEncryptionConfiguration`
- size: `153`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x49e60`

## callees

- `0x44400`
- `0x444f0`
- `0x44510`
- `0x49e70`
- `0x4d750`
- `0x5f6f0`
- `0x61420`

## string_xrefs

- `0x49e7d`: `IsConfigurationRow`
- `0x49eb4`: `LoadEncryptionConfiguration`
- `0x49eb9`: `D:\a\1\s\src\Platform\Core\DataServices\Configuration\Cache\EncryptionConfigurationCache.cs`

## pseudocode

```c

```

## disassembly

```asm
0x49e70  newobj   instance void Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::.ctor()
0x49e75  stloc.1
0x49e76  newobj   instance void Microsoft.Crm.Data.PropertyBag::.ctor()
0x49e7b  stloc.2
0x49e7c  ldloc.2
0x49e7d  ldstr    aIsconfiguratio// "IsConfigurationRow"
0x49e82  ldc.i4.1
0x49e83  box      [mscorlib]System.Boolean
0x49e88  callvirt instance void Microsoft.Crm.Data.PropertyBag::set_Item(string propertyName, object value)
0x49e8d  ldloc.1
0x49e8e  ldstr    aDataencryption// "DataEncryptionKey"
0x49e93  ldc.i4.3
0x49e94  newarr   [mscorlib]System.String
0x49e99  dup
0x49e9a  ldc.i4.0
0x49e9b  ldstr    aMastercertific// "MasterCertificate"
0x49ea0  stelem.ref
0x49ea1  dup
0x49ea2  ldc.i4.1
0x49ea3  ldstr    aEnabled// "Enabled"
0x49ea8  stelem.ref
0x49ea9  dup
0x49eaa  ldc.i4.2
0x49eab  ldstr    aId// "Id"
0x49eb0  stelem.ref
0x49eb1  ldloc.2
0x49eb2  ldc.i4.s 0x77
0x49eb4  ldstr    aLoadencryption// "LoadEncryptionConfiguration"
0x49eb9  ldstr    aDA1SSrcPlatfor_32// "D:\\a\\1\\s\\src\\Platform\\Core\\DataS"...
0x49ebe  callvirt instance class Microsoft.Crm.Data.PropertyBag Microsoft.Crm.SharedDatabase.DatabaseService::RetrieveSingleItem(string tableName, string[] columns, class Microsoft.Crm.Data.PropertyBag conditions, [opt] int32 sourceLineNumber, [opt] string memberName, [opt] string sourceFilePath)
0x49ec3  stloc.3
0x49ec4  ldloc.3
0x49ec5  brtrue.s loc_49ED5
0x49ec7  ldsfld   string [mscorlib]System.String::Empty
0x49ecc  ldc.i4.0
0x49ecd  newobj   instance void Microsoft.Crm.SharedDatabase.EncryptionConfiguration::.ctor(string encryptionCertificate, bool enabled)
0x49ed2  stloc.0
0x49ed3  leave.s  loc_49F07
0x49ed5  ldloc.3
0x49ed6  ldstr    aMastercertific// "MasterCertificate"
0x49edb  callvirt instance object Microsoft.Crm.Data.PropertyBag::get_Item(string propertyName)
0x49ee0  castclass [mscorlib]System.String
0x49ee5  ldloc.3
0x49ee6  ldstr    aEnabled// "Enabled"
0x49eeb  callvirt instance object Microsoft.Crm.Data.PropertyBag::get_Item(string propertyName)
0x49ef0  unbox.any [mscorlib]System.Boolean
0x49ef5  newobj   instance void Microsoft.Crm.SharedDatabase.EncryptionConfiguration::.ctor(string encryptionCertificate, bool enabled)
0x49efa  stloc.0
0x49efb  leave.s  loc_49F07
0x49efd  ldloc.1
0x49efe  brfalse.s loc_49F06
0x49f00  ldloc.1
0x49f01  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x49f06  endfinally
0x49f07  ldloc.0
0x49f08  ret
```
