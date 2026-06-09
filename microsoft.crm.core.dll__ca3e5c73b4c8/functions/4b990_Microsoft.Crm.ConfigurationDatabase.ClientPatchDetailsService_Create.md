# Microsoft.Crm.ConfigurationDatabase.ClientPatchDetailsService::Create

- ea: `0x4b990`
- end: `0x4b9f1`
- name: `Microsoft.Crm.ConfigurationDatabase.ClientPatchDetailsService::Create`
- size: `97`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x1be90`
- `0x2dae0`
- `0x44510`
- `0x4b860`
- `0x4b970`
- `0x4c110`
- `0x61910`

## string_xrefs

- `0x4b9dc`: `Create`
- `0x4b9e1`: `D:\a\1\s\src\Platform\Core\DataServices\Configuration\ObjectModel\ClientPatchDetails.cs`

## pseudocode

```c

```

## disassembly

```asm
0x4b990  ldarg.1
0x4b991  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.ConfigurationDatabase.ClientPatch::get_PatchId()
0x4b996  ldstr    aPatchid_0// "patchId"
0x4b99b  call     void Microsoft.Crm.Exceptions::ThrowIfGuidEmpty(valuetype [mscorlib]System.Guid parameter, string name)
0x4b9a0  ldarg.0
0x4b9a1  ldarg.1
0x4b9a2  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.ConfigurationDatabase.ClientPatch::get_PatchId()
0x4b9a7  call     instance void Microsoft.Crm.ConfigurationDatabase.ClientPatchDetailsService::ThrowIfPatchExists(valuetype [mscorlib]System.Guid patchId)
0x4b9ac  ldarg.1
0x4b9ad  callvirt instance class Microsoft.Crm.Data.PropertyBag Microsoft.Crm.ConfigurationDatabase.ClientPatch::get_Properties()
0x4b9b2  ldstr    aId// "Id"
0x4b9b7  call     valuetype [mscorlib]System.Guid Microsoft.Crm.SequentialGuid::CreateGuid()
0x4b9bc  box      [mscorlib]System.Guid
0x4b9c1  callvirt instance void Microsoft.Crm.Data.PropertyBag::set_Item(string propertyName, object value)
0x4b9c6  ldarg.0
0x4b9c7  ldfld    class Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService Microsoft.Crm.ConfigurationDatabase.ClientPatchDetailsService::_configService
0x4b9cc  ldstr    aClientpatchdet// "ClientPatchDetails"
0x4b9d1  ldarg.1
0x4b9d2  callvirt instance class Microsoft.Crm.Data.PropertyBag Microsoft.Crm.ConfigurationDatabase.ClientPatch::get_Properties()
0x4b9d7  ldc.i4   0xDE
0x4b9dc  ldstr    aCreate// "Create"
0x4b9e1  ldstr    aDA1SSrcPlatfor_35// "D:\\a\\1\\s\\src\\Platform\\Core\\DataS"...
0x4b9e6  callvirt instance object Microsoft.Crm.SharedDatabase.DatabaseService::Create(string tableName, class Microsoft.Crm.Data.PropertyBag columnSet, [opt] int32 sourceLineNumber, [opt] string memberName, [opt] string sourceFilePath)
0x4b9eb  unbox.any [mscorlib]System.Guid
0x4b9f0  ret
```
