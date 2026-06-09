# <>c__DisplayClass23_0::<CascadeMergeThroughOneToManyEntityRelationships>b__0

- ea: `0x8e140`
- end: `0x8e483`
- name: `<>c__DisplayClass23_0::<CascadeMergeThroughOneToManyEntityRelationships>b__0`
- size: `835`
- prototype: ``
- caller_count: `0`
- callee_count: `14`
- tags: `authz_impersonation`

## callees

- `0x13b10`
- `0x18520`
- `0x18540`
- `0x18800`
- `0x1ae30`
- `0x57c60`
- `0x57c70`
- `0x57d80`
- `0x57d90`
- `0x5eb60`
- `0x5faf0`
- `0x67cf0`
- `0x78470`
- `0x8e140`

## string_xrefs

- `0x8e447`: `Invalid CascadeLinkType: {0}`
- `0x8e361`: `address3_addressid`

## pseudocode

```c

```

## disassembly

```asm
0x8e140  ldarg.0
0x8e141  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata <>c__DisplayClass23_0::parentEntityMetadata
0x8e146  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IEntityRelationshipCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_ReferencesToEntityRelationships()
0x8e14b  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationship>::GetEnumerator()
0x8e150  stloc.0
0x8e151  br       loc_8E46B
0x8e156  ldloc.0
0x8e157  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationship>::get_Current()
0x8e15c  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OneToManyEntityRelationship
0x8e161  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Relationship [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OneToManyEntityRelationship::get_Relationship()
0x8e166  stloc.1
0x8e167  call     bool Microsoft.Crm.BusinessEntities.CascadeEngine::get_ReplicatedEntityCascadingOff()
0x8e16c  brfalse.s loc_8E185
0x8e16e  call     bool [Microsoft.Crm.Core]Microsoft.Crm.RegistryCache::get_IsOffline()
0x8e173  brfalse.s loc_8E185
0x8e175  ldloc.1
0x8e176  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Relationship::get_ReferencingEntity()
0x8e17b  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_IsReplicated()
0x8e180  brfalse  loc_8E46B
0x8e185  ldloc.1
0x8e186  ldc.i4.6
0x8e187  callvirt instance valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.CascadeLinkType [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Relationship::GetLinkType(valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.CascadeActionType)
0x8e18c  stloc.2
0x8e18d  ldloc.2
0x8e18e  switch   loc_8E46B, loc_8E1A8, loc_8E46B, loc_8E46B
0x8e1a3  br       loc_8E442
0x8e1a8  ldloc.1
0x8e1a9  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Relationship::get_ReferencingEntity()
0x8e1ae  stloc.3
0x8e1af  ldloc.3
0x8e1b0  ldc.i4.1
0x8e1b1  call     class Microsoft.Crm.BusinessEntities.BusinessProcessObject Microsoft.Crm.BusinessEntities.ServiceClassFactory::CreateInstance(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata metadata, bool returnBaseServiceIfNoServiceFound)
0x8e1b6  stloc.s  4
0x8e1b8  ldloc.3
0x8e1b9  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_PlatformName()
0x8e1be  ldarg.0
0x8e1bf  ldfld    class Microsoft.Crm.BusinessEntities.ExecutionContext <>c__DisplayClass23_0::context
0x8e1c4  newobj   instance void Microsoft.Crm.Query.EntityExpression::.ctor(string entityPlatformName, class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext userAndOrganizationContext)
0x8e1c9  stloc.s  5
0x8e1cb  ldloc.s  5
0x8e1cd  callvirt instance class Microsoft.Crm.Query.FilterExpression Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x8e1d2  ldloc.1
0x8e1d3  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Relationship::get_ReferencingColumnName()
0x8e1d8  ldc.i4.0
0x8e1d9  ldarg.0
0x8e1da  ldfld    valuetype [mscorlib]System.Guid <>c__DisplayClass23_0::subId
0x8e1df  box      [mscorlib]System.Guid
0x8e1e4  callvirt instance class Microsoft.Crm.Query.ConditionExpression Microsoft.Crm.Query.FilterExpression::AddCondition(string attributeName, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator conditionOperator, object value)
0x8e1e9  pop
0x8e1ea  ldloc.1
0x8e1eb  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Relationship::get_HasExtraConditions()
0x8e1f0  brfalse.s loc_8E22A
0x8e1f2  ldloc.1
0x8e1f3  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IRelationshipExtraConditionCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Relationship::get_ExtraConditions()
0x8e1f8  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.RelationshipExtraCondition>::GetEnumerator()
0x8e1fd  stloc.s  8
0x8e1ff  br.s     loc_8E213
0x8e201  ldloc.s  8
0x8e203  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.RelationshipExtraCondition>::get_Current()
0x8e208  stloc.s  9
0x8e20a  ldloc.s  5
0x8e20c  ldloc.s  9
0x8e20e  call     void Microsoft.Crm.BusinessEntities.ExtraConditionHandler::Check(class Microsoft.Crm.Query.EntityExpression expression, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.RelationshipExtraCondition condition)
0x8e213  ldloc.s  8
0x8e215  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x8e21a  brtrue.s loc_8E201
0x8e21c  leave.s  loc_8E22A
0x8e21e  ldloc.s  8
0x8e220  brfalse.s loc_8E229
0x8e222  ldloc.s  8
0x8e224  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x8e229  endfinally
0x8e22a  ldloc.3
0x8e22b  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_PrimaryKey()
0x8e230  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_PlatformName()
0x8e235  stloc.s  6
0x8e237  ldloc.s  5
0x8e239  callvirt instance class Microsoft.Crm.Query.ColumnSetExpression Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x8e23e  ldloc.s  6
0x8e240  callvirt instance void Microsoft.Crm.Query.ColumnSetExpression::AddColumn(string attributePlatformName)
0x8e245  ldloc.s  5
0x8e247  callvirt instance class Microsoft.Crm.Query.ColumnSetExpression Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x8e24c  ldloc.1
0x8e24d  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Relationship::get_ReferencingColumnName()
0x8e252  callvirt instance void Microsoft.Crm.Query.ColumnSetExpression::AddColumn(string attributePlatformName)
0x8e257  ldloc.s  4
0x8e259  callvirt instance string[] Microsoft.Crm.BusinessEntities.BusinessProcessObject::MergeSpecialColumns()
0x8e25e  stloc.s  7
0x8e260  ldloc.s  7
0x8e262  brfalse.s loc_8E2BF
0x8e264  ldloc.s  7
0x8e266  stloc.s  0xA
0x8e268  ldc.i4.0
0x8e269  stloc.s  0xB
0x8e26b  br.s     loc_8E2B7
0x8e26d  ldloc.s  0xA
0x8e26f  ldloc.s  0xB
0x8e271  ldelem.ref
0x8e272  stloc.s  0xC
0x8e274  ldloc.3
0x8e275  ldloc.s  0xC
0x8e277  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::TryGetAttribute(string)
0x8e27c  brtrue.s loc_8E2A3
0x8e27e  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x8e283  ldstr    aInvalidColumnN// "Invalid column name: {0}"
0x8e288  ldc.i4.1
0x8e289  newarr   [mscorlib]System.Object
0x8e28e  dup
0x8e28f  ldc.i4.0
0x8e290  ldloc.s  0xC
0x8e292  stelem.ref
0x8e293  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x8e298  ldc.i4   0x80048106
0x8e29d  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x8e2a2  throw
0x8e2a3  ldloc.s  5
0x8e2a5  callvirt instance class Microsoft.Crm.Query.ColumnSetExpression Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x8e2aa  ldloc.s  0xC
0x8e2ac  callvirt instance void Microsoft.Crm.Query.ColumnSetExpression::AddColumn(string attributePlatformName)
0x8e2b1  ldloc.s  0xB
0x8e2b3  ldc.i4.1
0x8e2b4  add
0x8e2b5  stloc.s  0xB
0x8e2b7  ldloc.s  0xB
0x8e2b9  ldloc.s  0xA
0x8e2bb  ldlen
0x8e2bc  conv.i4
0x8e2bd  blt.s    loc_8E26D
0x8e2bf  ldarg.0
0x8e2c0  ldfld    bool <>c__DisplayClass23_0::useSystemContext
0x8e2c5  brtrue.s loc_8E2CA
0x8e2c7  ldnull
0x8e2c8  br.s     loc_8E2D6
0x8e2ca  ldarg.0
0x8e2cb  ldfld    class Microsoft.Crm.BusinessEntities.ExecutionContext <>c__DisplayClass23_0::context
0x8e2d0  ldc.i4.1
0x8e2d1  newobj   instance void Microsoft.Crm.BusinessEntities.SystemUserContext::.ctor(class Microsoft.Crm.BusinessEntities.ExecutionContext context, bool switchAuditingInfo)
0x8e2d6  stloc.s  0xD
0x8e2d8  ldloc.s  4
0x8e2da  ldloc.s  5
0x8e2dc  ldarg.0
0x8e2dd  ldfld    class Microsoft.Crm.BusinessEntities.ExecutionContext <>c__DisplayClass23_0::context
0x8e2e2  ldc.i4.1
0x8e2e3  ldloc.1
0x8e2e4  callvirt instance valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.RelationshipTypes [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Relationship::get_RelationshipType()
0x8e2e9  ceq
0x8e2eb  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection Microsoft.Crm.BusinessEntities.BusinessProcessObject::MergeMultipleRetrieve(class Microsoft.Crm.Query.EntityExpression exp, class Microsoft.Crm.BusinessEntities.ExecutionContext context, bool IsAppend)
0x8e2f0  stloc.s  0xE
0x8e2f2  ldloc.s  0xE
0x8e2f4  callvirt instance int32 [mscorlib]System.Collections.CollectionBase::get_Count()
0x8e2f9  ldc.i4.0
0x8e2fa  ble.s    loc_8E323
0x8e2fc  ldloc.s  4
0x8e2fe  ldarg.0
0x8e2ff  ldfld    valuetype [mscorlib]System.Guid <>c__DisplayClass23_0::masterId
0x8e304  ldarg.0
0x8e305  ldfld    valuetype [mscorlib]System.Guid <>c__DisplayClass23_0::subId
0x8e30a  ldarg.0
0x8e30b  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata <>c__DisplayClass23_0::parentEntityMetadata
0x8e310  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_Code()
0x8e315  ldloc.s  0xE
0x8e317  ldloc.1
0x8e318  ldarg.0
0x8e319  ldfld    class Microsoft.Crm.BusinessEntities.ExecutionContext <>c__DisplayClass23_0::context
0x8e31e  callvirt instance void Microsoft.Crm.BusinessEntities.BusinessProcessObject::MergeSpecialHandler(valuetype [mscorlib]System.Guid masterId, valuetype [mscorlib]System.Guid subId, int32 parentOtc, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection entities, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Relationship relationship, class Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x8e323  ldloc.s  0xE
0x8e325  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.CollectionBase::GetEnumerator()
0x8e32a  stloc.s  0xF
0x8e32c  br       loc_8E413
0x8e331  ldloc.s  0xF
0x8e333  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x8e338  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity
0x8e33d  stloc.s  0x10
0x8e33f  ldloc.s  0x10
0x8e341  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_PrimaryKey()
0x8e346  unbox.any [mscorlib]System.Guid
0x8e34b  ldarg.0
0x8e34c  ldfld    valuetype [mscorlib]System.Guid <>c__DisplayClass23_0::masterId
0x8e351  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x8e356  brtrue   loc_8E413
0x8e35b  ldarg.0
0x8e35c  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata <>c__DisplayClass23_0::parentEntityMetadata
0x8e361  ldstr    aAddress3Addres// "address3_addressid"
0x8e366  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::TryGetAttribute(string)
0x8e36b  brtrue.s loc_8E370
0x8e36d  ldc.i4.2
0x8e36e  br.s     loc_8E371
0x8e370  ldc.i4.3
0x8e371  stloc.s  0x11
0x8e373  ldloc.s  0x10
0x8e375  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Metadata()
0x8e37a  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_Code()
0x8e37f  ldc.i4   0x42F
0x8e384  bne.un.s loc_8E39B
0x8e386  ldloc.s  0x10
0x8e388  ldstr    aAddressnumber// "addressnumber"
0x8e38d  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::GetAttributeValue(string)
0x8e392  unbox.any [mscorlib]System.Int32
0x8e397  ldloc.s  0x11
0x8e399  ble.s    loc_8E413
0x8e39b  ldloc.s  0x10
0x8e39d  ldloc.1
0x8e39e  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Relationship::get_ReferencingColumnName()
0x8e3a3  ldarg.0
0x8e3a4  ldfld    valuetype [mscorlib]System.Guid <>c__DisplayClass23_0::masterId
0x8e3a9  box      [mscorlib]System.Guid
0x8e3ae  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x8e3b3  ldloc.1
0x8e3b4  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Relationship::get_HasExtraConditions()
0x8e3b9  brfalse.s loc_8E404
0x8e3bb  ldloc.1
0x8e3bc  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IRelationshipExtraConditionCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Relationship::get_ExtraConditions()
0x8e3c1  callvirt instance int32 class [mscorlib]System.Collections.Generic.ICollection`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.RelationshipExtraCondition>::get_Count()
0x8e3c6  ldc.i4.1
0x8e3c7  ceq
0x8e3c9  ldstr    aOnlyOneExtraCo// "Only one extra condition per relationsh"...
0x8e3ce  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x8e3d3  ldloc.1
0x8e3d4  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IRelationshipExtraConditionCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Relationship::get_ExtraConditions()
0x8e3d9  ldc.i4.0
0x8e3da  callvirt instance var<u1> class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IMetadataCollection`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.RelationshipExtraCondition>::get_Item(!!T0)
0x8e3df  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.RelationshipExtraCondition::get_Attribute()
0x8e3e4  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_Name()
0x8e3e9  stloc.s  0x12
0x8e3eb  ldloc.s  0x10
0x8e3ed  ldloc.s  0x12
0x8e3ef  ldarg.0
0x8e3f0  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata <>c__DisplayClass23_0::parentEntityMetadata
0x8e3f5  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_Code()
0x8e3fa  box      [mscorlib]System.Int32
0x8e3ff  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x8e404  ldloc.s  4
0x8e406  ldloc.s  0x10
0x8e408  ldarg.0
0x8e409  ldfld    class Microsoft.Crm.BusinessEntities.ExecutionContext <>c__DisplayClass23_0::context
0x8e40e  callvirt instance void Microsoft.Crm.BusinessEntities.BusinessProcessObject::MergeUpdate(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity entity, class Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x8e413  ldloc.s  0xF
0x8e415  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x8e41a  brtrue   loc_8E331
0x8e41f  leave.s  loc_8E46B
0x8e421  ldloc.s  0xF
0x8e423  isinst   [mscorlib]System.IDisposable
0x8e428  stloc.s  0x13
0x8e42a  ldloc.s  0x13
0x8e42c  brfalse.s loc_8E435
0x8e42e  ldloc.s  0x13
0x8e430  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x8e435  endfinally
0x8e436  ldloc.s  0xD
0x8e438  brfalse.s loc_8E441
0x8e43a  ldloc.s  0xD
0x8e43c  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x8e441  endfinally
0x8e442  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x8e447  ldstr    aInvalidCascade// "Invalid CascadeLinkType: {0}"
0x8e44c  ldc.i4.1
0x8e44d  newarr   [mscorlib]System.Object
0x8e452  dup
0x8e453  ldc.i4.0
0x8e454  ldloc.2
0x8e455  box      [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.CascadeLinkType
0x8e45a  stelem.ref
0x8e45b  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x8e460  ldc.i4   0x80048102
0x8e465  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x8e46a  throw
0x8e46b  ldloc.0
0x8e46c  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x8e471  brtrue   loc_8E156
0x8e476  leave.s  loc_8E482
0x8e478  ldloc.0
0x8e479  brfalse.s loc_8E481
0x8e47b  ldloc.0
0x8e47c  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x8e481  endfinally
0x8e482  ret
```
