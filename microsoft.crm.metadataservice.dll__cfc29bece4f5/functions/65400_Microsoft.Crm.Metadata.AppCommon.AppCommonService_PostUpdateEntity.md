# Microsoft.Crm.Metadata.AppCommon.AppCommonService::PostUpdateEntity

- ea: `0x65400`
- end: `0x65b4f`
- name: `Microsoft.Crm.Metadata.AppCommon.AppCommonService::PostUpdateEntity`
- size: `1871`
- prototype: ``
- caller_count: `1`
- callee_count: `30`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x37ad0`

## callees

- `0x331b0`
- `0x34b80`
- `0x37750`
- `0x39410`
- `0x3ab10`
- `0x3ab20`
- `0x3ab30`
- `0x3ab80`
- `0x3cc40`
- `0x3cc60`
- `0x3cc80`
- `0x3ccc0`
- `0x3cda0`
- `0x3d020`
- `0x3d1a0`
- `0x3d7b0`
- `0x50a20`
- `0x50ee0`
- `0x50f40`
- `0x51000`
- `0x55b40`
- `0x59320`
- `0x593c0`
- `0x59420`
- `0x61990`
- `0x65320`
- `0x65400`
- `0x65b80`
- `0x65c60`
- `0x78480`

## string_xrefs

- `0x65769`: `isdocumentrecommendationsenabled`
- `0x65829`: `CheckExistingBeforeCreateForInternalSystemConvertedSolutions`

## pseudocode

```c

```

## disassembly

```asm
0x65400  newobj   instance void <>c__DisplayClass10_0::.ctor()
0x65405  stloc.0
0x65406  ldloc.0
0x65407  ldarg.2
0x65408  stfld    class [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper <>c__DisplayClass10_0::metadataHelper
0x6540d  ldloc.0
0x6540e  ldarg.1
0x6540f  stfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext <>c__DisplayClass10_0::context
0x65414  ldloc.0
0x65415  ldarg.0
0x65416  stfld    class Microsoft.Crm.Metadata.EntityUpdateInfo <>c__DisplayClass10_0::entityInfo
0x6541b  ldloc.0
0x6541c  ldfld    class Microsoft.Crm.Metadata.EntityUpdateInfo <>c__DisplayClass10_0::entityInfo
0x65421  ldstr    aEntityinfo// "entityInfo"
0x65426  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x6542b  ldloc.0
0x6542c  ldloc.0
0x6542d  ldfld    class Microsoft.Crm.Metadata.EntityUpdateInfo <>c__DisplayClass10_0::entityInfo
0x65432  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityDescriptionPropertyBag Microsoft.Crm.Metadata.EntityUpdateInfo::get_EntityDescription()
0x65437  stfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityDescriptionPropertyBag <>c__DisplayClass10_0::entityDescription
0x6543c  ldloc.0
0x6543d  ldfld    class Microsoft.Crm.Metadata.EntityUpdateInfo <>c__DisplayClass10_0::entityInfo
0x65442  callvirt instance bool Microsoft.Crm.Metadata.EntityUpdateInfo::get_IsActivity()
0x65447  brfalse.s loc_65472
0x65449  ldloc.0
0x6544a  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext <>c__DisplayClass10_0::context
0x6544f  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x65454  call     bool [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SolutionsHelper::IsInSystemConvertedSolutionUpgradeContext(class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext)
0x65459  brfalse.s loc_65472
0x6545b  ldloc.0
0x6545c  ldfld    class Microsoft.Crm.Metadata.EntityUpdateInfo <>c__DisplayClass10_0::entityInfo
0x65461  ldloc.0
0x65462  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext <>c__DisplayClass10_0::context
0x65467  ldloc.0
0x65468  ldfld    class [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper <>c__DisplayClass10_0::metadataHelper
0x6546d  call     void Microsoft.Crm.Metadata.AppCommon.AppCommonService::PostUpdateActivityEntity(class Microsoft.Crm.Metadata.EntityUpdateInfo entityInfo, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, class [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper metadataHelper)
0x65472  ldc.i4.1
0x65473  call     class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.IEntityFacadeBridge [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.EntityFacadeBridgeFactory::Create(int32)
0x65478  ldloc.0
0x65479  ldfld    class Microsoft.Crm.Metadata.EntityUpdateInfo <>c__DisplayClass10_0::entityInfo
0x6547e  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Metadata.EntityUpdateInfo::get_EntityId()
0x65483  ldloc.0
0x65484  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext <>c__DisplayClass10_0::context
0x65489  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.EntityFacade.IEntity [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.IEntityFacadeBridge::RetrieveEntity(valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x6548e  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.EntityFacade.IEntity::get_InnerEntity()
0x65493  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity
0x65498  stloc.1
0x65499  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.AttributeService::.ctor()
0x6549e  stloc.2
0x6549f  ldloc.0
0x654a0  ldnull
0x654a1  stfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity <>c__DisplayClass10_0::primaryFieldAttribute
0x654a6  ldloc.2
0x654a7  ldloc.0
0x654a8  ldfld    class Microsoft.Crm.Metadata.EntityUpdateInfo <>c__DisplayClass10_0::entityInfo
0x654ad  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Metadata.EntityUpdateInfo::get_EntityId()
0x654b2  ldstr    aAttribute// "Attribute"
0x654b7  ldc.i4.2
0x654b8  newarr   [mscorlib]System.String
0x654bd  dup
0x654be  ldc.i4.0
0x654bf  ldstr    aAttributeid// "attributeid"
0x654c4  stelem.ref
0x654c5  dup
0x654c6  ldc.i4.1
0x654c7  ldstr    aIslogical// "islogical"
0x654cc  stelem.ref
0x654cd  ldloc.0
0x654ce  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext <>c__DisplayClass10_0::context
0x654d3  call     class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.ColumnCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.ColumnCollection::CreateColumnsCollection(string, string[], class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x654d8  ldloc.0
0x654d9  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext <>c__DisplayClass10_0::context
0x654de  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x654e3  ldloc.0
0x654e4  ldflda   class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity <>c__DisplayClass10_0::primaryFieldAttribute
0x654e9  callvirt instance bool [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.AttributeService::TryRetrievePrimaryFieldAttributeAsIfPublished(valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.ColumnCollection, class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity&)
0x654ee  pop
0x654ef  ldloc.2
0x654f0  ldloc.0
0x654f1  ldfld    class Microsoft.Crm.Metadata.EntityUpdateInfo <>c__DisplayClass10_0::entityInfo
0x654f6  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Metadata.EntityUpdateInfo::get_EntityId()
0x654fb  ldstr    aAttribute// "Attribute"
0x65500  ldc.i4.1
0x65501  newarr   [mscorlib]System.String
0x65506  dup
0x65507  ldc.i4.0
0x65508  ldstr    aAttributeid// "attributeid"
0x6550d  stelem.ref
0x6550e  ldloc.0
0x6550f  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext <>c__DisplayClass10_0::context
0x65514  call     class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.ColumnCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.ColumnCollection::CreateColumnsCollection(string, string[], class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x65519  ldloc.0
0x6551a  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext <>c__DisplayClass10_0::context
0x6551f  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x65524  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.AttributeService::RetrievePrimaryKeyAttributeAsIfPublished(valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.ColumnCollection, class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext)
0x65529  stloc.3
0x6552a  ldloc.0
0x6552b  ldloc.3
0x6552c  ldstr    aAttributeid// "attributeid"
0x65531  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x65536  unbox.any [mscorlib]System.Guid
0x6553b  stfld    valuetype [mscorlib]System.Guid <>c__DisplayClass10_0::primaryKeyAttributeId
0x65540  ldloc.0
0x65541  ldloc.1
0x65542  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityDescriptionPropertyBag::.ctor(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity)
0x65547  stfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityDescriptionPropertyBag <>c__DisplayClass10_0::existingEntityDescription
0x6554c  ldloc.0
0x6554d  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityDescriptionPropertyBag <>c__DisplayClass10_0::entityDescription
0x65552  ldloc.0
0x65553  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityDescriptionPropertyBag <>c__DisplayClass10_0::existingEntityDescription
0x65558  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityDescriptionPropertyBag [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityDescriptionPropertyBag::CreateDifferenceDescription(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityDescriptionPropertyBag)
0x6555d  stloc.s  4
0x6555f  ldloc.0
0x65560  ldfld    class Microsoft.Crm.Metadata.EntityUpdateInfo <>c__DisplayClass10_0::entityInfo
0x65565  callvirt instance bool Microsoft.Crm.Metadata.EntityUpdateInfo::get_HasRelatedActivities()
0x6556a  brfalse.s loc_65587
0x6556c  ldloc.0
0x6556d  ldfld    class Microsoft.Crm.Metadata.EntityUpdateInfo <>c__DisplayClass10_0::entityInfo
0x65572  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Metadata.EntityUpdateInfo::get_EntityId()
0x65577  ldloc.0
0x65578  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext <>c__DisplayClass10_0::context
0x6557d  call     bool Microsoft.Crm.Metadata.EntityService::HasRelatedActivities(valuetype [mscorlib]System.Guid entityId, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x65582  ldc.i4.0
0x65583  ceq
0x65585  br.s     loc_65588
0x65587  ldc.i4.0
0x65588  stloc.s  5
0x6558a  ldloc.0
0x6558b  ldfld    class Microsoft.Crm.Metadata.EntityUpdateInfo <>c__DisplayClass10_0::entityInfo
0x65590  callvirt instance bool Microsoft.Crm.Metadata.EntityUpdateInfo::get_HasRelatedNotes()
0x65595  brfalse.s loc_655B2
0x65597  ldloc.0
0x65598  ldfld    class Microsoft.Crm.Metadata.EntityUpdateInfo <>c__DisplayClass10_0::entityInfo
0x6559d  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Metadata.EntityUpdateInfo::get_EntityId()
0x655a2  ldloc.0
0x655a3  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext <>c__DisplayClass10_0::context
0x655a8  call     bool Microsoft.Crm.Metadata.EntityService::HasRelatedNotes(valuetype [mscorlib]System.Guid entityId, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x655ad  ldc.i4.0
0x655ae  ceq
0x655b0  br.s     loc_655B3
0x655b2  ldc.i4.0
0x655b3  stloc.s  6
0x655b5  ldloc.0
0x655b6  ldfld    class Microsoft.Crm.Metadata.EntityUpdateInfo <>c__DisplayClass10_0::entityInfo
0x655bb  callvirt instance bool Microsoft.Crm.Metadata.EntityUpdateInfo::get_HasRelatedFeedback()
0x655c0  brfalse.s loc_655E3
0x655c2  ldloc.0
0x655c3  ldfld    class Microsoft.Crm.Metadata.EntityUpdateInfo <>c__DisplayClass10_0::entityInfo
0x655c8  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Metadata.EntityUpdateInfo::get_EntityId()
0x655cd  ldloc.0
0x655ce  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext <>c__DisplayClass10_0::context
0x655d3  ldloc.0
0x655d4  ldfld    valuetype [mscorlib]System.Guid <>c__DisplayClass10_0::primaryKeyAttributeId
0x655d9  call     bool Microsoft.Crm.Metadata.EntityService::HasRelatedFeedback(valuetype [mscorlib]System.Guid entityId, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, valuetype [mscorlib]System.Guid primaryKeyAttributeId)
0x655de  ldc.i4.0
0x655df  ceq
0x655e1  br.s     loc_655E4
0x655e3  ldc.i4.0
0x655e4  stloc.s  7
0x655e6  ldloc.0
0x655e7  ldfld    class Microsoft.Crm.Metadata.EntityUpdateInfo <>c__DisplayClass10_0::entityInfo
0x655ec  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityDescriptionPropertyBag Microsoft.Crm.Metadata.EntityUpdateInfo::get_EntityDescription()
0x655f1  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityDescriptionPropertyBag::get_InnerEntityData()
0x655f6  ldstr    aIsconnectionse// "isconnectionsenabled"
0x655fb  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::IsPropertyNull(string)
0x65600  brtrue.s loc_6562A
0x65602  ldloc.0
0x65603  ldfld    class Microsoft.Crm.Metadata.EntityUpdateInfo <>c__DisplayClass10_0::entityInfo
0x65608  callvirt instance bool Microsoft.Crm.Metadata.EntityUpdateInfo::get_IsConnectionsEnabled()
0x6560d  brfalse.s loc_6562A
0x6560f  ldloc.0
0x65610  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityDescriptionPropertyBag <>c__DisplayClass10_0::entityDescription
0x65615  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityDescriptionPropertyBag::get_InnerEntityData()
0x6561a  ldloc.0
0x6561b  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext <>c__DisplayClass10_0::context
0x65620  call     bool Microsoft.Crm.Metadata.EntityService::IsConnectionsEnabled(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity entityData, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x65625  ldc.i4.0
0x65626  ceq
0x65628  br.s     loc_6562B
0x6562a  ldc.i4.0
0x6562b  ldloc.0
0x6562c  ldloc.1
0x6562d  ldstr    aLogicalname// "logicalname"
0x65632  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x65637  castclass [mscorlib]System.String
0x6563c  stfld    string <>c__DisplayClass10_0::logicalName
0x65641  brfalse.s loc_656B0
0x65643  ldloc.0
0x65644  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityDescriptionPropertyBag <>c__DisplayClass10_0::entityDescription
0x65649  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityDescriptionPropertyBag::get_InnerEntityData()
0x6564e  ldloc.0
0x6564f  ldfld    valuetype [mscorlib]System.Guid <>c__DisplayClass10_0::primaryKeyAttributeId
0x65654  ldloc.0
0x65655  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity <>c__DisplayClass10_0::primaryFieldAttribute
0x6565a  dup
0x6565b  brtrue.s loc_65661
0x6565d  pop
0x6565e  ldnull
0x6565f  br.s     loc_6566B
0x65661  ldstr    aAttributeid// "attributeid"
0x65666  call     instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x6566b  unbox.any valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>
0x65670  stloc.s  8
0x65672  ldloca.s 8
0x65674  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::get_HasValue()
0x65679  brtrue.s loc_65682
0x6567b  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x65680  br.s     loc_65689
0x65682  ldloca.s 8
0x65684  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::GetValueOrDefault()
0x65689  ldloc.0
0x6568a  ldfld    class [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper <>c__DisplayClass10_0::metadataHelper
0x6568f  ldloc.0
0x65690  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext <>c__DisplayClass10_0::context
0x65695  ldloc.0
0x65696  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityDescriptionPropertyBag <>c__DisplayClass10_0::entityDescription
0x6569b  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityDescription::get_DataProviderId()
0x656a0  stloc.s  8
0x656a2  ldloca.s 8
0x656a4  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::get_HasValue()
0x656a9  call     void Microsoft.Crm.Metadata.RelationshipService::CreateConnectionRelationship(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity entityData, valuetype [mscorlib]System.Guid primaryKeyId, valuetype [mscorlib]System.Guid primaryFieldId, class [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper metadataHelper, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, bool isVirtualEntity)
0x656ae  br.s     loc_656F2
0x656b0  ldloc.0
0x656b1  ldfld    class Microsoft.Crm.Metadata.EntityUpdateInfo <>c__DisplayClass10_0::entityInfo
0x656b6  callvirt instance bool Microsoft.Crm.Metadata.EntityUpdateInfo::get_IsConnectionsEnabled()
0x656bb  brfalse.s loc_656F2
0x656bd  ldloc.0
0x656be  ldfld    class Microsoft.Crm.Metadata.EntityUpdateInfo <>c__DisplayClass10_0::entityInfo
0x656c3  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityDescriptionPropertyBag Microsoft.Crm.Metadata.EntityUpdateInfo::get_EntityDescription()
0x656c8  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityDescription::get_EntityId()
0x656cd  ldloc.0
0x656ce  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext <>c__DisplayClass10_0::context
0x656d3  call     bool Microsoft.Crm.Metadata.UpgradeHelper::IsEntityNotSystemOwnedDuringSystemConvertedUpgrade(valuetype [mscorlib]System.Guid entityId, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x656d8  brfalse.s loc_656F2
0x656da  ldloc.0
0x656db  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext <>c__DisplayClass10_0::context
0x656e0  ldloc.0
0x656e1  ldftn    instance void <>c__DisplayClass10_0::<PostUpdateEntity>b__0()
0x656e7  newobj   instance void [mscorlib]System.Action::.ctor(object, native int)
0x656ec  ldc.i4.0
0x656ed  call     void Microsoft.Crm.Metadata.UpgradeHelper::ExecuteCreateInUpgradeContext(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, class [mscorlib]System.Action action, [opt] bool CreateIfExistingNotFound)
0x656f2  ldloc.0
0x656f3  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityDescriptionPropertyBag <>c__DisplayClass10_0::entityDescription
0x656f8  ldstr    aIsdocumentmana// "isdocumentmanagementenabled"
0x656fd  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ManagedMetadataDescriptionBase::get_Item(string)
0x65702  brfalse.s loc_65781
0x65704  ldloc.0
0x65705  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityDescriptionPropertyBag <>c__DisplayClass10_0::entityDescription
0x6570a  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityDescription::get_IsDocumentManagementEnabled()
0x6570f  brfalse.s loc_6574F
0x65711  ldloc.0
0x65712  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext <>c__DisplayClass10_0::context
0x65717  ldc.i4.1
0x65718  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SystemUserContext::.ctor(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext, bool)
0x6571d  stloc.s  9
0x6571f  ldloc.0
0x65720  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityDescriptionPropertyBag <>c__DisplayClass10_0::entityDescription
0x65725  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityDescriptionPropertyBag::get_InnerEntityData()
0x6572a  ldloc.0
0x6572b  ldfld    class [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper <>c__DisplayClass10_0::metadataHelper
0x65730  ldloc.0
0x65731  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity <>c__DisplayClass10_0::primaryFieldAttribute
0x65736  ldloc.0
0x65737  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext <>c__DisplayClass10_0::context
0x6573c  call     void Microsoft.Crm.Metadata.EntityService::CreateDocumentManagementRelationshipIfDoesntExist(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity entityData, class [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper metadataHelper, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity primaryFieldAttribute, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x65741  leave.s  loc_65781
0x65743  ldloc.s  9
0x65745  brfalse.s loc_6574E
0x65747  ldloc.s  9
0x65749  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x6574e  endfinally
0x6574f  ldloc.1
0x65750  ldstr    aIsonenoteinteg// "isonenoteintegrationenabled"
0x65755  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::IsPropertyNullOrNameInvalid(string)
0x6575a  brtrue.s loc_65768
0x6575c  ldloc.0
0x6575d  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityDescriptionPropertyBag <>c__DisplayClass10_0::entityDescription
0x65762  ldc.i4.0
0x65763  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityDescription::set_IsOneNoteIntegrationEnabled(bool)
0x65768  ldloc.1
0x65769  ldstr    aIsdocumentreco// "isdocumentrecommendationsenabled"
0x6576e  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::IsPropertyNullOrNameInvalid(string)
0x65773  brtrue.s loc_65781
0x65775  ldloc.0
0x65776  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityDescriptionPropertyBag <>c__DisplayClass10_0::entityDescription
0x6577b  ldc.i4.0
0x6577c  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityDescription::set_IsDocumentRecommendationsEnabled(bool)
0x65781  ldloc.0
0x65782  ldfld    class Microsoft.Crm.Metadata.EntityUpdateInfo <>c__DisplayClass10_0::entityInfo
0x65787  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityDescriptionPropertyBag Microsoft.Crm.Metadata.EntityUpdateInfo::get_EntityDescription()
0x6578c  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityDescriptionPropertyBag::get_InnerEntityData()
0x65791  ldstr    aIsknowledgeman// "isknowledgemanagementenabled"
0x65796  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::IsPropertyNullOrNameInvalid(string)
0x6579b  brtrue.s loc_657EF
0x6579d  ldloc.0
0x6579e  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityDescriptionPropertyBag <>c__DisplayClass10_0::entityDescription
0x657a3  ldstr    aIsknowledgeman// "isknowledgemanagementenabled"
0x657a8  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ManagedMetadataDescriptionBase::get_Item(string)
0x657ad  brfalse.s loc_657EF
0x657af  ldloc.0
  ... truncated ...
```
