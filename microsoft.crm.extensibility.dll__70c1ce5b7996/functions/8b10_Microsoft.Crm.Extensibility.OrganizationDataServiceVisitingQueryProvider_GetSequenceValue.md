# Microsoft.Crm.Extensibility.OrganizationDataServiceVisitingQueryProvider::GetSequenceValue

- ea: `0x8b10`
- end: `0x8d60`
- name: `Microsoft.Crm.Extensibility.OrganizationDataServiceVisitingQueryProvider::GetSequenceValue`
- size: `592`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callees

- `0x6e00`
- `0x8b10`
- `0x9be0`
- `0x9ca0`
- `0x9d10`
- `0x9d90`
- `0x9e10`
- `0x9e20`

## pseudocode

```c

```

## disassembly

```asm
0x8b10  ldarg.1
0x8b11  ldstr    aValue// "value"
0x8b16  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x8b1b  ldarg.2
0x8b1c  ldstr    aProperty// "property"
0x8b21  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x8b26  ldarg.1
0x8b27  isinst   [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity
0x8b2c  brfalse  loc_8D5E
0x8b31  ldarg.2
0x8b32  callvirt instance class [System.Data.Services]System.Data.Services.Providers.ResourceType [System.Data.Services]System.Data.Services.Providers.ResourceProperty::get_ResourceType()
0x8b37  callvirt instance object [System.Data.Services]System.Data.Services.Providers.ResourceType::get_CustomState()
0x8b3c  isinst   [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata
0x8b41  stloc.0
0x8b42  ldloc.0
0x8b43  brfalse  loc_8D5E
0x8b48  ldloc.0
0x8b49  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0x8b4e  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::.ctor(string)
0x8b53  stloc.1
0x8b54  ldarg.0
0x8b55  ldarg.2
0x8b56  call     instance class [mscorlib]System.Tuple`3<class [System.Data.Services]System.Data.Services.Providers.ResourceAssociationSet, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationship, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityRole> Microsoft.Crm.Extensibility.OrganizationDataServiceVisitingQueryProvider::GetAssocationInformation(class [System.Data.Services]System.Data.Services.Providers.ResourceProperty property)
0x8b5b  stloc.2
0x8b5c  ldloc.2
0x8b5d  ldstr    aAssociationinf// "associationInfo"
0x8b62  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x8b67  ldloc.2
0x8b68  callvirt instance var<u1> class [mscorlib]System.Tuple`3<class [System.Data.Services]System.Data.Services.Providers.ResourceAssociationSet, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationship, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityRole>::get_Item2()
0x8b6d  stloc.3
0x8b6e  ldloc.3
0x8b6f  isinst   [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OneToManyEntityRelationship
0x8b74  stloc.s  4
0x8b76  ldloc.s  4
0x8b78  brfalse.s loc_8BB5
0x8b7a  ldloc.1
0x8b7b  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::get_Criteria()
0x8b80  ldloc.s  4
0x8b82  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Relationship [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OneToManyEntityRelationship::get_Relationship()
0x8b87  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Relationship::get_ReferencingAttribute()
0x8b8c  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_LogicalName()
0x8b91  ldc.i4.0
0x8b92  ldc.i4.1
0x8b93  newarr   [mscorlib]System.Object
0x8b98  dup
0x8b99  ldc.i4.0
0x8b9a  ldarg.1
0x8b9b  castclass [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity
0x8ba0  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Id()
0x8ba5  box      [mscorlib]System.Guid
0x8baa  stelem.ref
0x8bab  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object[])
0x8bb0  br       loc_8D17
0x8bb5  ldloc.3
0x8bb6  isinst   [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ManyToManyEntityRelationship
0x8bbb  stloc.s  5
0x8bbd  ldloc.s  5
0x8bbf  ldstr    aManytomanyrela// "manyToManyRelationship"
0x8bc4  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x8bc9  ldloc.s  5
0x8bcb  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IEntityRelationshipRoleCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ManyToManyEntityRelationship::get_AssociationEntityRelationshipRoles()
0x8bd0  callvirt instance int32 class [mscorlib]System.Collections.Generic.ICollection`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationshipRole>::get_Count()
0x8bd5  ldc.i4.2
0x8bd6  ceq
0x8bd8  ldstr    aAssociationent// "AssociationEntityRelationshipRoles coun"...
0x8bdd  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x8be2  ldloc.s  5
0x8be4  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IEntityRelationshipRoleCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ManyToManyEntityRelationship::get_AssociationEntityRelationshipRoles()
0x8be9  ldc.i4.0
0x8bea  callvirt instance var<u1> class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IMetadataCollection`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationshipRole>::get_Item(!!T0)
0x8bef  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationshipRole::get_EntityId()
0x8bf4  ldloc.s  5
0x8bf6  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IEntityRelationshipRoleCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ManyToManyEntityRelationship::get_AssociationEntityRelationshipRoles()
0x8bfb  ldc.i4.1
0x8bfc  callvirt instance var<u1> class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IMetadataCollection`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationshipRole>::get_Item(!!T0)
0x8c01  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationshipRole::get_EntityId()
0x8c06  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x8c0b  ldnull
0x8c0c  stloc.s  6
0x8c0e  ldnull
0x8c0f  stloc.s  7
0x8c11  brfalse.s loc_8C3A
0x8c13  ldarg.0
0x8c14  ldloc.s  5
0x8c16  ldloc.2
0x8c17  callvirt instance var<u1> class [mscorlib]System.Tuple`3<class [System.Data.Services]System.Data.Services.Providers.ResourceAssociationSet, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationship, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityRole>::get_Item3()
0x8c1c  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Relationship Microsoft.Crm.Extensibility.OrganizationDataServiceVisitingQueryProvider::GetIntesectRelationship(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ManyToManyEntityRelationship entityRelationship, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityRole role)
0x8c21  stloc.s  6
0x8c23  ldarg.0
0x8c24  ldloc.s  5
0x8c26  ldloc.2
0x8c27  callvirt instance var<u1> class [mscorlib]System.Tuple`3<class [System.Data.Services]System.Data.Services.Providers.ResourceAssociationSet, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationship, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityRole>::get_Item3()
0x8c2c  call     valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityRole Microsoft.Crm.Extensibility.OrganizationDataServiceVisitingQueryProvider::GetOtherEntityRole(valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityRole role)
0x8c31  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Relationship Microsoft.Crm.Extensibility.OrganizationDataServiceVisitingQueryProvider::GetIntesectRelationship(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ManyToManyEntityRelationship entityRelationship, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityRole role)
0x8c36  stloc.s  7
0x8c38  br.s     loc_8C5C
0x8c3a  ldarg.0
0x8c3b  ldloc.s  5
0x8c3d  ldloc.1
0x8c3e  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::get_EntityName()
0x8c43  ldc.i4.1
0x8c44  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Relationship Microsoft.Crm.Extensibility.OrganizationDataServiceVisitingQueryProvider::GetIntesectRelationship(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ManyToManyEntityRelationship entityRelationship, string entityName, bool withEntity)
0x8c49  stloc.s  6
0x8c4b  ldarg.0
0x8c4c  ldloc.s  5
0x8c4e  ldloc.1
0x8c4f  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::get_EntityName()
0x8c54  ldc.i4.0
0x8c55  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Relationship Microsoft.Crm.Extensibility.OrganizationDataServiceVisitingQueryProvider::GetIntesectRelationship(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ManyToManyEntityRelationship entityRelationship, string entityName, bool withEntity)
0x8c5a  stloc.s  7
0x8c5c  ldloc.s  6
0x8c5e  ldstr    aRelationship1// "relationship1"
0x8c63  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x8c68  ldloc.s  7
0x8c6a  ldstr    aRelationship2// "relationship2"
0x8c6f  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x8c74  ldarg.0
0x8c75  ldloc.s  6
0x8c77  ldloc.1
0x8c78  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::get_EntityName()
0x8c7d  call     instance string Microsoft.Crm.Extensibility.OrganizationDataServiceVisitingQueryProvider::GetRelationshipOtherEntityName(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Relationship relationship, string entityName)
0x8c82  stloc.s  8
0x8c84  ldloc.1
0x8c85  ldloc.s  8
0x8c87  ldarg.0
0x8c88  ldloc.s  6
0x8c8a  ldloc.1
0x8c8b  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::get_EntityName()
0x8c90  call     instance string Microsoft.Crm.Extensibility.OrganizationDataServiceVisitingQueryProvider::GetRelationshipAttributeName(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Relationship relationship, string entityName)
0x8c95  ldarg.0
0x8c96  ldloc.s  6
0x8c98  ldloc.s  8
0x8c9a  call     instance string Microsoft.Crm.Extensibility.OrganizationDataServiceVisitingQueryProvider::GetRelationshipAttributeName(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Relationship relationship, string entityName)
0x8c9f  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.LinkEntity [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::AddLink(string, string, string)
0x8ca4  stloc.s  9
0x8ca6  ldarg.0
0x8ca7  ldloc.s  7
0x8ca9  ldloc.s  8
0x8cab  call     instance string Microsoft.Crm.Extensibility.OrganizationDataServiceVisitingQueryProvider::GetRelationshipOtherEntityName(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Relationship relationship, string entityName)
0x8cb0  stloc.s  0xA
0x8cb2  ldloc.s  8
0x8cb4  ldloc.s  0xA
0x8cb6  ldarg.0
0x8cb7  ldloc.s  7
0x8cb9  ldloc.s  8
0x8cbb  call     instance string Microsoft.Crm.Extensibility.OrganizationDataServiceVisitingQueryProvider::GetRelationshipAttributeName(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Relationship relationship, string entityName)
0x8cc0  ldarg.0
0x8cc1  ldloc.s  7
0x8cc3  ldloc.s  0xA
0x8cc5  call     instance string Microsoft.Crm.Extensibility.OrganizationDataServiceVisitingQueryProvider::GetRelationshipAttributeName(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Relationship relationship, string entityName)
0x8cca  ldc.i4.0
0x8ccb  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.LinkEntity::.ctor(string, string, string, string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.JoinOperator)
0x8cd0  stloc.s  0xB
0x8cd2  ldloc.s  0xB
0x8cd4  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.LinkEntity::get_LinkCriteria()
0x8cd9  ldloc.s  7
0x8cdb  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Relationship::get_ReferencedEntity()
0x8ce0  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_PrimaryKey()
0x8ce5  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_LogicalName()
0x8cea  ldc.i4.0
0x8ceb  ldc.i4.1
0x8cec  newarr   [mscorlib]System.Object
0x8cf1  dup
0x8cf2  ldc.i4.0
0x8cf3  ldarg.1
0x8cf4  castclass [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity
0x8cf9  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Id()
0x8cfe  box      [mscorlib]System.Guid
0x8d03  stelem.ref
0x8d04  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object[])
0x8d09  ldloc.s  9
0x8d0b  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.LinkEntity> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.LinkEntity::get_LinkEntities()
0x8d10  ldloc.s  0xB
0x8d12  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.LinkEntity>::Add(var<u1>)
0x8d17  ldloc.1
0x8d18  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::get_ColumnSet()
0x8d1d  ldc.i4.1
0x8d1e  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet::set_AllColumns(bool)
0x8d23  ldloc.1
0x8d24  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.OrderExpression> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::get_Orders()
0x8d29  ldloc.0
0x8d2a  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_PrimaryKey()
0x8d2f  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_LogicalName()
0x8d34  ldc.i4.0
0x8d35  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.OrderExpression::.ctor(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.OrderType)
0x8d3a  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.OrderExpression>::Add(var<u1>)
0x8d3f  ldloc.1
0x8d40  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.PagingInfo::.ctor()
0x8d45  dup
0x8d46  call     int32 Microsoft.Crm.Extensibility.OrganizationDataService::get_PageSize()
0x8d4b  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.PagingInfo::set_Count(int32)
0x8d50  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::set_PageInfo(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.PagingInfo)
0x8d55  ldarg.0
0x8d56  ldloc.1
0x8d57  ldc.i4.0
0x8d58  call     T0x2B000038
0x8d5d  ret
0x8d5e  ldnull
0x8d5f  ret
```
