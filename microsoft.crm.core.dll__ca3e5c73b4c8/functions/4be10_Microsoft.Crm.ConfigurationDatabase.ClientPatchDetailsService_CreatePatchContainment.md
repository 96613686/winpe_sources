# Microsoft.Crm.ConfigurationDatabase.ClientPatchDetailsService::CreatePatchContainment

- ea: `0x4be10`
- end: `0x4bea5`
- name: `Microsoft.Crm.ConfigurationDatabase.ClientPatchDetailsService::CreatePatchContainment`
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
- `0x4c380`
- `0x61910`

## string_xrefs

- `0x4be99`: `D:\a\1\s\src\Platform\Core\DataServices\Configuration\ObjectModel\ClientPatchDetails.cs`
- `0x4be94`: `CreatePatchContainment`

## pseudocode

```c

```

## disassembly

```asm
0x4be10  ldarg.1
0x4be11  ldstr    aPatchid_0// "patchId"
0x4be16  call     void Microsoft.Crm.Exceptions::ThrowIfGuidEmpty(valuetype [mscorlib]System.Guid parameter, string name)
0x4be1b  ldarg.2
0x4be1c  ldstr    aContainedpatch_0// "containedPatchId"
0x4be21  call     void Microsoft.Crm.Exceptions::ThrowIfGuidEmpty(valuetype [mscorlib]System.Guid parameter, string name)
0x4be26  ldarg.0
0x4be27  ldarg.1
0x4be28  ldstr    aPatchid_0// "patchId"
0x4be2d  call     instance void Microsoft.Crm.ConfigurationDatabase.ClientPatchDetailsService::ThrowIfPatchDoesNotExist(valuetype [mscorlib]System.Guid patchId, string parameterName)
0x4be32  ldarg.0
0x4be33  ldarg.2
0x4be34  ldstr    aContainedpatch_0// "containedPatchId"
0x4be39  call     instance void Microsoft.Crm.ConfigurationDatabase.ClientPatchDetailsService::ThrowIfPatchDoesNotExist(valuetype [mscorlib]System.Guid patchId, string parameterName)
0x4be3e  ldarg.0
0x4be3f  ldarg.2
0x4be40  ldarg.1
0x4be41  call     instance void Microsoft.Crm.ConfigurationDatabase.ClientPatchDetailsService::ThrowIfContainmentLoopExists(valuetype [mscorlib]System.Guid sourcePatchId, valuetype [mscorlib]System.Guid destinationPatchId)
0x4be46  newobj   instance void Microsoft.Crm.Data.PropertyBag::.ctor()
0x4be4b  stloc.0
0x4be4c  ldloc.0
0x4be4d  ldstr    aPatchid// "PatchId"
0x4be52  ldarg.1
0x4be53  box      [mscorlib]System.Guid
0x4be58  callvirt instance void Microsoft.Crm.Data.PropertyBag::set_Item(string propertyName, object value)
0x4be5d  ldloc.0
0x4be5e  ldstr    aContainedpatch// "ContainedPatchId"
0x4be63  ldarg.2
0x4be64  box      [mscorlib]System.Guid
0x4be69  callvirt instance void Microsoft.Crm.Data.PropertyBag::set_Item(string propertyName, object value)
0x4be6e  ldloc.0
0x4be6f  ldstr    aId// "Id"
0x4be74  call     valuetype [mscorlib]System.Guid Microsoft.Crm.SequentialGuid::CreateGuid()
0x4be79  box      [mscorlib]System.Guid
0x4be7e  callvirt instance void Microsoft.Crm.Data.PropertyBag::set_Item(string propertyName, object value)
0x4be83  ldarg.0
0x4be84  ldfld    class Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService Microsoft.Crm.ConfigurationDatabase.ClientPatchDetailsService::_configService
0x4be89  ldstr    aClientpatchcon// "ClientPatchContainedInfo"
0x4be8e  ldloc.0
0x4be8f  ldc.i4   0x171
0x4be94  ldstr    aCreatepatchcon// "CreatePatchContainment"
0x4be99  ldstr    aDA1SSrcPlatfor_35// "D:\\a\\1\\s\\src\\Platform\\Core\\DataS"...
0x4be9e  callvirt instance object Microsoft.Crm.SharedDatabase.DatabaseService::Create(string tableName, class Microsoft.Crm.Data.PropertyBag columnSet, [opt] int32 sourceLineNumber, [opt] string memberName, [opt] string sourceFilePath)
0x4bea3  pop
0x4bea4  ret
```
