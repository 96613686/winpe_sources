# Microsoft.Crm.Metadata.RelationshipService::Delete_0

- ea: `0x4ee60`
- end: `0x4ef1f`
- name: `Microsoft.Crm.Metadata.RelationshipService::Delete_0`
- size: `191`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops, service_task, broker_com_uri`

## callees

- `0x4ee60`
- `0x4ef20`
- `0x50330`
- `0x503e0`
- `0x57320`
- `0x5a810`

## string_xrefs

- `0x4ee8e`: `prvDeleteRelationship`
- `0x4eeff`: `RelationshipService.Delete caught exception: {0}`

## pseudocode

```c

```

## disassembly

```asm
0x4ee60  ldarg.1
0x4ee61  ldstr    aEntityrelation_9// "entityRelationshipId"
0x4ee66  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfGuidEmpty(valuetype [mscorlib]System.Guid, string)
0x4ee6b  ldarg.2
0x4ee6c  ldstr    aMetadatahelper// "metadataHelper"
0x4ee71  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x4ee76  ldarg.3
0x4ee77  ldstr    aContext// "context"
0x4ee7c  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x4ee81  ldarg.3
0x4ee82  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x4ee87  pop
0x4ee88  ldarg.3
0x4ee89  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_Caller()
0x4ee8e  ldstr    aPrvdeleterelat// "prvDeleteRelationship"
0x4ee93  ldarg.3
0x4ee94  call     valuetype [mscorlib]System.Guid Microsoft.Crm.Metadata.CustomizationSecurityCache::GetPrivilegeIdFromName(string privilegeName, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x4ee99  ldarg.3
0x4ee9a  call     void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SecurityLibrary::CheckPrivilegeGlobalDepth(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x4ee9f  ldarg.3
0x4eea0  callvirt instance bool [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::StartTransactionIfRequired()
0x4eea5  stloc.0
0x4eea6  ldarg.1
0x4eea7  ldarg.3
0x4eea8  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x4eead  call     valuetype [mscorlib]System.Guid Microsoft.Crm.Metadata.RelationshipService::RetrieveRelationshipIdFromEntityRelationshipId(valuetype [mscorlib]System.Guid entityRelationshipId, class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext context)
0x4eeb2  stloc.1
0x4eeb3  call     class [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataQueryHelper [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataQueryHelper::get_Instance()
0x4eeb8  ldloc.1
0x4eeb9  ldstr    aRelationship_0// "Relationship"
0x4eebe  ldarg.3
0x4eebf  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x4eec4  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataQueryHelper::RetrieveMetadataEntity(valuetype [mscorlib]System.Guid, string, class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext)
0x4eec9  stloc.2
0x4eeca  ldarg.0
0x4eecb  ldarg.1
0x4eecc  ldarg.3
0x4eecd  call     instance void Microsoft.Crm.Metadata.RelationshipServiceBase::ValidateForDelete(valuetype [mscorlib]System.Guid entityRelationshipId, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x4eed2  ldarg.0
0x4eed3  ldloc.2
0x4eed4  ldarg.3
0x4eed5  call     instance void Microsoft.Crm.Metadata.RelationshipService::ThrowIfCustomerAttributeRelationship(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity existingRelationship, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x4eeda  ldarg.0
0x4eedb  ldarg.1
0x4eedc  ldloc.2
0x4eedd  ldarg.2
0x4eede  ldarg.3
0x4eedf  call     instance void Microsoft.Crm.Metadata.RelationshipService::DeleteInternal(valuetype [mscorlib]System.Guid entityRelationshipId, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity relationshipData, class [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper metadataHelper, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x4eee4  ldarg.2
0x4eee5  callvirt instance void [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper::ProcessQueue()
0x4eeea  ldloc.0
0x4eeeb  brfalse.s loc_4EEF3
0x4eeed  ldarg.3
0x4eeee  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::CommitTransaction()
0x4eef3  leave.s  loc_4EF1E
0x4eef5  stloc.3
0x4eef6  ldloc.3
0x4eef7  ldarg.3
0x4eef8  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x4eefd  ldc.i4.s 0x19
0x4eeff  ldstr    aRelationshipse// "RelationshipService.Delete caught excep"...
0x4ef04  ldc.i4.1
0x4ef05  newarr   [mscorlib]System.Object
0x4ef0a  dup
0x4ef0b  ldc.i4.0
0x4ef0c  ldloc.3
0x4ef0d  stelem.ref
0x4ef0e  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x4ef13  ldloc.0
0x4ef14  brfalse.s loc_4EF1C
0x4ef16  ldarg.3
0x4ef17  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::RollbackTransaction()
0x4ef1c  rethrow
0x4ef1e  ret
```
