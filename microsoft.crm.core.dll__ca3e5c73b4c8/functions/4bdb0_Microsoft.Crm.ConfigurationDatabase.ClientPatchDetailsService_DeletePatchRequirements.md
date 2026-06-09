# Microsoft.Crm.ConfigurationDatabase.ClientPatchDetailsService::DeletePatchRequirements

- ea: `0x4bdb0`
- end: `0x4be02`
- name: `Microsoft.Crm.ConfigurationDatabase.ClientPatchDetailsService::DeletePatchRequirements`
- size: `82`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x1be90`
- `0x44400`
- `0x44510`
- `0x4bdb0`
- `0x625b0`

## string_xrefs

- `0x4bdf1`: `D:\a\1\s\src\Platform\Core\DataServices\Configuration\ObjectModel\ClientPatchDetails.cs`
- `0x4bdec`: `DeletePatchRequirements`

## pseudocode

```c

```

## disassembly

```asm
0x4bdb0  ldarg.1
0x4bdb1  ldstr    aPatchid_0// "patchId"
0x4bdb6  call     void Microsoft.Crm.Exceptions::ThrowIfGuidEmpty(valuetype [mscorlib]System.Guid parameter, string name)
0x4bdbb  newobj   instance void Microsoft.Crm.Data.PropertyBag::.ctor()
0x4bdc0  stloc.0
0x4bdc1  ldloc.0
0x4bdc2  ldstr    aPatchid// "PatchId"
0x4bdc7  ldarg.1
0x4bdc8  box      [mscorlib]System.Guid
0x4bdcd  callvirt instance void Microsoft.Crm.Data.PropertyBag::set_Item(string propertyName, object value)
0x4bdd2  ldarg.0
0x4bdd3  ldfld    class Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService Microsoft.Crm.ConfigurationDatabase.ClientPatchDetailsService::_configService
0x4bdd8  ldstr    aClientpatchreq// "ClientPatchRequiredInfo"
0x4bddd  ldc.i4.1
0x4bdde  newarr   Microsoft.Crm.Data.PropertyBag
0x4bde3  dup
0x4bde4  ldc.i4.0
0x4bde5  ldloc.0
0x4bde6  stelem.ref
0x4bde7  ldc.i4   0x159
0x4bdec  ldstr    aDeletepatchreq// "DeletePatchRequirements"
0x4bdf1  ldstr    aDA1SSrcPlatfor_35// "D:\\a\\1\\s\\src\\Platform\\Core\\DataS"...
0x4bdf6  callvirt instance int32 Microsoft.Crm.SharedDatabase.DatabaseService::Delete(string tableName, class Microsoft.Crm.Data.PropertyBag[] conditions, [opt] int32 sourceLineNumber, [opt] string memberName, [opt] string sourceFilePath)
0x4bdfb  pop
0x4bdfc  leave.s  loc_4BE01
0x4bdfe  pop
0x4bdff  leave.s  loc_4BE01
0x4be01  ret
```
