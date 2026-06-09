# Microsoft.Crm.ObjectModel.DependencyFilter::FilterUnnecessaryDependencies

- ea: `0x1adca0`
- end: `0x1ae108`
- name: `Microsoft.Crm.ObjectModel.DependencyFilter::FilterUnnecessaryDependencies`
- size: `1128`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1af4c0`

## callees

- `0x191750`
- `0x192150`
- `0x1adca0`

## string_xrefs

- `0x1adcdb`: `componenttype`
- `0x1add7e`: `requiredcomponentobjectid`
- `0x1ae0c9`: `requiredcomponentobjectid`
- `0x1add6d`: `requiredcomponenttype`
- `0x1ae07c`: `requiredcomponentbasesolutionid`
- `0x1adca6`: `SolutionComponent`
- `0x1ade41`: `SolutionComponent`
- `0x1ade5b`: `SolutionComponent`
- `0x1adee8`: `SolutionComponent`
- `0x1adeff`: `SolutionComponent`
- `0x1adeb2`: `rootcomponentbehavior`

## pseudocode

```c

```

## disassembly

```asm
0x1adca0  ldarg.1
0x1adca1  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection::get_EntityName()
0x1adca6  ldstr    aSolutioncompon// "SolutionComponent"
0x1adcab  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1adcb0  brfalse.s loc_1ADD2F
0x1adcb2  ldarg.1
0x1adcb3  callvirt instance int32 [mscorlib]System.Collections.CollectionBase::get_Count()
0x1adcb8  ldc.i4.1
0x1adcb9  sub
0x1adcba  stloc.0
0x1adcbb  br.s     loc_1ADD26
0x1adcbd  ldarg.1
0x1adcbe  ldloc.0
0x1adcbf  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection::get_Item(int32)
0x1adcc4  ldstr    aObjectid// "objectid"
0x1adcc9  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::GetAttributeValue(string)
0x1adcce  unbox.any [mscorlib]System.Guid
0x1adcd3  stloc.1
0x1adcd4  ldarg.1
0x1adcd5  ldloc.0
0x1adcd6  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection::get_Item(int32)
0x1adcdb  ldstr    aComponenttype// "componenttype"
0x1adce0  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::GetAttributeValue(string)
0x1adce5  unbox.any [mscorlib]System.Int32
0x1adcea  stloc.2
0x1adceb  ldloc.2
0x1adcec  call     class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateLoader [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateLoaderFactory::Create(int32)
0x1adcf1  ldloc.2
0x1adcf2  ldloc.1
0x1adcf3  ldc.i4.0
0x1adcf4  ldarg.3
0x1adcf5  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.SolutionAwareComponents.BusinessComponentState [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateLoader::Load(int32, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateLoadOption, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x1adcfa  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.SolutionAwareComponents.BusinessComponentState::get_BaseInstance()
0x1adcff  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance::get_SolutionId()
0x1add04  ldsfld   valuetype [mscorlib]System.Guid [Microsoft.Crm.Constants]Microsoft.Crm.SolutionConstants::SystemSolutionId
0x1add09  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x1add0e  brfalse.s loc_1ADD22
0x1add10  ldloc.2
0x1add11  ldc.i4.s 0x1F
0x1add13  beq.s    loc_1ADD22
0x1add15  ldarg.1
0x1add16  ldarg.1
0x1add17  ldloc.0
0x1add18  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection::get_Item(int32)
0x1add1d  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection::Remove(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity)
0x1add22  ldloc.0
0x1add23  ldc.i4.1
0x1add24  sub
0x1add25  stloc.0
0x1add26  ldloc.0
0x1add27  ldc.i4.0
0x1add28  bge.s    loc_1ADCBD
0x1add2a  br       loc_1AE106
0x1add2f  ldarg.2
0x1add30  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x1add35  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x1add3a  brfalse  loc_1AE106
0x1add3f  newobj   instance void Microsoft.Crm.ObjectModel.SolutionComponentService::.ctor()
0x1add44  stloc.3
0x1add45  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>>::.ctor()
0x1add4a  stloc.s  4
0x1add4c  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, bool>::.ctor()
0x1add51  stloc.s  5
0x1add53  ldarg.1
0x1add54  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.CollectionBase::GetEnumerator()
0x1add59  stloc.s  0xA
0x1add5b  br       loc_1ADE1E
0x1add60  ldloc.s  0xA
0x1add62  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x1add67  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity
0x1add6c  dup
0x1add6d  ldstr    aRequiredcompon_0// "requiredcomponenttype"
0x1add72  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::GetAttributeValue(string)
0x1add77  unbox.any [mscorlib]System.Int32
0x1add7c  stloc.s  0xB
0x1add7e  ldstr    aRequiredcompon// "requiredcomponentobjectid"
0x1add83  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::GetAttributeValue(string)
0x1add88  unbox.any [mscorlib]System.Guid
0x1add8d  stloc.s  0xC
0x1add8f  ldloc.s  0xB
0x1add91  call     class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Dependency.ComponentDefinition [Microsoft.Crm.Platform.Server]Microsoft.Crm.Dependency.ComponentDefinitionFactory::Create(int32)
0x1add96  stloc.s  0xD
0x1add98  ldloc.s  0xD
0x1add9a  callvirt instance int32 [Microsoft.Crm.Platform.Server]Microsoft.Crm.Dependency.ComponentDefinition::get_RootComponent()
0x1add9f  ldc.i4.1
0x1adda0  bne.un.s loc_1ADE00
0x1adda2  ldloc.3
0x1adda3  ldloc.s  0xB
0x1adda5  ldloc.s  0xC
0x1adda7  ldarg.3
0x1adda8  callvirt instance valuetype [mscorlib]System.Guid[] Microsoft.Crm.ObjectModel.SolutionComponentService::GetRootEntityIds(int32 subComponentType, valuetype [mscorlib]System.Guid subComponentId, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x1addad  stloc.s  0xE
0x1addaf  ldc.i4.0
0x1addb0  stloc.s  0xF
0x1addb2  br.s     loc_1ADDF8
0x1addb4  ldloc.s  0xE
0x1addb6  ldloc.s  0xF
0x1addb8  ldelem   [mscorlib]System.Guid
0x1addbd  stloc.s  0x10
0x1addbf  ldloc.s  4
0x1addc1  ldloc.s  0x10
0x1addc3  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>>::ContainsKey(var<u1>)
0x1addc8  brfalse.s loc_1ADDDC
0x1addca  ldloc.s  4
0x1addcc  ldloc.s  0x10
0x1addce  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>>::get_Item(void)
0x1addd3  ldloc.s  0xC
0x1addd5  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::Add(var<u1>)
0x1addda  br.s     loc_1ADDF2
0x1adddc  ldloc.s  4
0x1addde  ldloc.s  0x10
0x1adde0  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::.ctor()
0x1adde5  dup
0x1adde6  ldloc.s  0xC
0x1adde8  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::Add(var<u1>)
0x1added  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>>::Add(var<u1>, !!T0)
0x1addf2  ldloc.s  0xF
0x1addf4  ldc.i4.1
0x1addf5  add
0x1addf6  stloc.s  0xF
0x1addf8  ldloc.s  0xF
0x1addfa  ldloc.s  0xE
0x1addfc  ldlen
0x1addfd  conv.i4
0x1addfe  blt.s    loc_1ADDB4
0x1ade00  ldloc.s  0xD
0x1ade02  callvirt instance bool [Microsoft.Crm.Platform.Server]Microsoft.Crm.Dependency.ComponentDefinition::get_CanBeAddedToSolutionComponents()
0x1ade07  brfalse.s loc_1ADE1E
0x1ade09  ldloc.s  5
0x1ade0b  ldloc.s  0xC
0x1ade0d  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, bool>::ContainsKey(var<u1>)
0x1ade12  brtrue.s loc_1ADE1E
0x1ade14  ldloc.s  5
0x1ade16  ldloc.s  0xC
0x1ade18  ldc.i4.1
0x1ade19  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, bool>::Add(var<u1>, !!T0)
0x1ade1e  ldloc.s  0xA
0x1ade20  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x1ade25  brtrue   loc_1ADD60
0x1ade2a  leave.s  loc_1ADE41
0x1ade2c  ldloc.s  0xA
0x1ade2e  isinst   [mscorlib]System.IDisposable
0x1ade33  stloc.s  0x11
0x1ade35  ldloc.s  0x11
0x1ade37  brfalse.s loc_1ADE40
0x1ade39  ldloc.s  0x11
0x1ade3b  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1ade40  endfinally
0x1ade41  ldstr    aSolutioncompon// "SolutionComponent"
0x1ade46  ldarg.3
0x1ade47  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1ade4c  stloc.s  6
0x1ade4e  ldloc.s  4
0x1ade50  callvirt instance int32 class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>>::get_Count()
0x1ade55  ldc.i4.0
0x1ade56  ble      loc_1ADEE8
0x1ade5b  ldstr    aSolutioncompon// "SolutionComponent"
0x1ade60  ldarg.3
0x1ade61  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext)
0x1ade66  stloc.s  0x12
0x1ade68  ldloc.s  0x12
0x1ade6a  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x1ade6f  ldstr    aObjectid// "objectid"
0x1ade74  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumn(string)
0x1ade79  ldloc.s  4
0x1ade7b  callvirt instance int32 class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>>::get_Count()
0x1ade80  newarr   [mscorlib]System.Guid
0x1ade85  stloc.s  0x13
0x1ade87  ldloc.s  4
0x1ade89  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>>::get_Keys()
0x1ade8e  ldloc.s  0x13
0x1ade90  ldc.i4.0
0x1ade91  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection<valuetype [mscorlib]System.Guid, class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>>::CopyTo(var<u1>[], !!T0)
0x1ade96  ldloc.s  0x12
0x1ade98  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x1ade9d  ldstr    aObjectid// "objectid"
0x1adea2  ldc.i4.8
0x1adea3  ldloc.s  0x13
0x1adea5  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, class [mscorlib]System.Array)
0x1adeaa  pop
0x1adeab  ldloc.s  0x12
0x1adead  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x1adeb2  ldstr    aRootcomponentb// "rootcomponentbehavior"
0x1adeb7  ldc.i4.0
0x1adeb8  ldc.i4.0
0x1adeb9  box      [mscorlib]System.Int32
0x1adebe  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x1adec3  pop
0x1adec4  ldloc.s  0x12
0x1adec6  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x1adecb  ldstr    aSolutionid// "solutionid"
0x1aded0  ldc.i4.0
0x1aded1  ldarg.2
0x1aded2  box      [mscorlib]System.Guid
0x1aded7  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x1adedc  pop
0x1adedd  ldloc.3
0x1adede  ldloc.s  0x12
0x1adee0  ldarg.3
0x1adee1  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::RetrieveMultiple(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x1adee6  stloc.s  6
0x1adee8  ldstr    aSolutioncompon// "SolutionComponent"
0x1adeed  ldarg.3
0x1adeee  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1adef3  stloc.s  7
0x1adef5  ldloc.s  5
0x1adef7  callvirt instance int32 class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, bool>::get_Count()
0x1adefc  ldc.i4.0
0x1adefd  ble.s    loc_1ADF73
0x1adeff  ldstr    aSolutioncompon// "SolutionComponent"
0x1adf04  ldarg.3
0x1adf05  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext)
0x1adf0a  stloc.s  0x14
0x1adf0c  ldloc.s  0x14
0x1adf0e  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x1adf13  ldstr    aObjectid// "objectid"
0x1adf18  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumn(string)
0x1adf1d  ldloc.s  5
0x1adf1f  callvirt instance int32 class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, bool>::get_Count()
0x1adf24  newarr   [mscorlib]System.Guid
0x1adf29  stloc.s  0x15
0x1adf2b  ldloc.s  5
0x1adf2d  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, bool>::get_Keys()
0x1adf32  ldloc.s  0x15
0x1adf34  ldc.i4.0
0x1adf35  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection<valuetype [mscorlib]System.Guid, bool>::CopyTo(var<u1>[], !!T0)
0x1adf3a  ldloc.s  0x14
0x1adf3c  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x1adf41  ldstr    aObjectid// "objectid"
0x1adf46  ldc.i4.8
0x1adf47  ldloc.s  0x15
0x1adf49  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, class [mscorlib]System.Array)
0x1adf4e  pop
0x1adf4f  ldloc.s  0x14
0x1adf51  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x1adf56  ldstr    aSolutionid// "solutionid"
0x1adf5b  ldc.i4.0
0x1adf5c  ldarg.2
0x1adf5d  box      [mscorlib]System.Guid
0x1adf62  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x1adf67  pop
0x1adf68  ldloc.3
0x1adf69  ldloc.s  0x14
0x1adf6b  ldarg.3
0x1adf6c  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::RetrieveMultiple(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x1adf71  stloc.s  7
0x1adf73  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, bool>::.ctor()
0x1adf78  stloc.s  8
0x1adf7a  ldloc.s  6
0x1adf7c  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.CollectionBase::GetEnumerator()
0x1adf81  stloc.s  0xA
0x1adf83  br.s     loc_1ADFE0
0x1adf85  ldloc.s  0xA
0x1adf87  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x1adf8c  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity
0x1adf91  stloc.s  0x16
0x1adf93  ldloc.s  4
0x1adf95  ldloc.s  0x16
0x1adf97  ldstr    aObjectid// "objectid"
0x1adf9c  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::GetAttributeValue(string)
0x1adfa1  unbox.any [mscorlib]System.Guid
0x1adfa6  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>>::get_Item(void)
0x1adfab  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::GetEnumerator()
0x1adfb0  stloc.s  0x17
0x1adfb2  br.s     loc_1ADFC7
0x1adfb4  ldloca.s 0x17
0x1adfb6  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<valuetype [mscorlib]System.Guid>::get_Current()
0x1adfbb  stloc.s  0x18
0x1adfbd  ldloc.s  8
0x1adfbf  ldloc.s  0x18
0x1adfc1  ldc.i4.1
0x1adfc2  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, bool>::set_Item(var<u1>, !!T0)
0x1adfc7  ldloca.s 0x17
0x1adfc9  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<valuetype [mscorlib]System.Guid>::MoveNext()
0x1adfce  brtrue.s loc_1ADFB4
0x1adfd0  leave.s  loc_1ADFE0
0x1adfd2  ldloca.s 0x17
0x1adfd4  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<valuetype [mscorlib]System.Guid>
0x1adfda  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1adfdf  endfinally
0x1adfe0  ldloc.s  0xA
0x1adfe2  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x1adfe7  brtrue.s loc_1ADF85
0x1adfe9  leave.s  loc_1AE000
0x1adfeb  ldloc.s  0xA
0x1adfed  isinst   [mscorlib]System.IDisposable
0x1adff2  stloc.s  0x11
0x1adff4  ldloc.s  0x11
0x1adff6  brfalse.s loc_1ADFFF
0x1adff8  ldloc.s  0x11
0x1adffa  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1adfff  endfinally
0x1ae000  ldloc.s  7
0x1ae002  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.CollectionBase::GetEnumerator()
0x1ae007  stloc.s  0xA
0x1ae009  br.s     loc_1AE032
0x1ae00b  ldloc.s  0xA
0x1ae00d  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x1ae012  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity
0x1ae017  stloc.s  0x19
  ... truncated ...
```
