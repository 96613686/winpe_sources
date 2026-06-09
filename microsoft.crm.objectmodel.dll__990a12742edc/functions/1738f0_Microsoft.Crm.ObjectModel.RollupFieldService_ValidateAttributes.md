# Microsoft.Crm.ObjectModel.RollupFieldService::ValidateAttributes

- ea: `0x1738f0`
- end: `0x173be9`
- name: `Microsoft.Crm.ObjectModel.RollupFieldService::ValidateAttributes`
- size: `761`
- prototype: ``
- caller_count: `2`
- callee_count: `11`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x173ee0`
- `0x173f40`

## callees

- `0x6cfa0`
- `0x6cfb0`
- `0x6d140`
- `0x1738f0`
- `0x173bf0`
- `0x173da0`
- `0x173dd0`
- `0x173e80`
- `0x176630`
- `0x176720`
- `0x1767f0`

## string_xrefs

- `0x173b86`: `CREATE`
- `0x173bb4`: `CREATE`
- `0x173b7f`: `UPDATE`
- `0x173a56`: `isamount`
- `0x173aa4`: `isamount`
- `0x173a67`: `amountdatatype`
- `0x173af9`: `amountdatatype`

## pseudocode

```c

```

## disassembly

```asm
0x1738f0  ldc.i4.m1
0x1738f1  stloc.0
0x1738f2  ldnull
0x1738f3  stloc.1
0x1738f4  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x1738f9  stloc.2
0x1738fa  ldarg.2
0x1738fb  brtrue.s loc_173941
0x1738fd  ldarg.0
0x1738fe  ldarg.1
0x1738ff  ldstr    aRollupfieldid// "rollupfieldid"
0x173904  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x173909  unbox.any [mscorlib]System.Guid
0x17390e  ldarg.3
0x17390f  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity Microsoft.Crm.ObjectModel.RollupFieldService::GetMetricLineItem(valuetype [mscorlib]System.Guid metricLineItemId, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x173914  stloc.1
0x173915  ldloc.1
0x173916  ldstr    aMetricid// "metricid"
0x17391b  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x173920  unbox.any [mscorlib]System.Guid
0x173925  stloc.2
0x173926  ldloc.2
0x173927  ldc.i4.1
0x173928  ldarg.3
0x173929  call     bool Microsoft.Crm.ObjectModel.GoalUtil::IsMetricRelatedToGoals(valuetype [mscorlib]System.Guid metricId, bool checkState, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x17392e  brfalse.s loc_173941
0x173930  ldc.i4   0x80044801
0x173935  ldc.i4.0
0x173936  newarr   [mscorlib]System.Object
0x17393b  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0x173940  throw
0x173941  ldarg.2
0x173942  brfalse.s loc_173957
0x173944  ldarg.1
0x173945  ldstr    aSourceentity// "sourceentity"
0x17394a  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x17394f  unbox.any [mscorlib]System.Int32
0x173954  stloc.0
0x173955  br.s     loc_173968
0x173957  ldloc.1
0x173958  ldstr    aSourceentity// "sourceentity"
0x17395d  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x173962  unbox.any [mscorlib]System.Int32
0x173967  stloc.0
0x173968  ldarg.3
0x173969  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x17396e  ldloc.0
0x17396f  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(int32)
0x173974  stloc.3
0x173975  ldnull
0x173976  stloc.s  4
0x173978  ldloc.3
0x173979  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_IsChildEntity()
0x17397e  brfalse.s loc_17398D
0x173980  ldloc.3
0x173981  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Relationship [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::GetParentChildRelationship()
0x173986  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Relationship::get_ReferencedEntity()
0x17398b  stloc.s  4
0x17398d  ldarg.2
0x17398e  brfalse.s loc_1739A3
0x173990  ldloc.s  4
0x173992  brfalse.s loc_17399D
0x173994  ldloc.s  4
0x173996  call     void Microsoft.Crm.ObjectModel.GoalUtil::ValidateEntityForRollup(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata entityMetadata)
0x17399b  br.s     loc_1739A3
0x17399d  ldloc.3
0x17399e  call     void Microsoft.Crm.ObjectModel.GoalUtil::ValidateEntityForRollup(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata entityMetadata)
0x1739a3  ldarg.1
0x1739a4  ldstr    aDateattribute// "dateattribute"
0x1739a9  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::IsAttributeNull(string)
0x1739ae  brtrue.s loc_173A27
0x1739b0  ldarg.1
0x1739b1  ldstr    aDateattribute// "dateattribute"
0x1739b6  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x1739bb  castclass [mscorlib]System.String
0x1739c0  stloc.s  0xC
0x1739c2  ldarg.1
0x1739c3  ldstr    aEntityfordatea// "entityfordateattribute"
0x1739c8  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::IsAttributeNull(string)
0x1739cd  brtrue.s loc_173A27
0x1739cf  ldarg.1
0x1739d0  ldstr    aEntityfordatea// "entityfordateattribute"
0x1739d5  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x1739da  unbox.any [mscorlib]System.Int32
0x1739df  ldloc.0
0x1739e0  bne.un.s loc_1739ED
0x1739e2  ldarg.0
0x1739e3  ldloc.s  0xC
0x1739e5  ldloc.3
0x1739e6  call     instance void Microsoft.Crm.ObjectModel.RollupFieldService::ValidateAttributeBelongToSourceEntity(string attribute, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata metadata)
0x1739eb  br.s     loc_173A27
0x1739ed  ldloc.s  4
0x1739ef  brfalse.s loc_173A16
0x1739f1  ldarg.1
0x1739f2  ldstr    aEntityfordatea// "entityfordateattribute"
0x1739f7  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x1739fc  unbox.any [mscorlib]System.Int32
0x173a01  ldloc.s  4
0x173a03  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_Code()
0x173a08  bne.un.s loc_173A16
0x173a0a  ldarg.0
0x173a0b  ldloc.s  0xC
0x173a0d  ldloc.s  4
0x173a0f  call     instance void Microsoft.Crm.ObjectModel.RollupFieldService::ValidateAttributeBelongToSourceEntity(string attribute, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata metadata)
0x173a14  br.s     loc_173A27
0x173a16  ldc.i4   0x80044812
0x173a1b  ldc.i4.0
0x173a1c  newarr   [mscorlib]System.Object
0x173a21  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0x173a26  throw
0x173a27  ldarg.2
0x173a28  brfalse.s loc_173A3B
0x173a2a  ldarg.1
0x173a2b  ldstr    aMetricid// "metricid"
0x173a30  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x173a35  unbox.any [mscorlib]System.Guid
0x173a3a  stloc.2
0x173a3b  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::.ctor()
0x173a40  stloc.s  5
0x173a42  ldstr    aMetric// "Metric"
0x173a47  ldarg.3
0x173a48  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext)
0x173a4d  stloc.s  6
0x173a4f  ldloc.s  6
0x173a51  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x173a56  ldstr    aIsamount// "isamount"
0x173a5b  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumn(string)
0x173a60  ldloc.s  6
0x173a62  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x173a67  ldstr    aAmountdatatype// "amountdatatype"
0x173a6c  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumn(string)
0x173a71  ldnull
0x173a72  stloc.s  7
0x173a74  ldarg.3
0x173a75  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SystemUserContext::.ctor(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x173a7a  stloc.s  0xD
0x173a7c  ldloc.s  5
0x173a7e  ldloc.2
0x173a7f  ldstr    aMetric// "Metric"
0x173a84  ldarg.3
0x173a85  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::.ctor(valuetype [mscorlib]System.Guid, string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x173a8a  ldloc.s  6
0x173a8c  ldarg.3
0x173a8d  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::Retrieve(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x173a92  stloc.s  7
0x173a94  leave.s  loc_173AA2
0x173a96  ldloc.s  0xD
0x173a98  brfalse.s loc_173AA1
0x173a9a  ldloc.s  0xD
0x173a9c  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x173aa1  endfinally
0x173aa2  ldloc.s  7
0x173aa4  ldstr    aIsamount// "isamount"
0x173aa9  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x173aae  unbox.any [mscorlib]System.Boolean
0x173ab3  stloc.s  8
0x173ab5  ldc.i4.m1
0x173ab6  stloc.s  9
0x173ab8  ldloc.s  8
0x173aba  brtrue.s loc_173ADA
0x173abc  ldarg.1
0x173abd  ldstr    aSourceattribut_4// "sourceattribute"
0x173ac2  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x173ac7  brfalse.s loc_173B3E
0x173ac9  ldc.i4   0x80044804
0x173ace  ldc.i4.0
0x173acf  newarr   [mscorlib]System.Object
0x173ad4  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0x173ad9  throw
0x173ada  ldarg.2
0x173adb  brfalse.s loc_173AF7
0x173add  ldarg.1
0x173ade  ldstr    aSourceattribut_4// "sourceattribute"
0x173ae3  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x173ae8  castclass [mscorlib]System.String
0x173aed  ldstr    aSourceAttribut// "Source attribute"
0x173af2  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string, string)
0x173af7  ldloc.s  7
0x173af9  ldstr    aAmountdatatype// "amountdatatype"
0x173afe  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x173b03  unbox.any [mscorlib]System.Int32
0x173b08  stloc.s  9
0x173b0a  ldarg.1
0x173b0b  ldstr    aSourceattribut_4// "sourceattribute"
0x173b10  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::IsAttributeNull(string)
0x173b15  brtrue.s loc_173B3E
0x173b17  ldarg.1
0x173b18  ldstr    aSourceattribut_4// "sourceattribute"
0x173b1d  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x173b22  castclass [mscorlib]System.String
0x173b27  stloc.s  0xE
0x173b29  ldarg.0
0x173b2a  ldloc.s  0xE
0x173b2c  ldloc.3
0x173b2d  call     instance void Microsoft.Crm.ObjectModel.RollupFieldService::ValidateAttributeBelongToSourceEntity(string attribute, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata metadata)
0x173b32  ldarg.0
0x173b33  ldloc.s  9
0x173b35  ldloc.0
0x173b36  ldloc.s  0xE
0x173b38  ldarg.3
0x173b39  call     instance void Microsoft.Crm.ObjectModel.RollupFieldService::ValidateSourceAttributeDataType(int32 goalType, int32 sourceEntityOTC, string sourceAttribute, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x173b3e  ldarg.0
0x173b3f  ldarg.1
0x173b40  ldloc.3
0x173b41  ldarg.2
0x173b42  call     instance void Microsoft.Crm.ObjectModel.RollupFieldService::ValidateStateStatus(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity entity, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata srcEntitymetadata, bool IsCreate)
0x173b47  ldarg.2
0x173b48  brfalse.s loc_173B7C
0x173b4a  ldarg.1
0x173b4b  ldstr    aGoalattribute// "goalattribute"
0x173b50  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x173b55  castclass [mscorlib]System.String
0x173b5a  stloc.s  0xF
0x173b5c  ldloc.s  8
0x173b5e  ldloc.s  9
0x173b60  ldloc.2
0x173b61  ldloc.s  0xF
0x173b63  ldarg.3
0x173b64  call     bool Microsoft.Crm.ObjectModel.GoalUtil::IsGoalAttribMapped(bool metricType, int32 goalType, valuetype [mscorlib]System.Guid metricId, string goalAttribute, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x173b69  brfalse.s loc_173B7C
0x173b6b  ldc.i4   0x80044807
0x173b70  ldc.i4.0
0x173b71  newarr   [mscorlib]System.Object
0x173b76  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0x173b7b  throw
0x173b7c  ldarg.2
0x173b7d  brtrue.s loc_173B86
0x173b7f  ldstr    aUpdate_0// "UPDATE"
0x173b84  br.s     loc_173B8B
0x173b86  ldstr    aCreate_0// "CREATE"
0x173b8b  stloc.s  0xA
0x173b8d  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Now()
0x173b92  stloc.s  0xB
0x173b94  call     class Microsoft.Crm.ObjectModel.GoalEntityEventSource Microsoft.Crm.ObjectModel.GoalEntityEventSource::get_Instance()
0x173b99  ldloc.s  0xB
0x173b9b  ldarg.3
0x173b9c  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_OrganizationSettings()
0x173ba1  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings::get_OrganizationId()
0x173ba6  ldc.i4   0x2584
0x173bab  ldloc.s  0xA
0x173bad  callvirt instance void Microsoft.Crm.ObjectModel.GoalEntityEventSource::WriteCrudTelemetryEvent(valuetype [mscorlib]System.DateTime Timestamp, valuetype [mscorlib]System.Guid organizationId, int32 EntityTypeCode, string OperationType)
0x173bb2  ldloc.s  0xA
0x173bb4  ldstr    aCreate_0// "CREATE"
0x173bb9  call     bool [mscorlib]System.String::op_Equality(string, string)
0x173bbe  brfalse.s loc_173BE8
0x173bc0  call     class Microsoft.Crm.ObjectModel.GoalEntityEventSource Microsoft.Crm.ObjectModel.GoalEntityEventSource::get_Instance()
0x173bc5  ldloc.s  0xB
0x173bc7  ldarg.3
0x173bc8  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_OrganizationSettings()
0x173bcd  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings::get_OrganizationId()
0x173bd2  ldloc.2
0x173bd3  ldarg.1
0x173bd4  ldstr    aSourceentity// "sourceentity"
0x173bd9  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x173bde  unbox.any [mscorlib]System.Int32
0x173be3  callvirt instance void Microsoft.Crm.ObjectModel.GoalEntityEventSource::WriteRollupFieldEnityTelemetryEvent(valuetype [mscorlib]System.DateTime Timestamp, valuetype [mscorlib]System.Guid organizationId, valuetype [mscorlib]System.Guid MetricID, int32 SourceRecordType)
0x173be8  ret
```
