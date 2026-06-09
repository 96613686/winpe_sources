# Microsoft.Crm.ObjectModel.DependencyFilter::FindDescendents

- ea: `0x1b0840`
- end: `0x1b0b4b`
- name: `Microsoft.Crm.ObjectModel.DependencyFilter::FindDescendents`
- size: `779`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1b04a0`

## callees

- `0x19a260`
- `0x1b0770`
- `0x1b0840`
- `0x1b0b50`
- `0x1b0ba0`
- `0x1b1010`

## string_xrefs

- `0x1b085e`: `componenttype`
- `0x1b0a84`: `componenttype`
- `0x1b08f1`: `requiredcomponentobjectid`
- `0x1b090a`: `requiredcomponenttype`
- `0x1b0990`: `dependentcomponentobjectid`
- `0x1b0923`: `dependentcomponenttype`
- `0x1b0977`: `dependentcomponenttype`
- `0x1b09a9`: `dependentcomponentbasesolutionid`
- `0x1b09c2`: `requiredcomponentparentid`
- `0x1b09d6`: `requiredcomponentparentid`
- `0x1b0ab8`: `solutioncomponentid`
- `0x1b089f`: `We should only attempt to find descendents for component that have the DescendentIsViewableComponent flag set, {0}({1}) does not (ViewableDescendentComponentType[{2}] != -1`
- `0x1b0a42`: `The {0}({1}) component must be viewable`

## pseudocode

```c

```

## disassembly

```asm
0x1b0840  newobj   instance void Microsoft.Crm.ObjectModel.DependencyService::.ctor()
0x1b0845  stloc.0
0x1b0846  ldarg.1
0x1b0847  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.CollectionBase::GetEnumerator()
0x1b084c  stloc.1
0x1b084d  br       loc_1B0B29
0x1b0852  ldloc.1
0x1b0853  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x1b0858  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity
0x1b085d  dup
0x1b085e  ldstr    aComponenttype// "componenttype"
0x1b0863  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::GetAttributeValue(string)
0x1b0868  unbox.any [mscorlib]System.Int32
0x1b086d  stloc.2
0x1b086e  ldstr    aObjectid// "objectid"
0x1b0873  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::GetAttributeValue(string)
0x1b0878  unbox.any [mscorlib]System.Guid
0x1b087d  stloc.3
0x1b087e  ldloc.2
0x1b087f  call     class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Dependency.ComponentDefinition [Microsoft.Crm.Platform.Server]Microsoft.Crm.Dependency.ComponentDefinitionFactory::Create(int32)
0x1b0884  stloc.s  4
0x1b0886  ldloc.s  4
0x1b0888  callvirt instance bool [Microsoft.Crm.Platform.Server]Microsoft.Crm.Dependency.ComponentDefinition::get_DescendentIsViewableComponent()
0x1b088d  brfalse.s loc_1B089E
0x1b088f  ldloc.s  4
0x1b0891  callvirt instance int32 [Microsoft.Crm.Platform.Server]Microsoft.Crm.Dependency.ComponentDefinition::get_ViewableDescendentComponentType()
0x1b0896  ldc.i4.m1
0x1b0897  ceq
0x1b0899  ldc.i4.0
0x1b089a  ceq
0x1b089c  br.s     loc_1B089F
0x1b089e  ldc.i4.0
0x1b089f  ldstr    aWeShouldOnlyAt// "We should only attempt to find descende"...
0x1b08a4  ldc.i4.3
0x1b08a5  newarr   [mscorlib]System.Object
0x1b08aa  dup
0x1b08ab  ldc.i4.0
0x1b08ac  ldloc.2
0x1b08ad  call     string [Microsoft.Crm.Platform.Server]Microsoft.Crm.Solution.SolutionComponentTypeMap::RetrievePlatformName(int32)
0x1b08b2  stelem.ref
0x1b08b3  dup
0x1b08b4  ldc.i4.1
0x1b08b5  ldloc.2
0x1b08b6  box      [mscorlib]System.Int32
0x1b08bb  stelem.ref
0x1b08bc  dup
0x1b08bd  ldc.i4.2
0x1b08be  ldloc.s  4
0x1b08c0  callvirt instance int32 [Microsoft.Crm.Platform.Server]Microsoft.Crm.Dependency.ComponentDefinition::get_ViewableDescendentComponentType()
0x1b08c5  box      [mscorlib]System.Int32
0x1b08ca  stelem.ref
0x1b08cb  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string, object[])
0x1b08d0  ldstr    aDependency_0// "Dependency"
0x1b08d5  ldarg.s  4
0x1b08d7  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext)
0x1b08dc  stloc.s  5
0x1b08de  ldloc.s  5
0x1b08e0  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x1b08e5  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddAllColumns()
0x1b08ea  ldloc.s  5
0x1b08ec  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x1b08f1  ldstr    aRequiredcompon// "requiredcomponentobjectid"
0x1b08f6  ldc.i4.0
0x1b08f7  ldloc.3
0x1b08f8  box      [mscorlib]System.Guid
0x1b08fd  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x1b0902  pop
0x1b0903  ldloc.s  5
0x1b0905  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x1b090a  ldstr    aRequiredcompon_0// "requiredcomponenttype"
0x1b090f  ldc.i4.0
0x1b0910  ldloc.2
0x1b0911  box      [mscorlib]System.Int32
0x1b0916  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x1b091b  pop
0x1b091c  ldloc.s  5
0x1b091e  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x1b0923  ldstr    aDependentcompo_0// "dependentcomponenttype"
0x1b0928  ldc.i4.0
0x1b0929  ldloc.s  4
0x1b092b  callvirt instance int32 [Microsoft.Crm.Platform.Server]Microsoft.Crm.Dependency.ComponentDefinition::get_ViewableDescendentComponentType()
0x1b0930  box      [mscorlib]System.Int32
0x1b0935  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x1b093a  pop
0x1b093b  ldloc.0
0x1b093c  ldloc.s  5
0x1b093e  ldarg.s  4
0x1b0940  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::RetrieveMultiple(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x1b0945  stloc.s  6
0x1b0947  ldloc.s  4
0x1b0949  callvirt instance int32 [Microsoft.Crm.Platform.Server]Microsoft.Crm.Dependency.ComponentDefinition::get_ViewableDescendentComponentType()
0x1b094e  stloc.s  7
0x1b0950  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x1b0955  stloc.s  8
0x1b0957  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x1b095c  stloc.s  9
0x1b095e  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x1b0963  stloc.s  0xA
0x1b0965  ldloc.s  6
0x1b0967  callvirt instance int32 [mscorlib]System.Collections.CollectionBase::get_Count()
0x1b096c  ldc.i4.0
0x1b096d  ble.s    loc_1B09E9
0x1b096f  ldloc.s  6
0x1b0971  ldc.i4.0
0x1b0972  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection::get_Item(int32)
0x1b0977  ldstr    aDependentcompo_0// "dependentcomponenttype"
0x1b097c  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::GetAttributeValue(string)
0x1b0981  unbox.any [mscorlib]System.Int32
0x1b0986  stloc.s  7
0x1b0988  ldloc.s  6
0x1b098a  ldc.i4.0
0x1b098b  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection::get_Item(int32)
0x1b0990  ldstr    aDependentcompo// "dependentcomponentobjectid"
0x1b0995  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::GetAttributeValue(string)
0x1b099a  unbox.any [mscorlib]System.Guid
0x1b099f  stloc.s  8
0x1b09a1  ldloc.s  6
0x1b09a3  ldc.i4.0
0x1b09a4  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection::get_Item(int32)
0x1b09a9  ldstr    aDependentcompo_3// "dependentcomponentbasesolutionid"
0x1b09ae  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::GetAttributeValue(string)
0x1b09b3  unbox.any [mscorlib]System.Guid
0x1b09b8  stloc.s  9
0x1b09ba  ldloc.s  6
0x1b09bc  ldc.i4.0
0x1b09bd  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection::get_Item(int32)
0x1b09c2  ldstr    aRequiredcompon_11// "requiredcomponentparentid"
0x1b09c7  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::IsAttributeNull(string)
0x1b09cc  brtrue.s loc_1B0A36
0x1b09ce  ldloc.s  6
0x1b09d0  ldc.i4.0
0x1b09d1  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection::get_Item(int32)
0x1b09d6  ldstr    aRequiredcompon_11// "requiredcomponentparentid"
0x1b09db  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::GetAttributeValue(string)
0x1b09e0  unbox.any [mscorlib]System.Guid
0x1b09e5  stloc.s  0xA
0x1b09e7  br.s     loc_1B0A36
0x1b09e9  ldarg.0
0x1b09ea  ldloc.3
0x1b09eb  ldarg.s  4
0x1b09ed  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.ObjectModel.DependencyFilter::FindEntityRelationshipIdFromRole(valuetype [mscorlib]System.Guid entityRelationshipRoleId, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x1b09f2  stloc.s  8
0x1b09f4  ldarg.0
0x1b09f5  ldloc.s  8
0x1b09f7  ldloc.s  7
0x1b09f9  ldarg.s  4
0x1b09fb  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity Microsoft.Crm.ObjectModel.DependencyFilter::RetrieveDependenciesNodeFromObjectId(valuetype [mscorlib]System.Guid objectId, int32 descendentComponentType, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x1b0a00  stloc.s  0xD
0x1b0a02  ldloc.s  0xD
0x1b0a04  ldstr    aBasesolutionid// "basesolutionid"
0x1b0a09  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::GetAttributeValue(string)
0x1b0a0e  unbox.any [mscorlib]System.Guid
0x1b0a13  stloc.s  9
0x1b0a15  ldloc.s  0xD
0x1b0a17  ldstr    aParentid// "parentid"
0x1b0a1c  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::IsAttributeNull(string)
0x1b0a21  brtrue.s loc_1B0A36
0x1b0a23  ldloc.s  0xD
0x1b0a25  ldstr    aParentid// "parentid"
0x1b0a2a  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::GetAttributeValue(string)
0x1b0a2f  unbox.any [mscorlib]System.Guid
0x1b0a34  stloc.s  0xA
0x1b0a36  ldloc.s  7
0x1b0a38  call     class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Dependency.ComponentDefinition [Microsoft.Crm.Platform.Server]Microsoft.Crm.Dependency.ComponentDefinitionFactory::Create(int32)
0x1b0a3d  callvirt instance bool [Microsoft.Crm.Platform.Server]Microsoft.Crm.Dependency.ComponentDefinition::get_IsViewable()
0x1b0a42  ldstr    aThe01Component// "The {0}({1}) component must be viewable"
0x1b0a47  ldc.i4.2
0x1b0a48  newarr   [mscorlib]System.Object
0x1b0a4d  dup
0x1b0a4e  ldc.i4.0
0x1b0a4f  ldloc.s  7
0x1b0a51  call     string [Microsoft.Crm.Platform.Server]Microsoft.Crm.Solution.SolutionComponentTypeMap::RetrievePlatformName(int32)
0x1b0a56  stelem.ref
0x1b0a57  dup
0x1b0a58  ldc.i4.1
0x1b0a59  ldloc.s  7
0x1b0a5b  box      [mscorlib]System.Int32
0x1b0a60  stelem.ref
0x1b0a61  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string, object[])
0x1b0a66  ldarg.s  4
0x1b0a68  newobj   instance void [Microsoft.Crm.Entities]Microsoft.Crm.Entities.SolutionComponent::.ctor(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1b0a6d  stloc.s  0xB
0x1b0a6f  ldloc.s  0xB
0x1b0a71  ldstr    aObjectid// "objectid"
0x1b0a76  ldloc.s  8
0x1b0a78  box      [mscorlib]System.Guid
0x1b0a7d  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x1b0a82  ldloc.s  0xB
0x1b0a84  ldstr    aComponenttype// "componenttype"
0x1b0a89  ldloc.s  7
0x1b0a8b  box      [mscorlib]System.Int32
0x1b0a90  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x1b0a95  ldloc.s  0xB
0x1b0a97  ldstr    aSolutionid// "solutionid"
0x1b0a9c  ldloc.s  9
0x1b0a9e  box      [mscorlib]System.Guid
0x1b0aa3  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x1b0aa8  ldloc.s  0xA
0x1b0aaa  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x1b0aaf  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x1b0ab4  brfalse.s loc_1B0AC9
0x1b0ab6  ldloc.s  0xB
0x1b0ab8  ldstr    aSolutioncompon_2// "solutioncomponentid"
0x1b0abd  ldloc.s  0xA
0x1b0abf  box      [mscorlib]System.Guid
0x1b0ac4  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x1b0ac9  ldarg.0
0x1b0aca  ldloc.3
0x1b0acb  ldloc.2
0x1b0acc  call     instance string Microsoft.Crm.ObjectModel.DependencyFilter::CreateKey(valuetype [mscorlib]System.Guid objectId, int32 componentType)
0x1b0ad1  stloc.s  0xC
0x1b0ad3  ldarg.0
0x1b0ad4  ldloc.s  0xC
0x1b0ad6  ldloc.s  0xB
0x1b0ad8  ldarg.3
0x1b0ad9  ldarg.s  4
0x1b0adb  call     instance void Microsoft.Crm.ObjectModel.DependencyFilter::AddResult(string key, class [Microsoft.Crm.Entities]Microsoft.Crm.Entities.SolutionComponent component, class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity> results, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x1b0ae0  ldarg.2
0x1b0ae1  ldloc.s  0xC
0x1b0ae3  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.ObjectModel.StringKeyCollection>::ContainsKey(var<u1>)
0x1b0ae8  brfalse.s loc_1B0B29
0x1b0aea  ldarg.2
0x1b0aeb  ldloc.s  0xC
0x1b0aed  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.ObjectModel.StringKeyCollection>::get_Item(void)
0x1b0af2  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<string>::GetEnumerator()
0x1b0af7  stloc.s  0xE
0x1b0af9  br.s     loc_1B0B10
0x1b0afb  ldloca.s 0xE
0x1b0afd  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<string>::get_Current()
0x1b0b02  pop
0x1b0b03  ldarg.0
0x1b0b04  ldloc.s  0xC
0x1b0b06  ldloc.s  0xB
0x1b0b08  ldarg.3
0x1b0b09  ldarg.s  4
0x1b0b0b  call     instance void Microsoft.Crm.ObjectModel.DependencyFilter::AddResult(string key, class [Microsoft.Crm.Entities]Microsoft.Crm.Entities.SolutionComponent component, class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity> results, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x1b0b10  ldloca.s 0xE
0x1b0b12  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<string>::MoveNext()
0x1b0b17  brtrue.s loc_1B0AFB
0x1b0b19  leave.s  loc_1B0B29
0x1b0b1b  ldloca.s 0xE
0x1b0b1d  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<string>
0x1b0b23  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1b0b28  endfinally
0x1b0b29  ldloc.1
0x1b0b2a  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x1b0b2f  brtrue   loc_1B0852
0x1b0b34  leave.s  loc_1B0B4A
0x1b0b36  ldloc.1
0x1b0b37  isinst   [mscorlib]System.IDisposable
0x1b0b3c  stloc.s  0xF
0x1b0b3e  ldloc.s  0xF
0x1b0b40  brfalse.s loc_1B0B49
0x1b0b42  ldloc.s  0xF
0x1b0b44  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1b0b49  endfinally
0x1b0b4a  ret
```
