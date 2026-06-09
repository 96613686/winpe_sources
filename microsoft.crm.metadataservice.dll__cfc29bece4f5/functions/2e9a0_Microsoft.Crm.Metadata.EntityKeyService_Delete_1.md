# Microsoft.Crm.Metadata.EntityKeyService::Delete_1

- ea: `0x2e9a0`
- end: `0x2ea4d`
- name: `Microsoft.Crm.Metadata.EntityKeyService::Delete_1`
- size: `173`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x2e980`
- `0x5f010`

## callees

- `0x2e9a0`
- `0x2ea50`
- `0x5a810`

## string_xrefs

- `0x2e9ce`: `prvDeleteEntityKey`
- `0x2ea2d`: `EntityKeyService.Delete caught exception: {0}`

## pseudocode

```c

```

## disassembly

```asm
0x2e9a0  ldarg.1
0x2e9a1  ldstr    aEntitykeyid_0// "entityKeyId"
0x2e9a6  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfGuidEmpty(valuetype [mscorlib]System.Guid, string)
0x2e9ab  ldarg.2
0x2e9ac  ldstr    aMetadatahelper// "metadataHelper"
0x2e9b1  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x2e9b6  ldarg.3
0x2e9b7  ldstr    aContext// "context"
0x2e9bc  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x2e9c1  ldarg.3
0x2e9c2  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x2e9c7  pop
0x2e9c8  ldarg.3
0x2e9c9  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_Caller()
0x2e9ce  ldstr    aPrvdeleteentit// "prvDeleteEntityKey"
0x2e9d3  ldarg.3
0x2e9d4  call     valuetype [mscorlib]System.Guid Microsoft.Crm.Metadata.CustomizationSecurityCache::GetPrivilegeIdFromName(string privilegeName, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x2e9d9  ldarg.3
0x2e9da  call     void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SecurityLibrary::CheckPrivilegeGlobalDepth(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x2e9df  ldarg.3
0x2e9e0  callvirt instance bool [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::StartTransactionIfRequired()
0x2e9e5  stloc.0
0x2e9e6  ldarg.0
0x2e9e7  ldarg.1
0x2e9e8  ldarg.3
0x2e9e9  call     instance void Microsoft.Crm.Metadata.EntityKeyService::ValidateAndDelete(valuetype [mscorlib]System.Guid entityKeyId, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x2e9ee  ldarg.3
0x2e9ef  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityKeyDescriptionPropertyBag::.ctor(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x2e9f4  stloc.1
0x2e9f5  ldloc.1
0x2e9f6  ldarg.1
0x2e9f7  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityKeyDescription::set_EntityKeyId(valuetype [mscorlib]System.Guid)
0x2e9fc  ldarg.2
0x2e9fd  ldloc.1
0x2e9fe  ldc.i4.2
0x2e9ff  callvirt instance void [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper::AddToQueue(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IEntityKeyDescription, valuetype [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.ActionType)
0x2ea04  ldarg.2
0x2ea05  callvirt instance void [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper::ProcessQueue()
0x2ea0a  ldarg.1
0x2ea0b  ldc.i4.s 0xE
0x2ea0d  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Solution.SolutionComponentMoniker::.ctor(valuetype [mscorlib]System.Guid, int32)
0x2ea12  ldarg.3
0x2ea13  call     void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.SolutionComponentHelper::DeleteFromAllSolutions(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Solution.SolutionComponentMoniker, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x2ea18  ldloc.0
0x2ea19  brfalse.s loc_2EA21
0x2ea1b  ldarg.3
0x2ea1c  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::CommitTransaction()
0x2ea21  leave.s  loc_2EA4C
0x2ea23  stloc.2
0x2ea24  ldloc.2
0x2ea25  ldarg.3
0x2ea26  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x2ea2b  ldc.i4.s 0x19
0x2ea2d  ldstr    aEntitykeyservi_1// "EntityKeyService.Delete caught exceptio"...
0x2ea32  ldc.i4.1
0x2ea33  newarr   [mscorlib]System.Object
0x2ea38  dup
0x2ea39  ldc.i4.0
0x2ea3a  ldloc.2
0x2ea3b  stelem.ref
0x2ea3c  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x2ea41  ldloc.0
0x2ea42  brfalse.s loc_2EA4A
0x2ea44  ldarg.3
0x2ea45  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::RollbackTransaction()
0x2ea4a  rethrow
0x2ea4c  ret
```
