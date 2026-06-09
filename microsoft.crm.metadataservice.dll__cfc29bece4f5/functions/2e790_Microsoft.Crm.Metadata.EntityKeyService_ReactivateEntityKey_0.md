# Microsoft.Crm.Metadata.EntityKeyService::ReactivateEntityKey_0

- ea: `0x2e790`
- end: `0x2e832`
- name: `Microsoft.Crm.Metadata.EntityKeyService::ReactivateEntityKey_0`
- size: `162`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0xde60`
- `0x2e740`

## callees

- `0x2dbc0`
- `0x2e790`
- `0x2e840`
- `0x2ea70`
- `0x5a810`

## string_xrefs

- `0x2e7ad`: `prvReadEntityKey`
- `0x2e796`: `prvCreateEntityKey`

## pseudocode

```c

```

## disassembly

```asm
0x2e790  ldarg.2
0x2e791  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_Caller()
0x2e796  ldstr    aPrvcreateentit// "prvCreateEntityKey"
0x2e79b  ldarg.2
0x2e79c  call     valuetype [mscorlib]System.Guid Microsoft.Crm.Metadata.CustomizationSecurityCache::GetPrivilegeIdFromName(string privilegeName, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x2e7a1  ldarg.2
0x2e7a2  call     void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SecurityLibrary::CheckPrivilegeGlobalDepth(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x2e7a7  ldarg.2
0x2e7a8  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_Caller()
0x2e7ad  ldstr    aPrvreadentityk// "prvReadEntityKey"
0x2e7b2  ldarg.2
0x2e7b3  call     valuetype [mscorlib]System.Guid Microsoft.Crm.Metadata.CustomizationSecurityCache::GetPrivilegeIdFromName(string privilegeName, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x2e7b8  ldarg.2
0x2e7b9  call     void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SecurityLibrary::CheckPrivilegeGlobalDepth(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x2e7be  ldarg.2
0x2e7bf  callvirt instance bool [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::StartTransactionIfRequired()
0x2e7c4  stloc.0
0x2e7c5  call     valuetype [mscorlib]System.Guid [mscorlib]System.Guid::NewGuid()
0x2e7ca  stloc.1
0x2e7cb  ldarg.0
0x2e7cc  ldarg.1
0x2e7cd  ldloc.1
0x2e7ce  ldarg.2
0x2e7cf  call     instance void Microsoft.Crm.Metadata.EntityKeyService::ValidateAndUpdateEntityKey(valuetype [mscorlib]System.Guid entityKeyId, valuetype [mscorlib]System.Guid asyncJobId, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x2e7d4  ldarg.2
0x2e7d5  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x2e7da  ldarg.1
0x2e7db  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityKeyMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntityKey(valuetype [mscorlib]System.Guid)
0x2e7e0  stloc.2
0x2e7e1  ldarg.0
0x2e7e2  ldloc.2
0x2e7e3  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityKeyMetadata::get_AsyncJobId()
0x2e7e8  ldarg.2
0x2e7e9  call     instance void Microsoft.Crm.Metadata.EntityKeyService::DeleteAsyncJob(valuetype [mscorlib]System.Guid asyncOperationId, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x2e7ee  ldarg.0
0x2e7ef  ldloc.2
0x2e7f0  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityKeyMetadata::get_EntityId()
0x2e7f5  ldarg.1
0x2e7f6  ldloc.1
0x2e7f7  ldarg.2
0x2e7f8  call     instance void Microsoft.Crm.Metadata.EntityKeyService::ExecuteAsyncJobForIndexCreation(valuetype [mscorlib]System.Guid entityId, valuetype [mscorlib]System.Guid entityKeyId, valuetype [mscorlib]System.Guid asyncJobId, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x2e7fd  ldloc.0
0x2e7fe  brfalse.s loc_2E806
0x2e800  ldarg.2
0x2e801  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::CommitTransaction()
0x2e806  leave.s  loc_2E831
0x2e808  stloc.3
0x2e809  ldloc.3
0x2e80a  ldarg.2
0x2e80b  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x2e810  ldc.i4.s 0x19
0x2e812  ldstr    aReactivateEnti// "Reactivate Entity Key caught exception:"...
0x2e817  ldc.i4.1
0x2e818  newarr   [mscorlib]System.Object
0x2e81d  dup
0x2e81e  ldc.i4.0
0x2e81f  ldloc.3
0x2e820  stelem.ref
0x2e821  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x2e826  ldloc.0
0x2e827  brfalse.s loc_2E82F
0x2e829  ldarg.2
0x2e82a  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::RollbackTransaction()
0x2e82f  rethrow
0x2e831  ret
```
