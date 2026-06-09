# Microsoft.Crm.ConfigurationDatabase.ClientPatchDetailsService::CreatePatchRequirement

- ea: `0x4bd10`
- end: `0x4bda5`
- name: `Microsoft.Crm.ConfigurationDatabase.ClientPatchDetailsService::CreatePatchRequirement`
- size: `149`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x1be90`
- `0x2dae0`
- `0x44400`
- `0x44510`
- `0x4c0e0`
- `0x4c140`
- `0x61910`

## string_xrefs

- `0x4bd99`: `D:\a\1\s\src\Platform\Core\DataServices\Configuration\ObjectModel\ClientPatchDetails.cs`
- `0x4bd94`: `CreatePatchRequirement`

## pseudocode

```c

```

## disassembly

```asm
0x4bd10  ldarg.1
0x4bd11  ldstr    aPatchid_0// "patchId"
0x4bd16  call     void Microsoft.Crm.Exceptions::ThrowIfGuidEmpty(valuetype [mscorlib]System.Guid parameter, string name)
0x4bd1b  ldarg.2
0x4bd1c  ldstr    aRequiredpatchi_0// "requiredPatchId"
0x4bd21  call     void Microsoft.Crm.Exceptions::ThrowIfGuidEmpty(valuetype [mscorlib]System.Guid parameter, string name)
0x4bd26  ldarg.0
0x4bd27  ldarg.1
0x4bd28  ldstr    aPatchid_0// "patchId"
0x4bd2d  call     instance void Microsoft.Crm.ConfigurationDatabase.ClientPatchDetailsService::ThrowIfPatchDoesNotExist(valuetype [mscorlib]System.Guid patchId, string parameterName)
0x4bd32  ldarg.0
0x4bd33  ldarg.2
0x4bd34  ldstr    aRequiredpatchi_0// "requiredPatchId"
0x4bd39  call     instance void Microsoft.Crm.ConfigurationDatabase.ClientPatchDetailsService::ThrowIfPatchDoesNotExist(valuetype [mscorlib]System.Guid patchId, string parameterName)
0x4bd3e  ldarg.0
0x4bd3f  ldarg.2
0x4bd40  ldarg.1
0x4bd41  call     instance void Microsoft.Crm.ConfigurationDatabase.ClientPatchDetailsService::ThrowIfRequirementLoopExists(valuetype [mscorlib]System.Guid sourcePatchId, valuetype [mscorlib]System.Guid destinationPatchId)
0x4bd46  newobj   instance void Microsoft.Crm.Data.PropertyBag::.ctor()
0x4bd4b  stloc.0
0x4bd4c  ldloc.0
0x4bd4d  ldstr    aPatchid// "PatchId"
0x4bd52  ldarg.1
0x4bd53  box      [mscorlib]System.Guid
0x4bd58  callvirt instance void Microsoft.Crm.Data.PropertyBag::set_Item(string propertyName, object value)
0x4bd5d  ldloc.0
0x4bd5e  ldstr    aRequiredpatchi// "RequiredPatchId"
0x4bd63  ldarg.2
0x4bd64  box      [mscorlib]System.Guid
0x4bd69  callvirt instance void Microsoft.Crm.Data.PropertyBag::set_Item(string propertyName, object value)
0x4bd6e  ldloc.0
0x4bd6f  ldstr    aId// "Id"
0x4bd74  call     valuetype [mscorlib]System.Guid Microsoft.Crm.SequentialGuid::CreateGuid()
0x4bd79  box      [mscorlib]System.Guid
0x4bd7e  callvirt instance void Microsoft.Crm.Data.PropertyBag::set_Item(string propertyName, object value)
0x4bd83  ldarg.0
0x4bd84  ldfld    class Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService Microsoft.Crm.ConfigurationDatabase.ClientPatchDetailsService::_configService
0x4bd89  ldstr    aClientpatchreq// "ClientPatchRequiredInfo"
0x4bd8e  ldloc.0
0x4bd8f  ldc.i4   0x14B
0x4bd94  ldstr    aCreatepatchreq// "CreatePatchRequirement"
0x4bd99  ldstr    aDA1SSrcPlatfor_35// "D:\\a\\1\\s\\src\\Platform\\Core\\DataS"...
0x4bd9e  callvirt instance object Microsoft.Crm.SharedDatabase.DatabaseService::Create(string tableName, class Microsoft.Crm.Data.PropertyBag columnSet, [opt] int32 sourceLineNumber, [opt] string memberName, [opt] string sourceFilePath)
0x4bda3  pop
0x4bda4  ret
```
