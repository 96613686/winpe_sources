# Microsoft.Crm.ConfigurationDatabase.ClientPatchDetailsService::DeletePatchContainments

- ea: `0x4beb0`
- end: `0x4bf02`
- name: `Microsoft.Crm.ConfigurationDatabase.ClientPatchDetailsService::DeletePatchContainments`
- size: `82`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x1be90`
- `0x44400`
- `0x44510`
- `0x4beb0`
- `0x625b0`

## string_xrefs

- `0x4bef1`: `D:\a\1\s\src\Platform\Core\DataServices\Configuration\ObjectModel\ClientPatchDetails.cs`
- `0x4beec`: `DeletePatchContainments`

## pseudocode

```c

```

## disassembly

```asm
0x4beb0  ldarg.1
0x4beb1  ldstr    aPatchid_0// "patchId"
0x4beb6  call     void Microsoft.Crm.Exceptions::ThrowIfGuidEmpty(valuetype [mscorlib]System.Guid parameter, string name)
0x4bebb  newobj   instance void Microsoft.Crm.Data.PropertyBag::.ctor()
0x4bec0  stloc.0
0x4bec1  ldloc.0
0x4bec2  ldstr    aPatchid// "PatchId"
0x4bec7  ldarg.1
0x4bec8  box      [mscorlib]System.Guid
0x4becd  callvirt instance void Microsoft.Crm.Data.PropertyBag::set_Item(string propertyName, object value)
0x4bed2  ldarg.0
0x4bed3  ldfld    class Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService Microsoft.Crm.ConfigurationDatabase.ClientPatchDetailsService::_configService
0x4bed8  ldstr    aClientpatchcon// "ClientPatchContainedInfo"
0x4bedd  ldc.i4.1
0x4bede  newarr   Microsoft.Crm.Data.PropertyBag
0x4bee3  dup
0x4bee4  ldc.i4.0
0x4bee5  ldloc.0
0x4bee6  stelem.ref
0x4bee7  ldc.i4   0x17F
0x4beec  ldstr    aDeletepatchcon// "DeletePatchContainments"
0x4bef1  ldstr    aDA1SSrcPlatfor_35// "D:\\a\\1\\s\\src\\Platform\\Core\\DataS"...
0x4bef6  callvirt instance int32 Microsoft.Crm.SharedDatabase.DatabaseService::Delete(string tableName, class Microsoft.Crm.Data.PropertyBag[] conditions, [opt] int32 sourceLineNumber, [opt] string memberName, [opt] string sourceFilePath)
0x4befb  pop
0x4befc  leave.s  loc_4BF01
0x4befe  pop
0x4beff  leave.s  loc_4BF01
0x4bf01  ret
```
