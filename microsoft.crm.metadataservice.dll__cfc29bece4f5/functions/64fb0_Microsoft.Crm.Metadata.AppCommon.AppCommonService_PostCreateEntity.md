# Microsoft.Crm.Metadata.AppCommon.AppCommonService::PostCreateEntity

- ea: `0x64fb0`
- end: `0x65162`
- name: `Microsoft.Crm.Metadata.AppCommon.AppCommonService::PostCreateEntity`
- size: `434`
- prototype: ``
- caller_count: `1`
- callee_count: `27`
- tags: `service_task, broker_com_uri`

## callers

- `0x32b80`

## callees

- `0x18440`
- `0x2ca90`
- `0x2cb70`
- `0x2ccf0`
- `0x2cd10`
- `0x2cd70`
- `0x2cdb0`
- `0x2d050`
- `0x2d070`
- `0x2d0b0`
- `0x2d0f0`
- `0x2d1b0`
- `0x2d530`
- `0x2d550`
- `0x331b0`
- `0x332d0`
- `0x39150`
- `0x50a20`
- `0x50ee0`
- `0x50f40`
- `0x51000`
- `0x52160`
- `0x55b40`
- `0x61960`
- `0x64fb0`
- `0x652e0`
- `0x65b80`

## string_xrefs

- `0x64fda`: `service`

## pseudocode

```c

```

## disassembly

```asm
0x64fb0  ldarg.0
0x64fb1  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityDescriptionPropertyBag Microsoft.Crm.Metadata.EntityCreateInfo::get_EntityDescription()
0x64fb6  stloc.0
0x64fb7  ldarg.0
0x64fb8  callvirt instance bool Microsoft.Crm.Metadata.EntityCreateInfo::get_IsActivity()
0x64fbd  brfalse.s loc_64FC7
0x64fbf  ldarg.0
0x64fc0  ldarg.1
0x64fc1  ldarg.2
0x64fc2  call     void Microsoft.Crm.Metadata.AppCommon.AppCommonService::PostCreateActivityEntity(class Microsoft.Crm.Metadata.EntityCreateInfo entityInfo, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, class [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper metadataHelper)
0x64fc7  ldarg.0
0x64fc8  callvirt instance bool Microsoft.Crm.Metadata.EntityCreateInfo::get_HasRelatedActivities()
0x64fcd  brfalse.s loc_65005
0x64fcf  ldarg.0
0x64fd0  callvirt instance string Microsoft.Crm.Metadata.EntityCreateInfo::get_LogicalName()
0x64fd5  callvirt instance string [mscorlib]System.String::ToLower()
0x64fda  ldstr    aService// "service"
0x64fdf  callvirt instance bool [mscorlib]System.String::Equals(string)
0x64fe4  brtrue.s loc_65005
0x64fe6  ldarg.1
0x64fe7  ldc.i4.0
0x64fe8  call     class [mscorlib]System.Collections.Generic.List`1<string> Microsoft.Crm.Metadata.AppCommon.AppCommonService::GetActivitiesList(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, [opt] bool isUpdateContext)
0x64fed  ldarg.0
0x64fee  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityDescriptionPropertyBag Microsoft.Crm.Metadata.EntityCreateInfo::get_EntityDescription()
0x64ff3  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityDescriptionPropertyBag::get_InnerEntityData()
0x64ff8  ldarg.0
0x64ff9  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Metadata.EntityCreateInfo::get_PrimaryKeyId()
0x64ffe  ldarg.2
0x64fff  ldarg.1
0x65000  call     void Microsoft.Crm.Metadata.RelationshipService::CreateActivityRelationship(class [mscorlib]System.Collections.Generic.List`1<string> activityNames, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity entityData, valuetype [mscorlib]System.Guid primaryKeyId, class [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper metadataHelper, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x65005  ldarg.0
0x65006  callvirt instance bool Microsoft.Crm.Metadata.EntityCreateInfo::get_IsConnectionsEnabled()
0x6500b  brfalse.s loc_6503E
0x6500d  ldarg.0
0x6500e  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityDescriptionPropertyBag Microsoft.Crm.Metadata.EntityCreateInfo::get_EntityDescription()
0x65013  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityDescriptionPropertyBag::get_InnerEntityData()
0x65018  ldarg.0
0x65019  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Metadata.EntityCreateInfo::get_PrimaryKeyId()
0x6501e  ldarg.0
0x6501f  callvirt instance class Microsoft.Crm.Metadata.AttributeInfo Microsoft.Crm.Metadata.EntityCreateInfo::get_PrimaryField()
0x65024  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Metadata.AttributeInfo::get_AttributeId()
0x65029  ldarg.2
0x6502a  ldarg.1
0x6502b  ldarg.0
0x6502c  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> Microsoft.Crm.Metadata.EntityCreateInfo::get_DataProviderId()
0x65031  stloc.1
0x65032  ldloca.s 1
0x65034  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::get_HasValue()
0x65039  call     void Microsoft.Crm.Metadata.RelationshipService::CreateConnectionRelationship(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity entityData, valuetype [mscorlib]System.Guid primaryKeyId, valuetype [mscorlib]System.Guid primaryFieldId, class [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper metadataHelper, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, bool isVirtualEntity)
0x6503e  ldloc.0
0x6503f  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityDescription::get_IsCollaboration()
0x65044  brfalse.s loc_65059
0x65046  ldloc.0
0x65047  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityDescriptionPropertyBag::get_InnerEntityData()
0x6504c  ldarg.0
0x6504d  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Metadata.EntityCreateInfo::get_PrimaryKeyId()
0x65052  ldarg.2
0x65053  ldarg.1
0x65054  call     void Microsoft.Crm.Metadata.RelationshipService::CreateQueueItemRelationship(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity entityData, valuetype [mscorlib]System.Guid primaryKeyId, class [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper metadataHelper, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x65059  ldarg.0
0x6505a  callvirt instance bool Microsoft.Crm.Metadata.EntityCreateInfo::get_HasRelatedNotes()
0x6505f  brfalse.s loc_65079
0x65061  ldarg.0
0x65062  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityDescriptionPropertyBag Microsoft.Crm.Metadata.EntityCreateInfo::get_EntityDescription()
0x65067  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityDescriptionPropertyBag::get_InnerEntityData()
0x6506c  ldarg.0
0x6506d  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Metadata.EntityCreateInfo::get_PrimaryKeyId()
0x65072  ldarg.2
0x65073  ldarg.1
0x65074  call     void Microsoft.Crm.Metadata.RelationshipService::CreateAnnotationRelationship(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity entityData, valuetype [mscorlib]System.Guid primaryKeyId, class [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper metadataHelper, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x65079  ldarg.0
0x6507a  callvirt instance bool Microsoft.Crm.Metadata.EntityCreateInfo::get_HasRelatedFeedback()
0x6507f  brfalse.s loc_650E6
0x65081  ldarg.0
0x65082  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityDescriptionPropertyBag Microsoft.Crm.Metadata.EntityCreateInfo::get_EntityDescription()
0x65087  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityDescriptionPropertyBag::get_InnerEntityData()
0x6508c  ldarg.0
0x6508d  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Metadata.EntityCreateInfo::get_PrimaryKeyId()
0x65092  ldarg.2
0x65093  ldarg.1
0x65094  call     valuetype [mscorlib]System.Guid Microsoft.Crm.Metadata.RelationshipService::CreateFeedbackRelationship(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity entityData, valuetype [mscorlib]System.Guid primaryKeyId, class [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper metadataHelper, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x65099  stloc.2
0x6509a  ldarg.2
0x6509b  ldloc.2
0x6509c  ldarg.1
0x6509d  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x650a2  ldc.i4   0x26E6
0x650a7  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(int32)
0x650ac  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_Id()
0x650b1  ldstr    aRegardingobjec_6// "regardingobjectidname"
0x650b6  ldarg.0
0x650b7  callvirt instance class Microsoft.Crm.Metadata.AttributeInfo Microsoft.Crm.Metadata.EntityCreateInfo::get_PrimaryField()
0x650bc  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Metadata.AttributeInfo::get_AttributeId()
0x650c1  ldarg.1
0x650c2  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x650c7  callvirt instance bool [Microsoft.Crm.Core]Microsoft.Crm.ISolutionContext::get_IsSystemContext()
0x650cc  brtrue.s loc_650D1
0x650ce  ldc.i4.1
0x650cf  br.s     loc_650D2
0x650d1  ldc.i4.0
0x650d2  ldarg.1
0x650d3  ldarg.0
0x650d4  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> Microsoft.Crm.Metadata.EntityCreateInfo::get_DataProviderId()
0x650d9  stloc.1
0x650da  ldloca.s 1
0x650dc  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::get_HasValue()
0x650e1  call     void Microsoft.Crm.Metadata.RelationshipService::CreateViewInfoForRelationship(class [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper metadataHelper, valuetype [mscorlib]System.Guid relationshipId, valuetype [mscorlib]System.Guid referencingEntityId, string referencingEntityNameViewAttributeId, valuetype [mscorlib]System.Guid primaryFieldAttributeId, valuetype [Microsoft.Crm.Core]Microsoft.Crm.ContextModifierOption option, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, [opt] bool isVirtualEntity)
0x650e6  ldarg.1
0x650e7  call     bool [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ObjectServiceUtility::IsSLAFeatureAvailable(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x650ec  brfalse.s loc_65151
0x650ee  ldarg.0
0x650ef  callvirt instance bool Microsoft.Crm.Metadata.EntityCreateInfo::get_IsSLAEnabled()
0x650f4  brfalse.s loc_65151
0x650f6  ldarg.0
0x650f7  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityDescriptionPropertyBag Microsoft.Crm.Metadata.EntityCreateInfo::get_EntityDescription()
0x650fc  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityDescription::get_EntityId()
0x65101  ldarg.0
0x65102  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection Microsoft.Crm.Metadata.EntityCreateInfo::get_DisplayName()
0x65107  ldarg.1
0x65108  ldc.i4.0
0x65109  call     class [mscorlib]System.Collections.Generic.List`1<object> Microsoft.Crm.Metadata.EntityService::GetEntityDisplayInfo(valuetype [mscorlib]System.Guid entityId, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection newDisplayNameCollection, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, [opt] bool retrieveDeletedLabels)
0x6510e  ldc.i4.1
0x6510f  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<object>::get_Item(!!T0)
0x65114  castclass [mscorlib]System.String
0x65119  stloc.3
0x6511a  ldstr    aA483e6d485ef45// "a483e6d4-85ef-457a-9bf4-5dfff8381e88"
0x6511f  ldloc.3
0x65120  ldarg.0
0x65121  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityDescriptionPropertyBag Microsoft.Crm.Metadata.EntityCreateInfo::get_EntityDescription()
0x65126  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityDescription::get_ObjectTypeCode()
0x6512b  ldstr    aA483e6d485ef45// "a483e6d4-85ef-457a-9bf4-5dfff8381e88"
0x65130  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x65135  ldc.i4.0
0x65136  ldarg.1
0x65137  call     void Microsoft.Crm.Metadata.EntityService::AddorUpdateGlobalOptionSetValues(string globalOptionSetId, string entityName, int32 objectTypeCode, valuetype [mscorlib]System.Guid optionSetId, bool isUpdate, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x6513c  ldloc.0
0x6513d  ldarg.2
0x6513e  ldc.i4.1
0x6513f  ldarg.1
0x65140  ldloc.0
0x65141  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityDescription::get_IsCustomEntity()
0x65146  ldloc.0
0x65147  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityDescription::get_IsActivity()
0x6514c  call     void Microsoft.Crm.Metadata.EntityService::CreateRequiredSLAAttributeAndRelationship(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityDescriptionPropertyBag entityDescription, class [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper metadataHelper, bool isCreate, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, bool isCustomEntity, bool isActivity)
0x65151  ldarg.0
0x65152  callvirt instance bool Microsoft.Crm.Metadata.EntityCreateInfo::get_IsKnowledgeManagementEnabled()
0x65157  brfalse.s loc_65161
0x65159  ldarg.1
0x6515a  ldarg.2
0x6515b  ldloc.0
0x6515c  call     void Microsoft.Crm.Metadata.CrmCommon.KnowledgeRelationship::CreateKnowledgeManagementRelationship(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, class [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper metadataHelper, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityDescriptionPropertyBag entityDescription)
0x65161  ret
```
