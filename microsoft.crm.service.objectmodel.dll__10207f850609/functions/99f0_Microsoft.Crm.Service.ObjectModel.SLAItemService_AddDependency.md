# Microsoft.Crm.Service.ObjectModel.SLAItemService::AddDependency

- ea: `0x99f0`
- end: `0x9c2e`
- name: `Microsoft.Crm.Service.ObjectModel.SLAItemService::AddDependency`
- size: `574`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x9740`

## callees

- `0x9980`
- `0x99f0`
- `0x9c30`

## string_xrefs

- `0x9a6b`: `componenttype`
- `0x9b64`: `componenttype`
- `0x9baa`: `issharedcomponent`
- `0x9bee`: `dependentcomponentnodeid`
- `0x9c13`: `requiredcomponentnodeid`

## pseudocode

```c

```

## disassembly

```asm
0x99f0  ldarg.1
0x99f1  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfoCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Attributes()
0x99f6  ldstr    aRelatedfield// "relatedfield"
0x99fb  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfo [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfoCollection::get_Item(string)
0x9a00  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfo::get_Value()
0x9a05  callvirt instance string [mscorlib]System.Object::ToString()
0x9a0a  stloc.0
0x9a0b  ldarg.0
0x9a0c  ldarg.1
0x9a0d  ldstr    aSlaid// "slaid"
0x9a12  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x9a17  unbox.any [mscorlib]System.Guid
0x9a1c  ldarg.2
0x9a1d  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity Microsoft.Crm.Service.ObjectModel.SLAItemService::RetrieveSLARecord(valuetype [mscorlib]System.Guid id, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x9a22  ldarg.2
0x9a23  call     string Microsoft.Crm.Service.ObjectModel.SLAItemService::GetApplicableEntityName(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity slaEntity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x9a28  stloc.1
0x9a29  ldarg.2
0x9a2a  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x9a2f  ldloc.1
0x9a30  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::TryGetEntity(string)
0x9a35  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IAttributeMetadataCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_AttributesByName()
0x9a3a  ldloc.0
0x9a3b  callvirt instance var<u1> class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IMetadataHashtable`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata>::get_Item(!!T0)
0x9a40  stloc.2
0x9a41  newobj   instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.DependencyNodeService::.ctor()
0x9a46  stloc.3
0x9a47  ldstr    aDependencynode// "DependencyNode"
0x9a4c  ldarg.2
0x9a4d  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext)
0x9a52  stloc.s  4
0x9a54  ldloc.s  4
0x9a56  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x9a5b  ldc.i4.3
0x9a5c  newarr   [mscorlib]System.String
0x9a61  dup
0x9a62  ldc.i4.0
0x9a63  ldstr    aDependencynode_0// "dependencynodeid"
0x9a68  stelem.ref
0x9a69  dup
0x9a6a  ldc.i4.1
0x9a6b  ldstr    aComponenttype// "componenttype"
0x9a70  stelem.ref
0x9a71  dup
0x9a72  ldc.i4.2
0x9a73  ldstr    aObjectid// "objectid"
0x9a78  stelem.ref
0x9a79  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumns(string[])
0x9a7e  ldloc.s  4
0x9a80  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x9a85  ldstr    aObjectid// "objectid"
0x9a8a  ldc.i4.0
0x9a8b  ldloc.2
0x9a8c  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_Id()
0x9a91  box      [mscorlib]System.Guid
0x9a96  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x9a9b  pop
0x9a9c  ldloc.s  4
0x9a9e  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.TopExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Top()
0x9aa3  ldc.i4.1
0x9aa4  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.TopExpression::set_Count(int32)
0x9aa9  ldloc.3
0x9aaa  ldloc.s  4
0x9aac  ldarg.2
0x9aad  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::RetrieveMultiple(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x9ab2  stloc.s  5
0x9ab4  ldloc.s  5
0x9ab6  callvirt instance int32 [mscorlib]System.Collections.CollectionBase::get_Count()
0x9abb  brfalse  loc_9C2D
0x9ac0  ldloca.s 6
0x9ac2  ldloc.s  5
0x9ac4  ldc.i4.0
0x9ac5  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection::get_Item(int32)
0x9aca  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfoCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Attributes()
0x9acf  ldstr    aDependencynode_0// "dependencynodeid"
0x9ad4  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfo [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfoCollection::get_Item(string)
0x9ad9  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfo::get_Value()
0x9ade  callvirt instance string [mscorlib]System.Object::ToString()
0x9ae3  call     instance void [mscorlib]System.Guid::.ctor(string)
0x9ae8  call     valuetype [mscorlib]System.Guid [mscorlib]System.Guid::NewGuid()
0x9aed  stloc.s  7
0x9aef  ldarg.2
0x9af0  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x9af5  newobj   instance void [Microsoft.Crm.Entities]Microsoft.Crm.Entities.DependencyNode::.ctor(valuetype [mscorlib]System.Guid)
0x9afa  stloc.s  8
0x9afc  ldloc.s  8
0x9afe  ldstr    aBasesolutionid// "basesolutionid"
0x9b03  ldarg.2
0x9b04  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x9b09  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.ISolutionContext::get_SolutionId()
0x9b0e  box      [mscorlib]System.Guid
0x9b13  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x9b18  ldloc.s  8
0x9b1a  ldstr    aTopsolutionid// "topsolutionid"
0x9b1f  ldarg.2
0x9b20  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x9b25  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.ISolutionContext::get_SolutionId()
0x9b2a  box      [mscorlib]System.Guid
0x9b2f  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x9b34  ldloc.s  8
0x9b36  ldstr    aParentid// "parentid"
0x9b3b  ldloca.s 0xA
0x9b3d  initobj  [mscorlib]System.Guid
0x9b43  ldloc.s  0xA
0x9b45  box      [mscorlib]System.Guid
0x9b4a  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x9b4f  ldloc.s  8
0x9b51  ldstr    aDependencynode_0// "dependencynodeid"
0x9b56  ldloc.s  7
0x9b58  box      [mscorlib]System.Guid
0x9b5d  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x9b62  ldloc.s  8
0x9b64  ldstr    aComponenttype// "componenttype"
0x9b69  ldc.i4   0x99
0x9b6e  box      [mscorlib]System.Int32
0x9b73  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x9b78  ldloc.s  8
0x9b7a  ldstr    aObjectid// "objectid"
0x9b7f  ldarg.1
0x9b80  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfoCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Attributes()
0x9b85  ldstr    aSlaitemid// "slaitemid"
0x9b8a  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfo [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfoCollection::get_Item(string)
0x9b8f  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfo::get_Value()
0x9b94  callvirt instance string [mscorlib]System.Object::ToString()
0x9b99  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x9b9e  box      [mscorlib]System.Guid
0x9ba3  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x9ba8  ldloc.s  8
0x9baa  ldstr    aIssharedcompon// "issharedcomponent"
0x9baf  ldc.i4.0
0x9bb0  box      [mscorlib]System.Boolean
0x9bb5  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x9bba  ldloc.3
0x9bbb  ldloc.s  8
0x9bbd  ldarg.2
0x9bbe  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::Create(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x9bc3  pop
0x9bc4  newobj   instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.DependencyService::.ctor()
0x9bc9  ldarg.2
0x9bca  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x9bcf  newobj   instance void [Microsoft.Crm.Entities]Microsoft.Crm.Entities.Dependency::.ctor(valuetype [mscorlib]System.Guid)
0x9bd4  stloc.s  9
0x9bd6  ldloc.s  9
0x9bd8  ldstr    aDependencyid// "dependencyid"
0x9bdd  call     valuetype [mscorlib]System.Guid [mscorlib]System.Guid::NewGuid()
0x9be2  box      [mscorlib]System.Guid
0x9be7  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x9bec  ldloc.s  9
0x9bee  ldstr    aDependentcompo// "dependentcomponentnodeid"
0x9bf3  ldloc.s  7
0x9bf5  box      [mscorlib]System.Guid
0x9bfa  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x9bff  ldloc.s  9
0x9c01  ldstr    aDependencytype// "dependencytype"
0x9c06  ldc.i4.2
0x9c07  box      [mscorlib]System.Int32
0x9c0c  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x9c11  ldloc.s  9
0x9c13  ldstr    aRequiredcompon// "requiredcomponentnodeid"
0x9c18  ldloc.s  6
0x9c1a  box      [mscorlib]System.Guid
0x9c1f  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x9c24  ldloc.s  9
0x9c26  ldarg.2
0x9c27  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::Create(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x9c2c  pop
0x9c2d  ret
```
