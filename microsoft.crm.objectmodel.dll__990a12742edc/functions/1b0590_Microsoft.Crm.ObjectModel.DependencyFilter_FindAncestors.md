# Microsoft.Crm.ObjectModel.DependencyFilter::FindAncestors

- ea: `0x1b0590`
- end: `0x1b0763`
- name: `Microsoft.Crm.ObjectModel.DependencyFilter::FindAncestors`
- size: `467`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1b04a0`

## callees

- `0x1b0590`
- `0x1b0770`
- `0x1b07d0`
- `0x1b1010`
- `0x1b1530`
- `0x1b1650`
- `0x1b1700`

## string_xrefs

- `0x1b0638`: `componenttype`
- `0x1b05f7`: `requiredcomponentobjectid`
- `0x1b0609`: `requiredcomponenttype`
- `0x1b05d4`: `dependentcomponentobjectid`
- `0x1b05e5`: `dependentcomponenttype`
- `0x1b066b`: `requiredcomponentparentid`
- `0x1b067f`: `requiredcomponentparentid`
- `0x1b0651`: `requiredcomponentbasesolutionid`
- `0x1b05a5`: `SolutionComponent`
- `0x1b0679`: `solutioncomponentid`

## pseudocode

```c

```

## disassembly

```asm
0x1b0590  ldarg.1
0x1b0591  stloc.0
0x1b0592  br       loc_1B0756
0x1b0597  ldloc.0
0x1b0598  newobj   instance void Microsoft.Crm.ObjectModel.RetrieveMultipleDirectAncestorsOperation::.ctor(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection components)
0x1b059d  dup
0x1b059e  ldarg.s  5
0x1b05a0  callvirt instance void Microsoft.Crm.ObjectModel.DependencyOperation::Execute(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x1b05a5  ldstr    aSolutioncompon// "SolutionComponent"
0x1b05aa  ldarg.s  5
0x1b05ac  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x1b05b1  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection::.ctor(string, valuetype [mscorlib]System.Guid)
0x1b05b6  stloc.0
0x1b05b7  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection Microsoft.Crm.ObjectModel.DependencyOperation::get_Results()
0x1b05bc  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.CollectionBase::GetEnumerator()
0x1b05c1  stloc.1
0x1b05c2  br       loc_1B0735
0x1b05c7  ldloc.1
0x1b05c8  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x1b05cd  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity
0x1b05d2  stloc.2
0x1b05d3  ldloc.2
0x1b05d4  ldstr    aDependentcompo// "dependentcomponentobjectid"
0x1b05d9  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::GetAttributeValue(string)
0x1b05de  unbox.any [mscorlib]System.Guid
0x1b05e3  stloc.3
0x1b05e4  ldloc.2
0x1b05e5  ldstr    aDependentcompo_0// "dependentcomponenttype"
0x1b05ea  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::GetAttributeValue(string)
0x1b05ef  unbox.any [mscorlib]System.Int32
0x1b05f4  stloc.s  4
0x1b05f6  ldloc.2
0x1b05f7  ldstr    aRequiredcompon// "requiredcomponentobjectid"
0x1b05fc  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::GetAttributeValue(string)
0x1b0601  unbox.any [mscorlib]System.Guid
0x1b0606  stloc.s  5
0x1b0608  ldloc.2
0x1b0609  ldstr    aRequiredcompon_0// "requiredcomponenttype"
0x1b060e  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::GetAttributeValue(string)
0x1b0613  unbox.any [mscorlib]System.Int32
0x1b0618  stloc.s  6
0x1b061a  ldarg.s  5
0x1b061c  newobj   instance void [Microsoft.Crm.Entities]Microsoft.Crm.Entities.SolutionComponent::.ctor(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1b0621  stloc.s  7
0x1b0623  ldloc.s  7
0x1b0625  ldstr    aObjectid// "objectid"
0x1b062a  ldloc.s  5
0x1b062c  box      [mscorlib]System.Guid
0x1b0631  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x1b0636  ldloc.s  7
0x1b0638  ldstr    aComponenttype// "componenttype"
0x1b063d  ldloc.s  6
0x1b063f  box      [mscorlib]System.Int32
0x1b0644  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x1b0649  ldloc.s  7
0x1b064b  ldstr    aSolutionid// "solutionid"
0x1b0650  ldloc.2
0x1b0651  ldstr    aRequiredcompon_12// "requiredcomponentbasesolutionid"
0x1b0656  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::GetAttributeValue(string)
0x1b065b  unbox.any [mscorlib]System.Guid
0x1b0660  box      [mscorlib]System.Guid
0x1b0665  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x1b066a  ldloc.2
0x1b066b  ldstr    aRequiredcompon_11// "requiredcomponentparentid"
0x1b0670  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::IsAttributeNull(string)
0x1b0675  brtrue.s loc_1B0698
0x1b0677  ldloc.s  7
0x1b0679  ldstr    aSolutioncompon_2// "solutioncomponentid"
0x1b067e  ldloc.2
0x1b067f  ldstr    aRequiredcompon_11// "requiredcomponentparentid"
0x1b0684  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x1b0689  unbox.any [mscorlib]System.Guid
0x1b068e  box      [mscorlib]System.Guid
0x1b0693  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x1b0698  ldarg.0
0x1b0699  ldloc.s  5
0x1b069b  ldloc.s  6
0x1b069d  call     instance string Microsoft.Crm.ObjectModel.DependencyFilter::CreateKey(valuetype [mscorlib]System.Guid objectId, int32 componentType)
0x1b06a2  stloc.s  8
0x1b06a4  ldarg.0
0x1b06a5  ldloc.3
0x1b06a6  ldloc.s  4
0x1b06a8  call     instance string Microsoft.Crm.ObjectModel.DependencyFilter::CreateKey(valuetype [mscorlib]System.Guid objectId, int32 componentType)
0x1b06ad  stloc.s  9
0x1b06af  ldloc.s  6
0x1b06b1  call     class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Dependency.ComponentDefinition [Microsoft.Crm.Platform.Server]Microsoft.Crm.Dependency.ComponentDefinitionFactory::Create(int32)
0x1b06b6  stloc.s  0xA
0x1b06b8  ldloc.s  0xA
0x1b06ba  callvirt instance bool [Microsoft.Crm.Platform.Server]Microsoft.Crm.Dependency.ComponentDefinition::get_DescendentIsViewableComponent()
0x1b06bf  brfalse.s loc_1B06D7
0x1b06c1  ldarg.2
0x1b06c2  ldloc.s  7
0x1b06c4  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection::Add(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity)
0x1b06c9  pop
0x1b06ca  ldarg.0
0x1b06cb  ldarg.3
0x1b06cc  ldloc.s  8
0x1b06ce  ldloc.s  9
0x1b06d0  call     instance void Microsoft.Crm.ObjectModel.DependencyFilter::AddToKeyMap(class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.ObjectModel.StringKeyCollection> keymap, string requiredKey, string dependentKey)
0x1b06d5  br.s     loc_1B0735
0x1b06d7  ldloc.s  0xA
0x1b06d9  callvirt instance bool [Microsoft.Crm.Platform.Server]Microsoft.Crm.Dependency.ComponentDefinition::get_IsViewable()
0x1b06de  brfalse.s loc_1B0721
0x1b06e0  ldarg.3
0x1b06e1  ldloc.s  9
0x1b06e3  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.ObjectModel.StringKeyCollection>::get_Item(void)
0x1b06e8  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<string>::GetEnumerator()
0x1b06ed  stloc.s  0xB
0x1b06ef  br.s     loc_1B0708
0x1b06f1  ldloca.s 0xB
0x1b06f3  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<string>::get_Current()
0x1b06f8  stloc.s  0xC
0x1b06fa  ldarg.0
0x1b06fb  ldloc.s  0xC
0x1b06fd  ldloc.s  7
0x1b06ff  ldarg.s  4
0x1b0701  ldarg.s  5
0x1b0703  call     instance void Microsoft.Crm.ObjectModel.DependencyFilter::AddResult(string key, class [Microsoft.Crm.Entities]Microsoft.Crm.Entities.SolutionComponent component, class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity> results, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x1b0708  ldloca.s 0xB
0x1b070a  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<string>::MoveNext()
0x1b070f  brtrue.s loc_1B06F1
0x1b0711  leave.s  loc_1B0735
0x1b0713  ldloca.s 0xB
0x1b0715  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<string>
0x1b071b  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1b0720  endfinally
0x1b0721  ldarg.0
0x1b0722  ldarg.3
0x1b0723  ldloc.s  8
0x1b0725  ldloc.s  9
0x1b0727  call     instance void Microsoft.Crm.ObjectModel.DependencyFilter::AddToKeyMap(class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.ObjectModel.StringKeyCollection> keymap, string requiredKey, string dependentKey)
0x1b072c  ldloc.0
0x1b072d  ldloc.s  7
0x1b072f  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection::Add(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity)
0x1b0734  pop
0x1b0735  ldloc.1
0x1b0736  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x1b073b  brtrue   loc_1B05C7
0x1b0740  leave.s  loc_1B0756
0x1b0742  ldloc.1
0x1b0743  isinst   [mscorlib]System.IDisposable
0x1b0748  stloc.s  0xD
0x1b074a  ldloc.s  0xD
0x1b074c  brfalse.s loc_1B0755
0x1b074e  ldloc.s  0xD
0x1b0750  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1b0755  endfinally
0x1b0756  ldloc.0
0x1b0757  callvirt instance int32 [mscorlib]System.Collections.CollectionBase::get_Count()
0x1b075c  ldc.i4.0
0x1b075d  bgt      loc_1B0597
0x1b0762  ret
```
