# Microsoft.Crm.Metadata.EntityService::CreateBusinessProcessMetadata

- ea: `0x34b80`
- end: `0x34bfa`
- name: `Microsoft.Crm.Metadata.EntityService::CreateBusinessProcessMetadata`
- size: `122`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x32f30`
- `0x65400`
- `0x78560`

## callees

- `0x34b80`
- `0x34c00`
- `0x34d50`
- `0x521c0`

## string_xrefs

- `0x34ba4`: `processid`
- `0x34ba9`: `ProcessIdAttributeDescription`
- `0x34bae`: `ProcessIdAttributeDisplayName`
- `0x34bd4`: `traversedpath`
- `0x34bd9`: `TraversedPathAttributeDescription`
- `0x34bde`: `TraversedPathAttributeDisplayName`

## pseudocode

```c

```

## disassembly

```asm
0x34b80  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x34b85  stloc.0
0x34b86  ldarg.0
0x34b87  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityDescription::get_IsActivity()
0x34b8c  brfalse.s loc_34BA2
0x34b8e  ldstr    aStageid_0// "stageid"
0x34b93  ldarg.0
0x34b94  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityDescription::get_EntityId()
0x34b99  ldarg.3
0x34b9a  call     valuetype [mscorlib]System.Guid Microsoft.Crm.Metadata.EntityService::RetrieveAttributeId(string attributeName, valuetype [mscorlib]System.Guid entityId, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x34b9f  stloc.0
0x34ba0  br.s     loc_34BEA
0x34ba2  ldarg.0
0x34ba3  ldarg.2
0x34ba4  ldstr    aProcessid_0// "processid"
0x34ba9  ldstr    aProcessidattri// "ProcessIdAttributeDescription"
0x34bae  ldstr    aProcessidattri_0// "ProcessIdAttributeDisplayName"
0x34bb3  ldarg.3
0x34bb4  call     valuetype [mscorlib]System.Guid Microsoft.Crm.Metadata.EntityService::CreateBusinessProcessField(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityDescriptionPropertyBag entityDescription, class [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper metadataHelper, string attributeName, string descriptionResourceName, string displayNameResourceName, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x34bb9  pop
0x34bba  ldarg.0
0x34bbb  ldarg.2
0x34bbc  ldstr    aStageid_0// "stageid"
0x34bc1  ldstr    aStageidattribu// "StageIdAttributeDescription"
0x34bc6  ldstr    aStageidattribu_0// "StageIdAttributeDisplayName"
0x34bcb  ldarg.3
0x34bcc  call     valuetype [mscorlib]System.Guid Microsoft.Crm.Metadata.EntityService::CreateBusinessProcessField(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityDescriptionPropertyBag entityDescription, class [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper metadataHelper, string attributeName, string descriptionResourceName, string displayNameResourceName, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x34bd1  stloc.0
0x34bd2  ldarg.0
0x34bd3  ldarg.2
0x34bd4  ldstr    aTraversedpath_0// "traversedpath"
0x34bd9  ldstr    aTraversedpatha// "TraversedPathAttributeDescription"
0x34bde  ldstr    aTraversedpatha_0// "TraversedPathAttributeDisplayName"
0x34be3  ldarg.3
0x34be4  call     valuetype [mscorlib]System.Guid Microsoft.Crm.Metadata.EntityService::CreateBusinessProcessField(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityDescriptionPropertyBag entityDescription, class [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper metadataHelper, string attributeName, string descriptionResourceName, string displayNameResourceName, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x34be9  pop
0x34bea  ldarg.0
0x34beb  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityDescriptionPropertyBag::get_InnerEntityData()
0x34bf0  ldarg.1
0x34bf1  ldloc.0
0x34bf2  ldarg.2
0x34bf3  ldarg.3
0x34bf4  call     void Microsoft.Crm.Metadata.RelationshipService::CreateProcessStageRelationship(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity entityData, string entityLogicalName, valuetype [mscorlib]System.Guid stageId, class [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper metadataHelper, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x34bf9  ret
```
