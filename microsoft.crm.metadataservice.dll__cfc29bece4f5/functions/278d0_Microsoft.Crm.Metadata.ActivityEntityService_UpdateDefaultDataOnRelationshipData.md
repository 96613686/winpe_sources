# Microsoft.Crm.Metadata.ActivityEntityService::UpdateDefaultDataOnRelationshipData

- ea: `0x278d0`
- end: `0x2824a`
- name: `Microsoft.Crm.Metadata.ActivityEntityService::UpdateDefaultDataOnRelationshipData`
- size: `2426`
- prototype: ``
- caller_count: `1`
- callee_count: `17`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x276c0`

## callees

- `0x278d0`
- `0x28250`
- `0x283e0`
- `0x28400`
- `0x28440`
- `0x28a90`
- `0x387f0`
- `0x52e20`
- `0x55de0`
- `0x56130`
- `0x56440`
- `0x56490`
- `0x565f0`
- `0x566d0`
- `0x59340`
- `0x65f40`
- `0x65f70`

## string_xrefs

- `0x27f00`: `cascadedelete`
- `0x27fec`: `cascadedelete`
- `0x27bcb`: `service`
- `0x27bde`: `serviceid`
- `0x27fdc`: `serviceid`
- `0x27e00`: `entityrelationshiprelationshipsid`

## pseudocode

```c

```

## disassembly

```asm
0x278d0  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, string>::.ctor()
0x278d5  stloc.0
0x278d6  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, string>::.ctor()
0x278db  stloc.1
0x278dc  ldarg.1
0x278dd  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.EntityMetadataDefinition::get_Entity()
0x278e2  ldstr    aLogicalname// "logicalname"
0x278e7  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x278ec  castclass [mscorlib]System.String
0x278f1  stloc.2
0x278f2  ldarg.1
0x278f3  ldstr    aRelationship_0// "Relationship"
0x278f8  ldloca.s 3
0x278fa  callvirt instance bool [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.EntityMetadataDefinition::TryRetrieveRelatedDataSet(string, class [mscorlib]System.Collections.Generic.IDictionary`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity>&)
0x278ff  brfalse.s loc_27909
0x27901  ldloc.3
0x27902  callvirt instance int32 class [mscorlib]System.Collections.Generic.ICollection`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity>>::get_Count()
0x27907  brtrue.s loc_2790A
0x27909  ret
0x2790a  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::.ctor()
0x2790f  stloc.s  4
0x27911  ldloc.3
0x27912  callvirt instance class [mscorlib]System.Collections.Generic.ICollection`1<var<u1>> class [mscorlib]System.Collections.Generic.IDictionary`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity>::get_Values()
0x27917  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity>::GetEnumerator()
0x2791c  stloc.s  0xE
0x2791e  br.s     loc_27941
0x27920  ldloc.s  0xE
0x27922  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity>::get_Current()
0x27927  stloc.s  0xF
0x27929  ldloc.s  4
0x2792b  ldloc.s  0xF
0x2792d  ldstr    aReferencedenti// "referencedentityid"
0x27932  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x27937  unbox.any [mscorlib]System.Guid
0x2793c  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::Add(var<u1>)
0x27941  ldloc.s  0xE
0x27943  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x27948  brtrue.s loc_27920
0x2794a  leave.s  loc_27958
0x2794c  ldloc.s  0xE
0x2794e  brfalse.s loc_27957
0x27950  ldloc.s  0xE
0x27952  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x27957  endfinally
0x27958  ldstr    aEntity_0// "Entity"
0x2795d  ldarg.2
0x2795e  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleQueryExpression::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x27963  stloc.s  5
0x27965  ldloc.s  5
0x27967  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.ColumnCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleQueryExpression::get_Columns()
0x2796c  ldstr    aLogicalname// "logicalname"
0x27971  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.ColumnCollection::AddColumn(string)
0x27976  ldloc.s  5
0x27978  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.ColumnCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleQueryExpression::get_Columns()
0x2797d  ldstr    aOwnershiptypem// "ownershiptypemask"
0x27982  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.ColumnCollection::AddColumn(string)
0x27987  ldloc.s  5
0x27989  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleConditionCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleQueryExpression::get_Conditions()
0x2798e  ldstr    aEntityid// "entityid"
0x27993  ldc.i4.2
0x27994  ldloc.s  4
0x27996  callvirt instance var<u1>[] class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::ToArray()
0x2799b  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleConditionCollection::AddCondition(string, valuetype [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleConditionOperator, class [mscorlib]System.Array)
0x279a0  call     class [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataQueryHelper [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataQueryHelper::get_Instance()
0x279a5  ldloc.s  5
0x279a7  ldarg.2
0x279a8  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x279ad  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntityCollection [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataQueryHelper::RetrieveMetadataEntities(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleQueryExpression, class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext)
0x279b2  dup
0x279b3  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity>::get_Count()
0x279b8  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, string>::.ctor(int32)
0x279bd  stloc.s  6
0x279bf  dup
0x279c0  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity>::get_Count()
0x279c5  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, int32>::.ctor(int32)
0x279ca  stloc.s  7
0x279cc  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity>::GetEnumerator()
0x279d1  stloc.s  0xE
0x279d3  br.s     loc_27A30
0x279d5  ldloc.s  0xE
0x279d7  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity>::get_Current()
0x279dc  stloc.s  0x10
0x279de  ldloc.s  6
0x279e0  ldloc.s  0x10
0x279e2  ldstr    aEntityid// "entityid"
0x279e7  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x279ec  unbox.any [mscorlib]System.Guid
0x279f1  ldloc.s  0x10
0x279f3  ldstr    aLogicalname// "logicalname"
0x279f8  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x279fd  castclass [mscorlib]System.String
0x27a02  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, string>::Add(var<u1>, !!T0)
0x27a07  ldloc.s  7
0x27a09  ldloc.s  0x10
0x27a0b  ldstr    aEntityid// "entityid"
0x27a10  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x27a15  unbox.any [mscorlib]System.Guid
0x27a1a  ldloc.s  0x10
0x27a1c  ldstr    aOwnershiptypem// "ownershiptypemask"
0x27a21  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x27a26  unbox.any [mscorlib]System.Int32
0x27a2b  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, int32>::Add(var<u1>, !!T0)
0x27a30  ldloc.s  0xE
0x27a32  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x27a37  brtrue.s loc_279D5
0x27a39  leave.s  loc_27A47
0x27a3b  ldloc.s  0xE
0x27a3d  brfalse.s loc_27A46
0x27a3f  ldloc.s  0xE
0x27a41  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x27a46  endfinally
0x27a47  ldarg.0
0x27a48  ldarg.2
0x27a49  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x27a4e  call     instance valuetype [mscorlib]System.Guid[] Microsoft.Crm.Metadata.ActivityEntityService::RetrieveMergeableEntityIds(class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext context)
0x27a53  stloc.s  8
0x27a55  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::.ctor()
0x27a5a  stloc.s  9
0x27a5c  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::.ctor()
0x27a61  stloc.s  0xA
0x27a63  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::.ctor()
0x27a68  stloc.s  0xB
0x27a6a  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::.ctor()
0x27a6f  stloc.s  0xC
0x27a71  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0x27a76  stloc.s  0xD
0x27a78  ldarg.2
0x27a79  newobj   instance void Microsoft.Crm.Metadata.EntityPropertiesBackCompatOverrider::.ctor(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x27a7e  ldarg.1
0x27a7f  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.EntityMetadataDefinition::get_Entity()
0x27a84  ldstr    aEntityid_1// "EntityId"
0x27a89  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x27a8e  callvirt instance string [mscorlib]System.Object::ToString()
0x27a93  call     instance class [mscorlib]System.Collections.Generic.List`1<string> Microsoft.Crm.Metadata.EntityPropertiesBackCompatOverrider::GetIgnoreListForRelationships(string entityId)
0x27a98  stloc.s  0xD
0x27a9a  ldloc.3
0x27a9b  callvirt instance class [mscorlib]System.Collections.Generic.ICollection`1<var<u1>> class [mscorlib]System.Collections.Generic.IDictionary`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity>::get_Values()
0x27aa0  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity>::GetEnumerator()
0x27aa5  stloc.s  0xE
0x27aa7  br       loc_2800C
0x27aac  ldloc.s  0xE
0x27aae  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity>::get_Current()
0x27ab3  stloc.s  0x11
0x27ab5  ldloc.s  0x11
0x27ab7  ldstr    aRelationshipid// "relationshipid"
0x27abc  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x27ac1  unbox.any [mscorlib]System.Guid
0x27ac6  stloc.s  0x12
0x27ac8  ldarg.1
0x27ac9  ldstr    aAttribute// "Attribute"
0x27ace  callvirt instance class [mscorlib]System.Collections.Generic.IDictionary`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity> [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.EntityMetadataDefinition::RetrieveRelatedDataSet(string)
0x27ad3  ldloc.s  0x11
0x27ad5  ldstr    aReferencingatt// "referencingattributeid"
0x27ada  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x27adf  unbox.any [mscorlib]System.Guid
0x27ae4  callvirt instance bool class [mscorlib]System.Collections.Generic.IDictionary`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity>::ContainsKey(var<u1>)
0x27ae9  brfalse.s loc_27B1F
0x27aeb  ldarg.1
0x27aec  ldstr    aAttribute// "Attribute"
0x27af1  callvirt instance class [mscorlib]System.Collections.Generic.IDictionary`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity> [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.EntityMetadataDefinition::RetrieveRelatedDataSet(string)
0x27af6  ldloc.s  0x11
0x27af8  ldstr    aReferencingatt// "referencingattributeid"
0x27afd  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x27b02  unbox.any [mscorlib]System.Guid
0x27b07  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IDictionary`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity>::get_Item(void)
0x27b0c  ldstr    aLogicalname// "logicalname"
0x27b11  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x27b16  castclass [mscorlib]System.String
0x27b1b  stloc.s  0x13
0x27b1d  br.s     loc_27B56
0x27b1f  call     class [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataQueryHelper [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataQueryHelper::get_Instance()
0x27b24  ldloc.s  0x11
0x27b26  ldstr    aReferencingatt// "referencingattributeid"
0x27b2b  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x27b30  unbox.any [mscorlib]System.Guid
0x27b35  ldstr    aAttribute// "Attribute"
0x27b3a  ldarg.2
0x27b3b  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x27b40  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataQueryHelper::RetrieveMetadataEntity(valuetype [mscorlib]System.Guid, string, class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext)
0x27b45  ldstr    aLogicalname// "logicalname"
0x27b4a  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x27b4f  castclass [mscorlib]System.String
0x27b54  stloc.s  0x13
0x27b56  ldstr    aRegardingobjec// "regardingobjectid"
0x27b5b  ldloc.s  0x13
0x27b5d  call     bool [mscorlib]System.String::op_Equality(string, string)
0x27b62  brfalse.s loc_27BA7
0x27b64  ldloc.s  0x11
0x27b66  ldstr    aName// "name"
0x27b6b  ldloc.s  6
0x27b6d  ldloc.s  0x11
0x27b6f  ldstr    aReferencedenti// "referencedentityid"
0x27b74  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x27b79  unbox.any [mscorlib]System.Guid
0x27b7e  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, string>::get_Item(void)
0x27b83  ldarg.1
0x27b84  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.EntityMetadataDefinition::get_Entity()
0x27b89  ldstr    aCollectionname// "collectionname"
0x27b8e  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x27b93  castclass [mscorlib]System.String
0x27b98  call     string Microsoft.Crm.Metadata.RelationshipService::CreateStandardRelationshipName(string referencedEntityLogicalName, string referencingEntityCollectionName)
0x27b9d  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::set_Item(string, object)
0x27ba2  br       loc_27C45
0x27ba7  ldloc.s  6
0x27ba9  ldloc.s  0x11
0x27bab  ldstr    aReferencedenti// "referencedentityid"
0x27bb0  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x27bb5  unbox.any [mscorlib]System.Guid
0x27bba  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, string>::get_Item(void)
0x27bbf  stloc.s  0x17
0x27bc1  ldarg.3
0x27bc2  brfalse.s loc_27C16
0x27bc4  ldloc.s  0x17
0x27bc6  callvirt instance string [mscorlib]System.String::ToLower()
0x27bcb  ldstr    aService// "service"
0x27bd0  callvirt instance bool [mscorlib]System.String::Equals(string)
0x27bd5  brfalse.s loc_27C16
0x27bd7  ldloc.s  0x13
0x27bd9  callvirt instance string [mscorlib]System.String::ToLower()
0x27bde  ldstr    aServiceid// "serviceid"
0x27be3  callvirt instance bool [mscorlib]System.String::Equals(string)
0x27be8  brfalse.s loc_27C16
0x27bea  ldloc.s  0x11
0x27bec  ldstr    aName// "name"
0x27bf1  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x27bf6  ldstr    a01// "{0}_{1}"
0x27bfb  ldc.i4.2
0x27bfc  newarr   [mscorlib]System.Object
0x27c01  dup
0x27c02  ldc.i4.0
0x27c03  ldloc.s  0x17
0x27c05  stelem.ref
0x27c06  dup
0x27c07  ldc.i4.1
0x27c08  ldloc.2
0x27c09  stelem.ref
0x27c0a  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x27c0f  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::set_Item(string, object)
0x27c14  br.s     loc_27C45
0x27c16  ldloc.s  0x11
0x27c18  ldstr    aName// "name"
0x27c1d  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x27c22  ldstr    a012_0// "{0}_{1}_{2}"
0x27c27  ldc.i4.3
0x27c28  newarr   [mscorlib]System.Object
0x27c2d  dup
0x27c2e  ldc.i4.0
0x27c2f  ldloc.2
0x27c30  stelem.ref
0x27c31  dup
0x27c32  ldc.i4.1
0x27c33  ldloc.s  0x17
0x27c35  stelem.ref
0x27c36  dup
0x27c37  ldc.i4.2
0x27c38  ldloc.s  0x13
0x27c3a  stelem.ref
0x27c3b  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x27c40  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::set_Item(string, object)
0x27c45  ldarg.2
0x27c46  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x27c4b  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.ISolutionContext::get_SolutionId()
0x27c50  ldarg.2
0x27c51  call     bool [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SolutionsHelper::IsInternalSolution(valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x27c56  brfalse.s loc_27C80
0x27c58  ldloc.s  0x11
0x27c5a  ldstr    aName// "name"
0x27c5f  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x27c64  castclass [mscorlib]System.String
0x27c69  ldloca.s 0x14
0x27c6b  call     bool Microsoft.Crm.MetadataService.RelationshipRenameMapper::TryGetCrmRelationshipName(string xrmRelationshipName, [out] string& crmRelationshipName)
0x27c70  brfalse.s loc_27C80
0x27c72  ldloc.s  0x11
0x27c74  ldstr    aName// "name"
0x27c79  ldloc.s  0x14
0x27c7b  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::set_Item(string, object)
0x27c80  ldarg.3
0x27c81  brfalse.s loc_27CBD
0x27c83  ldloc.s  0x11
0x27c85  ldstr    aName// "name"
0x27c8a  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x27c8f  callvirt instance string [mscorlib]System.Object::ToString()
0x27c94  call     bool Microsoft.Crm.MetadataService.RelationshipRenameMapper::IsRelationshipInBlackList(string xrmRelationshipName)
0x27c99  brtrue   loc_27D2C
0x27c9e  ldloc.s  0xD
0x27ca0  ldloc.s  0x11
0x27ca2  ldstr    aName// "name"
0x27ca7  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x27cac  callvirt instance string [mscorlib]System.Object::ToString()
0x27cb1  callvirt instance string [mscorlib]System.String::ToLower()
0x27cb6  callvirt instance bool class [mscorlib]System.Collections.Generic.List`1<string>::Contains(var<u1>)
0x27cbb  brtrue.s loc_27D2C
0x27cbd  ldarg.2
0x27cbe  call     bool Microsoft.Crm.Metadata.UpgradeHelper::IsInUpdateViaCreateDuringUpgradeContext(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x27cc3  brfalse.s loc_27D29
0x27cc5  ldarg.0
0x27cc6  ldloc.s  0x11
0x27cc8  ldstr    aReferencedenti// "referencedentityid"
0x27ccd  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x27cd2  unbox.any [mscorlib]System.Guid
  ... truncated ...
```
