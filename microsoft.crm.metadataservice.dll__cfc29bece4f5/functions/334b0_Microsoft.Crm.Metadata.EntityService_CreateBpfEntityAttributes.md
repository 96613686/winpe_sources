# Microsoft.Crm.Metadata.EntityService::CreateBpfEntityAttributes

- ea: `0x334b0`
- end: `0x33574`
- name: `Microsoft.Crm.Metadata.EntityService::CreateBpfEntityAttributes`
- size: `196`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x32b80`
- `0x76e30`

## callees

- `0x33580`
- `0x33670`

## string_xrefs

- `0x33511`: `TraversedPath`
- `0x334e0`: `ProcessId`
- `0x33516`: `TraversedPathInfoDescription`
- `0x3351b`: `TraversedPathInfoDisplayName`
- `0x3353a`: `CompletedOn`
- `0x3353f`: `CompletedOnInfoDescription`
- `0x33544`: `CompletedOnInfoDisplayName`

## pseudocode

```c

```

## disassembly

```asm
0x334b0  ldarg.0
0x334b1  ldarg.1
0x334b2  ldarg.2
0x334b3  ldarg.3
0x334b4  ldstr    aActivestageid// "ActiveStageId"
0x334b9  ldstr    aActivestageinf// "ActiveStageInfoDescription"
0x334be  ldstr    aActivestageinf_0// "ActiveStageInfoDisplayName"
0x334c3  ldstr    aProcessstage// "ProcessStage"
0x334c8  ldc.i4   0x1274
0x334cd  ldstr    aStagename// "stagename"
0x334d2  ldstr    aProcessstageid// "processstageid"
0x334d7  call     instance void Microsoft.Crm.Metadata.EntityService::CreateBpfEntityLookupAttribute(class Microsoft.Crm.Metadata.IEntityInfo entityInfo, class [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper metadataHelper, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, string attributeName, string description, string displayName, string targetEntityLogicalName, int32 targetEntityObjectTypeCode, string targetEntityNameAttribute, string targetEntityPrimaryKey)
0x334dc  ldarg.0
0x334dd  ldarg.1
0x334de  ldarg.2
0x334df  ldarg.3
0x334e0  ldstr    aProcessid// "ProcessId"
0x334e5  ldstr    aProcessinfodes// "ProcessInfoDescription"
0x334ea  ldstr    aProcessinfodis// "ProcessInfoDisplayName"
0x334ef  ldstr    aWorkflow// "Workflow"
0x334f4  ldc.i4   0x125F
0x334f9  ldstr    aName// "name"
0x334fe  ldstr    aWorkflowid// "workflowid"
0x33503  call     instance void Microsoft.Crm.Metadata.EntityService::CreateBpfEntityLookupAttribute(class Microsoft.Crm.Metadata.IEntityInfo entityInfo, class [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper metadataHelper, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, string attributeName, string description, string displayName, string targetEntityLogicalName, int32 targetEntityObjectTypeCode, string targetEntityNameAttribute, string targetEntityPrimaryKey)
0x33508  ldarg.0
0x33509  ldarg.1
0x3350a  ldarg.2
0x3350b  ldarg.3
0x3350c  ldstr    aNvarchar// "nvarchar"
0x33511  ldstr    aTraversedpath// "TraversedPath"
0x33516  ldstr    aTraversedpathi// "TraversedPathInfoDescription"
0x3351b  ldstr    aTraversedpathi_0// "TraversedPathInfoDisplayName"
0x33520  ldc.i4.0
0x33521  ldc.i4   0x9C4
0x33526  ldc.i4   0x4E2
0x3352b  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Metadata.EntityService::CreateBpfEntityAttribute(class Microsoft.Crm.Metadata.IEntityInfo entityInfo, class [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper metadataHelper, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, string attributeType, string attributeName, string descriptionResource, string displayNameResource, int32 referencedEntityObjectTypeCode, [opt] int32 length, [opt] int32 maxLength)
0x33530  pop
0x33531  ldarg.0
0x33532  ldarg.1
0x33533  ldarg.2
0x33534  ldarg.3
0x33535  ldstr    aDatetime// "datetime"
0x3353a  ldstr    aCompletedon// "CompletedOn"
0x3353f  ldstr    aCompletedoninf// "CompletedOnInfoDescription"
0x33544  ldstr    aCompletedoninf_0// "CompletedOnInfoDisplayName"
0x33549  ldc.i4.0
0x3354a  ldc.i4.0
0x3354b  ldc.i4.0
0x3354c  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Metadata.EntityService::CreateBpfEntityAttribute(class Microsoft.Crm.Metadata.IEntityInfo entityInfo, class [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper metadataHelper, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, string attributeType, string attributeName, string descriptionResource, string displayNameResource, int32 referencedEntityObjectTypeCode, [opt] int32 length, [opt] int32 maxLength)
0x33551  pop
0x33552  ldarg.0
0x33553  ldarg.1
0x33554  ldarg.2
0x33555  ldarg.3
0x33556  ldstr    aDatetime// "datetime"
0x3355b  ldstr    aActivestagesta// "ActiveStageStartedOn"
0x33560  ldstr    aActivestagesta_0// "ActiveStageStartedOnInfoDescription"
0x33565  ldstr    aActivestagesta_1// "ActiveStageStartedOnInfoDisplayName"
0x3356a  ldc.i4.0
0x3356b  ldc.i4.0
0x3356c  ldc.i4.0
0x3356d  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Metadata.EntityService::CreateBpfEntityAttribute(class Microsoft.Crm.Metadata.IEntityInfo entityInfo, class [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper metadataHelper, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, string attributeType, string attributeName, string descriptionResource, string displayNameResource, int32 referencedEntityObjectTypeCode, [opt] int32 length, [opt] int32 maxLength)
0x33572  pop
0x33573  ret
```
