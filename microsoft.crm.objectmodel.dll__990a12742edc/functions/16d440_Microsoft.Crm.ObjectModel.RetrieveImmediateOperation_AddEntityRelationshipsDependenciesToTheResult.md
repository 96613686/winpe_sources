# Microsoft.Crm.ObjectModel.RetrieveImmediateOperation::AddEntityRelationshipsDependenciesToTheResult

- ea: `0x16d440`
- end: `0x16d760`
- name: `Microsoft.Crm.ObjectModel.RetrieveImmediateOperation::AddEntityRelationshipsDependenciesToTheResult`
- size: `800`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x16cf60`

## callees

- `0x16d3a0`
- `0x16d440`
- `0x16d760`
- `0x199860`
- `0x1b1650`

## string_xrefs

- `0x16d4dc`: `requiredcomponentobjectid`
- `0x16d546`: `requiredcomponentobjectid`
- `0x16d6bc`: `requiredcomponentobjectid`
- `0x16d499`: `requiredcomponenttype`
- `0x16d51c`: `requiredcomponenttype`
- `0x16d692`: `requiredcomponenttype`
- `0x16d4c9`: `dependentcomponentobjectid`
- `0x16d64a`: `dependentcomponentobjectid`
- `0x16d651`: `dependentcomponentobjectid`
- `0x16d4b1`: `dependentcomponenttype`
- `0x16d61a`: `dependentcomponenttype`
- `0x16d621`: `dependentcomponenttype`
- `0x16d632`: `dependentcomponentnodeid`
- `0x16d639`: `dependentcomponentnodeid`
- `0x16d52e`: `requiredcomponentnodeid`
- `0x16d6a4`: `requiredcomponentnodeid`
- `0x16d67a`: `dependentcomponentbasesolutionid`
- `0x16d681`: `dependentcomponentbasesolutionid`
- `0x16d662`: `dependentcomponentparentid`
- `0x16d669`: `dependentcomponentparentid`
- `0x16d571`: `requiredcomponentparentid`
- `0x16d57f`: `requiredcomponentparentid`
- `0x16d6ec`: `requiredcomponentparentid`
- `0x16d6fa`: `requiredcomponentparentid`
- `0x16d559`: `requiredcomponentbasesolutionid`
- `0x16d6d4`: `requiredcomponentbasesolutionid`

## pseudocode

```c

```

## disassembly

```asm
0x16d440  ldarg.0
0x16d441  call     instance valuetype Microsoft.Crm.ObjectModel.DependencyRetrievalDirections Microsoft.Crm.ObjectModel.RetrieveImmediateOperation::get_Direction()
0x16d446  ldc.i4.2
0x16d447  bne.un.s loc_16D44A
0x16d449  ret
0x16d44a  ldnull
0x16d44b  stloc.0
0x16d44c  ldnull
0x16d44d  stloc.1
0x16d44e  ldarg.1
0x16d44f  brfalse.s loc_16D459
0x16d451  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.DependencyNodesCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.DependencyNodesCache::Instance()
0x16d456  stloc.0
0x16d457  br.s     loc_16D45F
0x16d459  newobj   instance void Microsoft.Crm.ObjectModel.DependencyNodeService::.ctor()
0x16d45e  stloc.1
0x16d45f  ldstr    aDependency_0// "Dependency"
0x16d464  ldarg.2
0x16d465  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x16d46a  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection::.ctor(string, valuetype [mscorlib]System.Guid)
0x16d46f  stloc.2
0x16d470  ldarg.2
0x16d471  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x16d476  stloc.3
0x16d477  ldarg.0
0x16d478  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection Microsoft.Crm.ObjectModel.DependencyOperation::get_Results()
0x16d47d  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.CollectionBase::GetEnumerator()
0x16d482  stloc.s  4
0x16d484  br       loc_16D727
0x16d489  ldloc.s  4
0x16d48b  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x16d490  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity
0x16d495  stloc.s  5
0x16d497  ldloc.s  5
0x16d499  ldstr    aRequiredcompon_0// "requiredcomponenttype"
0x16d49e  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::GetAttributeValue(string)
0x16d4a3  unbox.any [mscorlib]System.Int32
0x16d4a8  ldc.i4.s 0xB
0x16d4aa  bne.un   loc_16D727
0x16d4af  ldloc.s  5
0x16d4b1  ldstr    aDependentcompo_0// "dependentcomponenttype"
0x16d4b6  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::GetAttributeValue(string)
0x16d4bb  unbox.any [mscorlib]System.Int32
0x16d4c0  ldc.i4.s 0xA
0x16d4c2  bne.un   loc_16D727
0x16d4c7  ldloc.s  5
0x16d4c9  ldstr    aDependentcompo// "dependentcomponentobjectid"
0x16d4ce  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::GetAttributeValue(string)
0x16d4d3  unbox.any [mscorlib]System.Guid
0x16d4d8  stloc.s  6
0x16d4da  ldloc.s  5
0x16d4dc  ldstr    aRequiredcompon// "requiredcomponentobjectid"
0x16d4e1  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::GetAttributeValue(string)
0x16d4e6  unbox.any [mscorlib]System.Guid
0x16d4eb  stloc.s  7
0x16d4ed  ldloc.3
0x16d4ee  ldloc.s  6
0x16d4f0  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationship [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntityRelationship(valuetype [mscorlib]System.Guid)
0x16d4f5  stloc.s  8
0x16d4f7  ldloc.3
0x16d4f8  ldloc.s  7
0x16d4fa  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationshipRole [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntityRelationshipRole(valuetype [mscorlib]System.Guid)
0x16d4ff  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationshipRole::get_EntityId()
0x16d504  stloc.s  9
0x16d506  ldarg.0
0x16d507  ldloc.s  9
0x16d509  ldloc.1
0x16d50a  ldloc.0
0x16d50b  ldarg.2
0x16d50c  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity Microsoft.Crm.ObjectModel.RetrieveImmediateOperation::RetrieveEntityDependencyNode(valuetype [mscorlib]System.Guid entityId, class Microsoft.Crm.ObjectModel.DependencyNodeService dependencyNodeService, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.DependencyNodesCache dependencyNodesCache, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x16d511  stloc.s  0xA
0x16d513  ldloc.s  0xA
0x16d515  brfalse  loc_16D727
0x16d51a  ldloc.s  5
0x16d51c  ldstr    aRequiredcompon_0// "requiredcomponenttype"
0x16d521  ldc.i4.1
0x16d522  box      [mscorlib]System.Int32
0x16d527  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x16d52c  ldloc.s  5
0x16d52e  ldstr    aRequiredcompon_1// "requiredcomponentnodeid"
0x16d533  ldloc.s  0xA
0x16d535  ldstr    aDependencynode_0// "dependencynodeid"
0x16d53a  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::GetAttributeValue(string)
0x16d53f  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x16d544  ldloc.s  5
0x16d546  ldstr    aRequiredcompon// "requiredcomponentobjectid"
0x16d54b  ldloc.s  9
0x16d54d  box      [mscorlib]System.Guid
0x16d552  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x16d557  ldloc.s  5
0x16d559  ldstr    aRequiredcompon_12// "requiredcomponentbasesolutionid"
0x16d55e  ldloc.s  0xA
0x16d560  ldstr    aBasesolutionid// "basesolutionid"
0x16d565  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::GetAttributeValue(string)
0x16d56a  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x16d56f  ldloc.s  5
0x16d571  ldstr    aRequiredcompon_11// "requiredcomponentparentid"
0x16d576  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::IsAttributeNull(string)
0x16d57b  brtrue.s loc_16D589
0x16d57d  ldloc.s  5
0x16d57f  ldstr    aRequiredcompon_11// "requiredcomponentparentid"
0x16d584  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::ClearAttribute(string)
0x16d589  ldloc.s  8
0x16d58b  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationship::get_IsCustomRelationship()
0x16d590  brtrue   loc_16D727
0x16d595  ldloc.s  8
0x16d597  callvirt instance valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationshipType [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationship::get_EntityRelationshipType()
0x16d59c  brtrue   loc_16D727
0x16d5a1  ldloc.s  8
0x16d5a3  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IEntityRelationshipRoleCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationship::get_EntityRelationshipRoles()
0x16d5a8  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationshipRole>::GetEnumerator()
0x16d5ad  stloc.s  0xB
0x16d5af  br       loc_16D70D
0x16d5b4  ldloc.s  0xB
0x16d5b6  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationshipRole>::get_Current()
0x16d5bb  stloc.s  0xC
0x16d5bd  ldloc.s  0xC
0x16d5bf  callvirt instance valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationshipRoleType [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationshipRole::get_RelationshipRoleType()
0x16d5c4  brtrue   loc_16D70D
0x16d5c9  ldarg.0
0x16d5ca  ldloc.s  0xC
0x16d5cc  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationshipRole::get_EntityId()
0x16d5d1  ldloc.1
0x16d5d2  ldloc.0
0x16d5d3  ldarg.2
0x16d5d4  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity Microsoft.Crm.ObjectModel.RetrieveImmediateOperation::RetrieveEntityDependencyNode(valuetype [mscorlib]System.Guid entityId, class Microsoft.Crm.ObjectModel.DependencyNodeService dependencyNodeService, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.DependencyNodesCache dependencyNodesCache, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x16d5d9  stloc.s  0xD
0x16d5db  ldloc.s  0xD
0x16d5dd  brfalse  loc_16D70D
0x16d5e2  ldarg.2
0x16d5e3  newobj   instance void [Microsoft.Crm.Entities]Microsoft.Crm.Entities.Dependency::.ctor(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x16d5e8  stloc.s  0xE
0x16d5ea  ldloc.s  0xE
0x16d5ec  ldstr    aDependencyid// "dependencyid"
0x16d5f1  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x16d5f6  box      [mscorlib]System.Guid
0x16d5fb  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x16d600  ldloc.s  0xE
0x16d602  ldstr    aDependencytype// "dependencytype"
0x16d607  ldloc.s  5
0x16d609  ldstr    aDependencytype// "dependencytype"
0x16d60e  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::GetAttributeValue(string)
0x16d613  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x16d618  ldloc.s  0xE
0x16d61a  ldstr    aDependentcompo_0// "dependentcomponenttype"
0x16d61f  ldloc.s  5
0x16d621  ldstr    aDependentcompo_0// "dependentcomponenttype"
0x16d626  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::GetAttributeValue(string)
0x16d62b  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x16d630  ldloc.s  0xE
0x16d632  ldstr    aDependentcompo_1// "dependentcomponentnodeid"
0x16d637  ldloc.s  5
0x16d639  ldstr    aDependentcompo_1// "dependentcomponentnodeid"
0x16d63e  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::GetAttributeValue(string)
0x16d643  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x16d648  ldloc.s  0xE
0x16d64a  ldstr    aDependentcompo// "dependentcomponentobjectid"
0x16d64f  ldloc.s  5
0x16d651  ldstr    aDependentcompo// "dependentcomponentobjectid"
0x16d656  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::GetAttributeValue(string)
0x16d65b  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x16d660  ldloc.s  0xE
0x16d662  ldstr    aDependentcompo_4// "dependentcomponentparentid"
0x16d667  ldloc.s  5
0x16d669  ldstr    aDependentcompo_4// "dependentcomponentparentid"
0x16d66e  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::GetAttributeValue(string)
0x16d673  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x16d678  ldloc.s  0xE
0x16d67a  ldstr    aDependentcompo_3// "dependentcomponentbasesolutionid"
0x16d67f  ldloc.s  5
0x16d681  ldstr    aDependentcompo_3// "dependentcomponentbasesolutionid"
0x16d686  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::GetAttributeValue(string)
0x16d68b  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x16d690  ldloc.s  0xE
0x16d692  ldstr    aRequiredcompon_0// "requiredcomponenttype"
0x16d697  ldc.i4.1
0x16d698  box      [mscorlib]System.Int32
0x16d69d  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x16d6a2  ldloc.s  0xE
0x16d6a4  ldstr    aRequiredcompon_1// "requiredcomponentnodeid"
0x16d6a9  ldloc.s  0xD
0x16d6ab  ldstr    aDependencynode_0// "dependencynodeid"
0x16d6b0  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::GetAttributeValue(string)
0x16d6b5  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x16d6ba  ldloc.s  0xE
0x16d6bc  ldstr    aRequiredcompon// "requiredcomponentobjectid"
0x16d6c1  ldloc.s  0xC
0x16d6c3  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationshipRole::get_EntityId()
0x16d6c8  box      [mscorlib]System.Guid
0x16d6cd  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x16d6d2  ldloc.s  0xE
0x16d6d4  ldstr    aRequiredcompon_12// "requiredcomponentbasesolutionid"
0x16d6d9  ldloc.s  0xD
0x16d6db  ldstr    aBasesolutionid// "basesolutionid"
0x16d6e0  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::GetAttributeValue(string)
0x16d6e5  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x16d6ea  ldloc.s  0xE
0x16d6ec  ldstr    aRequiredcompon_11// "requiredcomponentparentid"
0x16d6f1  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::IsAttributeNull(string)
0x16d6f6  brtrue.s loc_16D704
0x16d6f8  ldloc.s  0xE
0x16d6fa  ldstr    aRequiredcompon_11// "requiredcomponentparentid"
0x16d6ff  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::ClearAttribute(string)
0x16d704  ldloc.2
0x16d705  ldloc.s  0xE
0x16d707  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection::Add(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity)
0x16d70c  pop
0x16d70d  ldloc.s  0xB
0x16d70f  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x16d714  brtrue   loc_16D5B4
0x16d719  leave.s  loc_16D727
0x16d71b  ldloc.s  0xB
0x16d71d  brfalse.s loc_16D726
0x16d71f  ldloc.s  0xB
0x16d721  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x16d726  endfinally
0x16d727  ldloc.s  4
0x16d729  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x16d72e  brtrue   loc_16D489
0x16d733  leave.s  loc_16D74A
0x16d735  ldloc.s  4
0x16d737  isinst   [mscorlib]System.IDisposable
0x16d73c  stloc.s  0xF
0x16d73e  ldloc.s  0xF
0x16d740  brfalse.s loc_16D749
0x16d742  ldloc.s  0xF
0x16d744  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x16d749  endfinally
0x16d74a  ldloc.2
0x16d74b  callvirt instance int32 [mscorlib]System.Collections.CollectionBase::get_Count()
0x16d750  ldc.i4.0
0x16d751  ble.s    loc_16D75F
0x16d753  ldarg.0
0x16d754  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection Microsoft.Crm.ObjectModel.DependencyOperation::get_Results()
0x16d759  ldloc.2
0x16d75a  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection::AddRange(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection)
0x16d75f  ret
```
