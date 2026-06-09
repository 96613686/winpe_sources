# Microsoft.Crm.Service.ObjectModel.SLAService::AddDependency

- ea: `0xa9a0`
- end: `0xabff`
- name: `Microsoft.Crm.Service.ObjectModel.SLAService::AddDependency`
- size: `607`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x9cc0`

## callees

- `0x9c30`
- `0xa9a0`

## string_xrefs

- `0xaa3a`: `componenttype`
- `0xab34`: `componenttype`
- `0xab7a`: `issharedcomponent`
- `0xabbf`: `dependentcomponentnodeid`
- `0xabe4`: `requiredcomponentnodeid`

## pseudocode

```c

```

## disassembly

```asm
0xa9a0  ldarg.1
0xa9a1  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfoCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Attributes()
0xa9a6  ldstr    aApplicablefrom// "applicablefrom"
0xa9ab  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfo [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfoCollection::get_Item(string)
0xa9b0  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfo::get_Value()
0xa9b5  callvirt instance string [mscorlib]System.Object::ToString()
0xa9ba  stloc.0
0xa9bb  ldarg.1
0xa9bc  ldarg.2
0xa9bd  call     string Microsoft.Crm.Service.ObjectModel.SLAItemService::GetApplicableEntityName(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity slaEntity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0xa9c2  stloc.1
0xa9c3  ldarg.2
0xa9c4  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xa9c9  ldloc.1
0xa9ca  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::TryGetEntity(string)
0xa9cf  stloc.2
0xa9d0  ldloc.2
0xa9d1  ldstr    aApplicableenti// "applicableEntityMetadata"
0xa9d6  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0xa9db  ldloc.2
0xa9dc  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IAttributeMetadataCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_AttributesByName()
0xa9e1  ldloc.0
0xa9e2  callvirt instance bool class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IMetadataHashtable`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata>::ContainsKey(object)
0xa9e7  brfalse.s loc_A9F7
0xa9e9  ldloc.2
0xa9ea  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IAttributeMetadataCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_AttributesByName()
0xa9ef  ldloc.0
0xa9f0  callvirt instance var<u1> class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IMetadataHashtable`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata>::get_Item(!!T0)
0xa9f5  brtrue.s loc_AA02
0xa9f7  ldstr    aFailedToAddSla// "Failed to add SLA dependency on Applica"...
0xa9fc  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0xaa01  throw
0xaa02  ldloc.2
0xaa03  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IAttributeMetadataCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_AttributesByName()
0xaa08  ldloc.0
0xaa09  callvirt instance var<u1> class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IMetadataHashtable`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata>::get_Item(!!T0)
0xaa0e  stloc.3
0xaa0f  newobj   instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.DependencyNodeService::.ctor()
0xaa14  stloc.s  4
0xaa16  ldstr    aDependencynode// "DependencyNode"
0xaa1b  ldarg.2
0xaa1c  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext)
0xaa21  stloc.s  5
0xaa23  ldloc.s  5
0xaa25  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0xaa2a  ldc.i4.3
0xaa2b  newarr   [mscorlib]System.String
0xaa30  dup
0xaa31  ldc.i4.0
0xaa32  ldstr    aDependencynode_0// "dependencynodeid"
0xaa37  stelem.ref
0xaa38  dup
0xaa39  ldc.i4.1
0xaa3a  ldstr    aComponenttype// "componenttype"
0xaa3f  stelem.ref
0xaa40  dup
0xaa41  ldc.i4.2
0xaa42  ldstr    aObjectid// "objectid"
0xaa47  stelem.ref
0xaa48  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumns(string[])
0xaa4d  ldloc.s  5
0xaa4f  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0xaa54  ldstr    aObjectid// "objectid"
0xaa59  ldc.i4.0
0xaa5a  ldloc.3
0xaa5b  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_Id()
0xaa60  box      [mscorlib]System.Guid
0xaa65  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0xaa6a  pop
0xaa6b  ldloc.s  5
0xaa6d  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.TopExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Top()
0xaa72  ldc.i4.1
0xaa73  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.TopExpression::set_Count(int32)
0xaa78  ldloc.s  4
0xaa7a  ldloc.s  5
0xaa7c  ldarg.2
0xaa7d  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::RetrieveMultiple(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0xaa82  stloc.s  6
0xaa84  ldloc.s  6
0xaa86  callvirt instance int32 [mscorlib]System.Collections.CollectionBase::get_Count()
0xaa8b  brfalse  loc_ABFE
0xaa90  ldloca.s 7
0xaa92  ldloc.s  6
0xaa94  ldc.i4.0
0xaa95  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection::get_Item(int32)
0xaa9a  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfoCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Attributes()
0xaa9f  ldstr    aDependencynode_0// "dependencynodeid"
0xaaa4  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfo [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfoCollection::get_Item(string)
0xaaa9  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfo::get_Value()
0xaaae  callvirt instance string [mscorlib]System.Object::ToString()
0xaab3  call     instance void [mscorlib]System.Guid::.ctor(string)
0xaab8  call     valuetype [mscorlib]System.Guid [mscorlib]System.Guid::NewGuid()
0xaabd  stloc.s  8
0xaabf  ldarg.2
0xaac0  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0xaac5  newobj   instance void [Microsoft.Crm.Entities]Microsoft.Crm.Entities.DependencyNode::.ctor(valuetype [mscorlib]System.Guid)
0xaaca  stloc.s  9
0xaacc  ldloc.s  9
0xaace  ldstr    aBasesolutionid// "basesolutionid"
0xaad3  ldarg.2
0xaad4  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0xaad9  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.ISolutionContext::get_SolutionId()
0xaade  box      [mscorlib]System.Guid
0xaae3  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0xaae8  ldloc.s  9
0xaaea  ldstr    aTopsolutionid// "topsolutionid"
0xaaef  ldarg.2
0xaaf0  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0xaaf5  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.ISolutionContext::get_SolutionId()
0xaafa  box      [mscorlib]System.Guid
0xaaff  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0xab04  ldloc.s  9
0xab06  ldstr    aParentid// "parentid"
0xab0b  ldloca.s 0xB
0xab0d  initobj  [mscorlib]System.Guid
0xab13  ldloc.s  0xB
0xab15  box      [mscorlib]System.Guid
0xab1a  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0xab1f  ldloc.s  9
0xab21  ldstr    aDependencynode_0// "dependencynodeid"
0xab26  ldloc.s  8
0xab28  box      [mscorlib]System.Guid
0xab2d  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0xab32  ldloc.s  9
0xab34  ldstr    aComponenttype// "componenttype"
0xab39  ldc.i4   0x98
0xab3e  box      [mscorlib]System.Int32
0xab43  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0xab48  ldloc.s  9
0xab4a  ldstr    aObjectid// "objectid"
0xab4f  ldarg.1
0xab50  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfoCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Attributes()
0xab55  ldstr    aSlaid// "slaid"
0xab5a  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfo [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfoCollection::get_Item(string)
0xab5f  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfo::get_Value()
0xab64  callvirt instance string [mscorlib]System.Object::ToString()
0xab69  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0xab6e  box      [mscorlib]System.Guid
0xab73  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0xab78  ldloc.s  9
0xab7a  ldstr    aIssharedcompon// "issharedcomponent"
0xab7f  ldc.i4.0
0xab80  box      [mscorlib]System.Boolean
0xab85  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0xab8a  ldloc.s  4
0xab8c  ldloc.s  9
0xab8e  ldarg.2
0xab8f  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::Create(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0xab94  pop
0xab95  newobj   instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.DependencyService::.ctor()
0xab9a  ldarg.2
0xab9b  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0xaba0  newobj   instance void [Microsoft.Crm.Entities]Microsoft.Crm.Entities.Dependency::.ctor(valuetype [mscorlib]System.Guid)
0xaba5  stloc.s  0xA
0xaba7  ldloc.s  0xA
0xaba9  ldstr    aDependencyid// "dependencyid"
0xabae  call     valuetype [mscorlib]System.Guid [mscorlib]System.Guid::NewGuid()
0xabb3  box      [mscorlib]System.Guid
0xabb8  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0xabbd  ldloc.s  0xA
0xabbf  ldstr    aDependentcompo// "dependentcomponentnodeid"
0xabc4  ldloc.s  8
0xabc6  box      [mscorlib]System.Guid
0xabcb  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0xabd0  ldloc.s  0xA
0xabd2  ldstr    aDependencytype// "dependencytype"
0xabd7  ldc.i4.2
0xabd8  box      [mscorlib]System.Int32
0xabdd  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0xabe2  ldloc.s  0xA
0xabe4  ldstr    aRequiredcompon// "requiredcomponentnodeid"
0xabe9  ldloc.s  7
0xabeb  box      [mscorlib]System.Guid
0xabf0  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0xabf5  ldloc.s  0xA
0xabf7  ldarg.2
0xabf8  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::Create(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0xabfd  pop
0xabfe  ret
```
