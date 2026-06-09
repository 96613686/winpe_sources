# Microsoft.Crm.ConfigurationDatabase.ClientPatchDetailsService::Update

- ea: `0x4bca0`
- end: `0x4bd0e`
- name: `Microsoft.Crm.ConfigurationDatabase.ClientPatchDetailsService::Update`
- size: `110`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x1be90`
- `0x44400`
- `0x44510`
- `0x4b860`
- `0x4b970`
- `0x4c0e0`
- `0x624a0`

## string_xrefs

- `0x4bcfd`: `Update`
- `0x4bd02`: `D:\a\1\s\src\Platform\Core\DataServices\Configuration\ObjectModel\ClientPatchDetails.cs`

## pseudocode

```c

```

## disassembly

```asm
0x4bca0  ldarg.1
0x4bca1  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.ConfigurationDatabase.ClientPatch::get_PatchId()
0x4bca6  ldstr    aPatchid_0// "patchId"
0x4bcab  call     void Microsoft.Crm.Exceptions::ThrowIfGuidEmpty(valuetype [mscorlib]System.Guid parameter, string name)
0x4bcb0  ldarg.0
0x4bcb1  ldarg.1
0x4bcb2  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.ConfigurationDatabase.ClientPatch::get_PatchId()
0x4bcb7  ldstr    aPatchid_0// "patchId"
0x4bcbc  call     instance void Microsoft.Crm.ConfigurationDatabase.ClientPatchDetailsService::ThrowIfPatchDoesNotExist(valuetype [mscorlib]System.Guid patchId, string parameterName)
0x4bcc1  newobj   instance void Microsoft.Crm.Data.PropertyBag::.ctor()
0x4bcc6  stloc.0
0x4bcc7  ldloc.0
0x4bcc8  ldstr    aPatchid// "PatchId"
0x4bccd  ldarg.1
0x4bcce  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.ConfigurationDatabase.ClientPatch::get_PatchId()
0x4bcd3  box      [mscorlib]System.Guid
0x4bcd8  callvirt instance void Microsoft.Crm.Data.PropertyBag::set_Item(string propertyName, object value)
0x4bcdd  ldarg.0
0x4bcde  ldfld    class Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService Microsoft.Crm.ConfigurationDatabase.ClientPatchDetailsService::_configService
0x4bce3  ldstr    aClientpatchdet// "ClientPatchDetails"
0x4bce8  ldarg.1
0x4bce9  callvirt instance class Microsoft.Crm.Data.PropertyBag Microsoft.Crm.ConfigurationDatabase.ClientPatch::get_Properties()
0x4bcee  ldc.i4.1
0x4bcef  newarr   Microsoft.Crm.Data.PropertyBag
0x4bcf4  dup
0x4bcf5  ldc.i4.0
0x4bcf6  ldloc.0
0x4bcf7  stelem.ref
0x4bcf8  ldc.i4   0x137
0x4bcfd  ldstr    aUpdate// "Update"
0x4bd02  ldstr    aDA1SSrcPlatfor_35// "D:\\a\\1\\s\\src\\Platform\\Core\\DataS"...
0x4bd07  callvirt instance int32 Microsoft.Crm.SharedDatabase.DatabaseService::Update(string tableName, class Microsoft.Crm.Data.PropertyBag columnSet, class Microsoft.Crm.Data.PropertyBag[] conditions, [opt] int32 sourceLineNumber, [opt] string memberName, [opt] string sourceFilePath)
0x4bd0c  pop
0x4bd0d  ret
```
