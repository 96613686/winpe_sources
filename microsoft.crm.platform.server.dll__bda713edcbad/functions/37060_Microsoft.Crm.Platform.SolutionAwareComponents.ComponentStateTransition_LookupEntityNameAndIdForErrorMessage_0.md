# Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransition::LookupEntityNameAndIdForErrorMessage_0

- ea: `0x37060`
- end: `0x37386`
- name: `Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransition::LookupEntityNameAndIdForErrorMessage_0`
- size: `806`
- prototype: ``
- caller_count: `3`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x37020`
- `0x37060`
- `0x37390`

## callees

- `0x7690`
- `0x37060`
- `0x37390`
- `0x374c0`
- `0x7f640`
- `0x7f660`
- `0x7f6b0`
- `0x7f6c0`

## string_xrefs

- `0x372ab`: `pluginassemblyid`
- `0x372df`: `fieldsecurityprofileid`

## pseudocode

```c

```

## disassembly

```asm
0x37060  ldarg.3
0x37061  ldsfld   string [mscorlib]System.String::Empty
0x37066  stind.ref
0x37067  ldarg.s  4
0x37069  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x3706e  stobj    [mscorlib]System.Guid
0x37073  ldarg.s  5
0x37075  ldsfld   string [mscorlib]System.String::Empty
0x3707a  stind.ref
0x3707b  ldarg.1
0x3707c  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.EntityFacade.IEntity::get_PlatformName()
0x37081  ldarg.1
0x37082  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.EntityFacade.IEntity::get_IsMetadata()
0x37087  call     int32 Microsoft.Crm.Solution.SolutionComponentTypeMap::RetrieveComponentType(string platformName, bool isMetadata)
0x3708c  stloc.0
0x3708d  ldarg.1
0x3708e  call     class Microsoft.Crm.BusinessEntities.IEntityFacadeBridge Microsoft.Crm.BusinessEntities.EntityFacadeBridgeFactory::Create(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.EntityFacade.IEntity entity)
0x37093  ldarg.1
0x37094  ldarg.2
0x37095  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.EntityFacade.IEntity Microsoft.Crm.BusinessEntities.IEntityFacadeBridge::FillEntityColumns(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.EntityFacade.IEntity entity, class Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x3709a  stloc.1
0x3709b  ldloc.0
0x3709c  ldc.i4.s 0x22
0x3709e  bgt.s    loc_37101
0x370a0  ldloc.0
0x370a1  ldc.i4.s 0x15
0x370a3  bgt.s    loc_370EA
0x370a5  ldloc.0
0x370a6  ldc.i4.4
0x370a7  sub
0x370a8  switch   loc_371CD, loc_3719B, loc_371B4, loc_3715D, loc_371B4, loc_372F7, loc_372F7, loc_3716B, loc_3716B, loc_372F7, loc_372F7, loc_37185
0x370dd  ldloc.0
0x370de  ldc.i4.s 0x15
0x370e0  beq      loc_371E7
0x370e5  br       loc_372F7
0x370ea  ldloc.0
0x370eb  ldc.i4.s 0x17
0x370ed  beq      loc_37201
0x370f2  ldloc.0
0x370f3  ldc.i4.s 0x20
0x370f5  sub
0x370f6  ldc.i4.2
0x370f7  ble.un   loc_3721B
0x370fc  br       loc_372F7
0x37101  ldloc.0
0x37102  ldc.i4.s 0x37
0x37104  bgt.s    loc_37140
0x37106  ldloc.0
0x37107  ldc.i4.s 0x23
0x37109  beq      loc_37235
0x3710e  ldloc.0
0x3710f  ldc.i4.s 0x2F
0x37111  sub
0x37112  switch   loc_3724F, loc_37265, loc_37265, loc_372F7, loc_372F7, loc_37265, loc_3727B, loc_372F7, loc_37265
0x3713b  br       loc_372F7
0x37140  ldloc.0
0x37141  ldc.i4.s 0x47
0x37143  beq      loc_372DD
0x37148  ldloc.0
0x37149  ldc.i4.s 0x5A
0x3714b  beq      loc_372A9
0x37150  ldloc.0
0x37151  ldc.i4.s 0x5D
0x37153  beq      loc_372C3
0x37158  br       loc_372F7
0x3715d  ldarg.0
0x3715e  ldloc.1
0x3715f  ldarg.2
0x37160  ldarg.3
0x37161  ldarg.s  4
0x37163  ldarg.s  5
0x37165  call     instance void Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransition::ProcessLabelForErrorMessage(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.EntityFacade.IEntity entity, class Microsoft.Crm.BusinessEntities.ExecutionContext context, [out] string& entityName, [out] valuetype [mscorlib]System.Guid& entityId, [out] string& nameAttributeValue)
0x3716a  ret
0x3716b  ldarg.0
0x3716c  ldloc.1
0x3716d  ldstr    aEntityrelation_2// "entityrelationshipid"
0x37172  ldc.i4.s 0xA
0x37174  ldstr    aSchemaname_0// "schemaname"
0x37179  ldarg.2
0x3717a  ldarg.3
0x3717b  ldarg.s  4
0x3717d  ldarg.s  5
0x3717f  call     instance void Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransition::FillInEntityInfo(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.EntityFacade.IEntity fullEntity, string lookupAttributeId, int32 solutionComponentType, string nameAttribute, class Microsoft.Crm.BusinessEntities.ExecutionContext context, [out] string& entityName, [out] valuetype [mscorlib]System.Guid& entityId, [out] string& nameAttributeValue)
0x37184  ret
0x37185  ldarg.0
0x37186  ldloc.1
0x37187  ldstr    aEntitykeyattri_0// "entitykeyattributeid"
0x3718c  ldc.i4.s 0xF
0x3718e  ldnull
0x3718f  ldarg.2
0x37190  ldarg.3
0x37191  ldarg.s  4
0x37193  ldarg.s  5
0x37195  call     instance void Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransition::FillInEntityInfo(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.EntityFacade.IEntity fullEntity, string lookupAttributeId, int32 solutionComponentType, string nameAttribute, class Microsoft.Crm.BusinessEntities.ExecutionContext context, [out] string& entityName, [out] valuetype [mscorlib]System.Guid& entityId, [out] string& nameAttributeValue)
0x3719a  ret
0x3719b  ldarg.0
0x3719c  ldloc.1
0x3719d  ldstr    aAttributeid// "attributeid"
0x371a2  ldc.i4.2
0x371a3  ldstr    aName// "name"
0x371a8  ldarg.2
0x371a9  ldarg.3
0x371aa  ldarg.s  4
0x371ac  ldarg.s  5
0x371ae  call     instance void Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransition::FillInEntityInfo(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.EntityFacade.IEntity fullEntity, string lookupAttributeId, int32 solutionComponentType, string nameAttribute, class Microsoft.Crm.BusinessEntities.ExecutionContext context, [out] string& entityName, [out] valuetype [mscorlib]System.Guid& entityId, [out] string& nameAttributeValue)
0x371b3  ret
0x371b4  ldarg.0
0x371b5  ldloc.1
0x371b6  ldstr    aRelationshipid// "relationshipid"
0x371bb  ldc.i4.3
0x371bc  ldstr    aName// "name"
0x371c1  ldarg.2
0x371c2  ldarg.3
0x371c3  ldarg.s  4
0x371c5  ldarg.s  5
0x371c7  call     instance void Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransition::FillInEntityInfo(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.EntityFacade.IEntity fullEntity, string lookupAttributeId, int32 solutionComponentType, string nameAttribute, class Microsoft.Crm.BusinessEntities.ExecutionContext context, [out] string& entityName, [out] valuetype [mscorlib]System.Guid& entityId, [out] string& nameAttributeValue)
0x371cc  ret
0x371cd  ldarg.0
0x371ce  ldloc.1
0x371cf  ldstr    aOptionsetid_0// "optionsetid"
0x371d4  ldc.i4.s 9
0x371d6  ldstr    aName// "name"
0x371db  ldarg.2
0x371dc  ldarg.3
0x371dd  ldarg.s  4
0x371df  ldarg.s  5
0x371e1  call     instance void Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransition::FillInEntityInfo(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.EntityFacade.IEntity fullEntity, string lookupAttributeId, int32 solutionComponentType, string nameAttribute, class Microsoft.Crm.BusinessEntities.ExecutionContext context, [out] string& entityName, [out] valuetype [mscorlib]System.Guid& entityId, [out] string& nameAttributeValue)
0x371e6  ret
0x371e7  ldarg.0
0x371e8  ldloc.1
0x371e9  ldstr    aRoleid// "roleid"
0x371ee  ldc.i4.s 0x14
0x371f0  ldstr    aName// "name"
0x371f5  ldarg.2
0x371f6  ldarg.3
0x371f7  ldarg.s  4
0x371f9  ldarg.s  5
0x371fb  call     instance void Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransition::FillInEntityInfo(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.EntityFacade.IEntity fullEntity, string lookupAttributeId, int32 solutionComponentType, string nameAttribute, class Microsoft.Crm.BusinessEntities.ExecutionContext context, [out] string& entityName, [out] valuetype [mscorlib]System.Guid& entityId, [out] string& nameAttributeValue)
0x37200  ret
0x37201  ldarg.0
0x37202  ldloc.1
0x37203  ldstr    aDisplaystringi// "displaystringid"
0x37208  ldc.i4.s 0x16
0x3720a  ldstr    aDisplaystringk// "displaystringkey"
0x3720f  ldarg.2
0x37210  ldarg.3
0x37211  ldarg.s  4
0x37213  ldarg.s  5
0x37215  call     instance void Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransition::FillInEntityInfo(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.EntityFacade.IEntity fullEntity, string lookupAttributeId, int32 solutionComponentType, string nameAttribute, class Microsoft.Crm.BusinessEntities.ExecutionContext context, [out] string& entityName, [out] valuetype [mscorlib]System.Guid& entityId, [out] string& nameAttributeValue)
0x3721a  ret
0x3721b  ldarg.0
0x3721c  ldloc.1
0x3721d  ldstr    aReportid// "reportid"
0x37222  ldc.i4.s 0x1F
0x37224  ldstr    aName// "name"
0x37229  ldarg.2
0x3722a  ldarg.3
0x3722b  ldarg.s  4
0x3722d  ldarg.s  5
0x3722f  call     instance void Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransition::FillInEntityInfo(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.EntityFacade.IEntity fullEntity, string lookupAttributeId, int32 solutionComponentType, string nameAttribute, class Microsoft.Crm.BusinessEntities.ExecutionContext context, [out] string& entityName, [out] valuetype [mscorlib]System.Guid& entityId, [out] string& nameAttributeValue)
0x37234  ret
0x37235  ldarg.0
0x37236  ldloc.1
0x37237  ldstr    aObjectid// "objectid"
0x3723c  ldc.i4.s 0x24
0x3723e  ldstr    aTitle// "title"
0x37243  ldarg.2
0x37244  ldarg.3
0x37245  ldarg.s  4
0x37247  ldarg.s  5
0x37249  call     instance void Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransition::FillInEntityInfo(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.EntityFacade.IEntity fullEntity, string lookupAttributeId, int32 solutionComponentType, string nameAttribute, class Microsoft.Crm.BusinessEntities.ExecutionContext context, [out] string& entityName, [out] valuetype [mscorlib]System.Guid& entityId, [out] string& nameAttributeValue)
0x3724e  ret
0x3724f  ldarg.0
0x37250  ldloc.1
0x37251  ldstr    aEntitymapid// "entitymapid"
0x37256  ldc.i4.s 0x2E
0x37258  ldnull
0x37259  ldarg.2
0x3725a  ldarg.3
0x3725b  ldarg.s  4
0x3725d  ldarg.s  5
0x3725f  call     instance void Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransition::FillInEntityInfo(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.EntityFacade.IEntity fullEntity, string lookupAttributeId, int32 solutionComponentType, string nameAttribute, class Microsoft.Crm.BusinessEntities.ExecutionContext context, [out] string& entityName, [out] valuetype [mscorlib]System.Guid& entityId, [out] string& nameAttributeValue)
0x37264  ret
0x37265  ldarg.0
0x37266  ldloc.1
0x37267  ldstr    aRibboncustomiz_0// "ribboncustomizationid"
0x3726c  ldc.i4.s 0x32
0x3726e  ldnull
0x3726f  ldarg.2
0x37270  ldarg.3
0x37271  ldarg.s  4
0x37273  ldarg.s  5
0x37275  call     instance void Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransition::FillInEntityInfo(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.EntityFacade.IEntity fullEntity, string lookupAttributeId, int32 solutionComponentType, string nameAttribute, class Microsoft.Crm.BusinessEntities.ExecutionContext context, [out] string& entityName, [out] valuetype [mscorlib]System.Guid& entityId, [out] string& nameAttributeValue)
0x3727a  ret
0x3727b  ldloc.1
0x3727c  ldstr    aRibbondiffid// "ribbondiffid"
0x37281  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.EntityFacade.IEntity::get_Item(string)
0x37286  unbox.any [mscorlib]System.Guid
0x3728b  stloc.2
0x3728c  ldc.i4.s 0x37
0x3728e  call     class Microsoft.Crm.BusinessEntities.IEntityFacadeBridge Microsoft.Crm.BusinessEntities.EntityFacadeBridgeFactory::Create(int32 componentType)
0x37293  ldloc.2
0x37294  ldarg.2
0x37295  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.EntityFacade.IEntity Microsoft.Crm.BusinessEntities.IEntityFacadeBridge::RetrieveEntity(valuetype [mscorlib]System.Guid id, class Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x3729a  stloc.3
0x3729b  ldarg.0
0x3729c  ldloc.3
0x3729d  ldarg.2
0x3729e  ldarg.3
0x3729f  ldarg.s  4
0x372a1  ldarg.s  5
0x372a3  call     instance void Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransition::LookupEntityNameAndIdForErrorMessage(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.EntityFacade.IEntity entity, class Microsoft.Crm.BusinessEntities.ExecutionContext context, [out] string& entityName, [out] valuetype [mscorlib]System.Guid& entityId, [out] string& nameAttributeValue)
0x372a8  ret
0x372a9  ldarg.0
0x372aa  ldloc.1
0x372ab  ldstr    aPluginassembly_0// "pluginassemblyid"
0x372b0  ldc.i4.s 0x5B
0x372b2  ldstr    aName// "name"
0x372b7  ldarg.2
0x372b8  ldarg.3
0x372b9  ldarg.s  4
0x372bb  ldarg.s  5
0x372bd  call     instance void Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransition::FillInEntityInfo(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.EntityFacade.IEntity fullEntity, string lookupAttributeId, int32 solutionComponentType, string nameAttribute, class Microsoft.Crm.BusinessEntities.ExecutionContext context, [out] string& entityName, [out] valuetype [mscorlib]System.Guid& entityId, [out] string& nameAttributeValue)
0x372c2  ret
0x372c3  ldarg.0
0x372c4  ldloc.1
0x372c5  ldstr    aSdkmessageproc_1// "sdkmessageprocessingstepid"
0x372ca  ldc.i4.s 0x5C
0x372cc  ldstr    aName// "name"
0x372d1  ldarg.2
0x372d2  ldarg.3
0x372d3  ldarg.s  4
0x372d5  ldarg.s  5
0x372d7  call     instance void Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransition::FillInEntityInfo(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.EntityFacade.IEntity fullEntity, string lookupAttributeId, int32 solutionComponentType, string nameAttribute, class Microsoft.Crm.BusinessEntities.ExecutionContext context, [out] string& entityName, [out] valuetype [mscorlib]System.Guid& entityId, [out] string& nameAttributeValue)
0x372dc  ret
0x372dd  ldarg.0
0x372de  ldloc.1
0x372df  ldstr    aFieldsecurityp_0// "fieldsecurityprofileid"
0x372e4  ldc.i4.s 0x46
0x372e6  ldstr    aName// "name"
0x372eb  ldarg.2
0x372ec  ldarg.3
0x372ed  ldarg.s  4
0x372ef  ldarg.s  5
0x372f1  call     instance void Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransition::FillInEntityInfo(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.EntityFacade.IEntity fullEntity, string lookupAttributeId, int32 solutionComponentType, string nameAttribute, class Microsoft.Crm.BusinessEntities.ExecutionContext context, [out] string& entityName, [out] valuetype [mscorlib]System.Guid& entityId, [out] string& nameAttributeValue)
0x372f6  ret
0x372f7  ldarg.3
0x372f8  ldarg.1
0x372f9  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.EntityFacade.IEntity::get_PlatformName()
0x372fe  stind.ref
0x372ff  ldarg.s  4
0x37301  ldarg.1
0x37302  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.EntityFacade.IEntity::get_Id()
0x37307  stobj    [mscorlib]System.Guid
0x3730c  ldarg.1
0x3730d  ldstr    aName// "name"
0x37312  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.EntityFacade.IEntity::IsNull(string)
0x37317  brtrue.s loc_3732D
0x37319  ldarg.s  5
0x3731b  ldarg.1
0x3731c  ldstr    aName// "name"
0x37321  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.EntityFacade.IEntity::get_Item(string)
0x37326  callvirt instance string [mscorlib]System.Object::ToString()
0x3732b  stind.ref
0x3732c  ret
0x3732d  ldarg.1
0x3732e  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.EntityFacade.IEntity::get_InnerEntity()
0x37333  isinst   [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity
0x37338  brfalse.s loc_37365
0x3733a  ldarg.1
0x3733b  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.EntityFacade.IEntity::get_InnerEntity()
0x37340  isinst   [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity
0x37345  ldstr    aSchemaname_0// "schemaname"
0x3734a  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::IsPropertyNullOrNameInvalid(string)
0x3734f  brtrue.s loc_37385
0x37351  ldarg.s  5
0x37353  ldarg.1
0x37354  ldstr    aSchemaname_0// "schemaname"
0x37359  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.EntityFacade.IEntity::get_Item(string)
0x3735e  callvirt instance string [mscorlib]System.Object::ToString()
0x37363  stind.ref
0x37364  ret
0x37365  ldarg.1
0x37366  ldstr    aSchemaname_0// "schemaname"
0x3736b  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.EntityFacade.IEntity::IsNull(string)
0x37370  brtrue.s loc_37385
0x37372  ldarg.s  5
0x37374  ldarg.1
0x37375  ldstr    aSchemaname_0// "schemaname"
0x3737a  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.EntityFacade.IEntity::get_Item(string)
0x3737f  callvirt instance string [mscorlib]System.Object::ToString()
0x37384  stind.ref
0x37385  ret
```
