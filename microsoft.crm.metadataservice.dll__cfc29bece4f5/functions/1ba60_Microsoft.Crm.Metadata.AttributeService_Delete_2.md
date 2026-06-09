# Microsoft.Crm.Metadata.AttributeService::Delete_2

- ea: `0x1ba60`
- end: `0x1bb49`
- name: `Microsoft.Crm.Metadata.AttributeService::Delete_2`
- size: `233`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x1b070`
- `0x1b980`

## callees

- `0x1ba60`
- `0x20d90`
- `0x20fd0`
- `0x21160`
- `0x23300`
- `0x29080`

## string_xrefs

- `0x1ba75`: `DeleteAttribute`
- `0x1ba7a`: `DeleteAttribute`

## pseudocode

```c

```

## disassembly

```asm
0x1ba60  ldarg.0
0x1ba61  ldarg.1
0x1ba62  ldarg.3
0x1ba63  ldarg.s  4
0x1ba65  call     instance void Microsoft.Crm.Metadata.AttributeService::DeleteChildAttributes(valuetype [mscorlib]System.Guid attributeId, class [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper metadataHelper, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x1ba6a  ldarg.0
0x1ba6b  ldarg.1
0x1ba6c  ldarg.3
0x1ba6d  ldarg.s  4
0x1ba6f  call     instance void Microsoft.Crm.Metadata.AttributeService::ClearLinkedAttribute(valuetype [mscorlib]System.Guid attributeId, class [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper metadataHelper, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x1ba74  ldarg.1
0x1ba75  ldstr    aDeleteattribut// "DeleteAttribute"
0x1ba7a  ldstr    aDeleteattribut// "DeleteAttribute"
0x1ba7f  ldc.i4.0
0x1ba80  ldarg.s  4
0x1ba82  call     void Microsoft.Crm.Metadata.AuditHelper::InvokeAuditMetadataPlugin(valuetype [mscorlib]System.Guid targetId, string messageName, string requestName, bool isAuditEnabled, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x1ba87  call     class [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataQueryHelper [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataQueryHelper::get_Instance()
0x1ba8c  ldarg.1
0x1ba8d  ldstr    aAttribute// "Attribute"
0x1ba92  ldc.i4.4
0x1ba93  newarr   [mscorlib]System.String
0x1ba98  dup
0x1ba99  ldc.i4.0
0x1ba9a  ldstr    aEntityid// "entityid"
0x1ba9f  stelem.ref
0x1baa0  dup
0x1baa1  ldc.i4.1
0x1baa2  ldstr    aLogicalname// "logicalname"
0x1baa7  stelem.ref
0x1baa8  dup
0x1baa9  ldc.i4.2
0x1baaa  ldstr    aIssecured// "issecured"
0x1baaf  stelem.ref
0x1bab0  dup
0x1bab1  ldc.i4.3
0x1bab2  ldstr    aSourcetype// "sourcetype"
0x1bab7  stelem.ref
0x1bab8  ldarg.s  4
0x1baba  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataQueryHelper::RetrieveMetadataEntityPublished(valuetype [mscorlib]System.Guid, string, string[], class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x1babf  dup
0x1bac0  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag::.ctor(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity)
0x1bac5  stloc.0
0x1bac6  ldstr    aIssecured// "issecured"
0x1bacb  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x1bad0  unbox.any [mscorlib]System.Boolean
0x1bad5  brfalse.s loc_1BAEC
0x1bad7  ldarg.2
0x1bad8  ldarg.3
0x1bad9  ldarg.s  4
0x1badb  ldc.i4.1
0x1badc  ldc.i4.1
0x1badd  ldc.i4.1
0x1bade  newarr   [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription
0x1bae3  dup
0x1bae4  ldc.i4.0
0x1bae5  ldloc.0
0x1bae6  stelem.ref
0x1bae7  call     void Microsoft.Crm.Metadata.AttributeService::DeleteSecuredAttributeFromProfiles(int32 parentEntityTypeCode, class [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper helper, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, bool deletePOAAEntries, bool resetSubscriptions, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription[] attributesToDelete)
0x1baec  call     class [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataQueryHelper [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataQueryHelper::get_Instance()
0x1baf1  ldarg.1
0x1baf2  ldstr    aAttribute// "Attribute"
0x1baf7  ldarg.s  4
0x1baf9  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataQueryHelper::RetrieveMetadataEntity(valuetype [mscorlib]System.Guid, string, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x1bafe  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag::.ctor(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity)
0x1bb03  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::get_EntityId()
0x1bb08  ldarg.3
0x1bb09  ldc.i4.1
0x1bb0a  newarr   [mscorlib]System.String
0x1bb0f  dup
0x1bb10  ldc.i4.0
0x1bb11  ldstr    aDataproviderid// "dataproviderid"
0x1bb16  stelem.ref
0x1bb17  ldarg.s  4
0x1bb19  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x1bb1e  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IEntityDescription Microsoft.Crm.Metadata.AttributeService::GetParentEntity(valuetype [mscorlib]System.Guid entityId, class [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper helper, string[] columnNames, class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext context)
0x1bb23  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IEntityDescription::get_DataProviderId()
0x1bb28  stloc.2
0x1bb29  ldloca.s 2
0x1bb2b  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::get_HasValue()
0x1bb30  stloc.1
0x1bb31  ldarg.3
0x1bb32  ldloc.0
0x1bb33  ldc.i4.2
0x1bb34  ldloc.1
0x1bb35  callvirt instance void [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper::AddToQueue(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IAttributeDescription, valuetype [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.ActionType, bool)
0x1bb3a  ldarg.1
0x1bb3b  ldc.i4.2
0x1bb3c  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Solution.SolutionComponentMoniker::.ctor(valuetype [mscorlib]System.Guid, int32)
0x1bb41  ldarg.s  4
0x1bb43  call     void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.SolutionComponentHelper::DeleteFromAllSolutions(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Solution.SolutionComponentMoniker, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x1bb48  ret
```
