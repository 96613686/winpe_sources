# Microsoft.Crm.ObjectModel.DependencyService::GetDependentWorkflows

- ea: `0x19a800`
- end: `0x19a97b`
- name: `Microsoft.Crm.ObjectModel.DependencyService::GetDependentWorkflows`
- size: `379`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x19a6b0`

## callees

- `0x19a800`

## string_xrefs

- `0x19a88f`: `requiredcomponentobjectid`
- `0x19a865`: `requiredcomponenttype`
- `0x19a836`: `dependentcomponentobjectid`
- `0x19a887`: `dependentcomponentobjectid`
- `0x19a84c`: `dependentcomponenttype`
- `0x19a80c`: `SolutionComponent`
- `0x19a8d1`: `.dependentcomponentobjectid`
- `0x19a8fb`: `.requiredcomponentobjectid`

## pseudocode

```c

```

## disassembly

```asm
0x19a800  ldstr    aDep// "dep"
0x19a805  stloc.0
0x19a806  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>>::.ctor()
0x19a80b  stloc.1
0x19a80c  ldstr    aSolutioncompon// "SolutionComponent"
0x19a811  ldarg.2
0x19a812  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext)
0x19a817  stloc.2
0x19a818  ldloc.2
0x19a819  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x19a81e  ldstr    aSolutionid// "solutionid"
0x19a823  ldc.i4.0
0x19a824  ldarg.3
0x19a825  box      [mscorlib]System.Guid
0x19a82a  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x19a82f  pop
0x19a830  ldloc.2
0x19a831  ldstr    aDependency_0// "Dependency"
0x19a836  ldstr    aDependentcompo// "dependentcomponentobjectid"
0x19a83b  ldstr    aObjectid// "objectid"
0x19a840  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.LinkEntityExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::AddLinkEntity(string, string, string)
0x19a845  stloc.3
0x19a846  ldloc.3
0x19a847  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.LinkEntityExpression::get_Criteria()
0x19a84c  ldstr    aDependentcompo_0// "dependentcomponenttype"
0x19a851  ldc.i4.0
0x19a852  ldc.i4.s 0x1D
0x19a854  box      [mscorlib]System.Int32
0x19a859  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x19a85e  pop
0x19a85f  ldloc.3
0x19a860  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.LinkEntityExpression::get_Criteria()
0x19a865  ldstr    aRequiredcompon_0// "requiredcomponenttype"
0x19a86a  ldc.i4.0
0x19a86b  ldc.i4.s 0x1D
0x19a86d  box      [mscorlib]System.Int32
0x19a872  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x19a877  pop
0x19a878  ldloc.3
0x19a879  ldloc.0
0x19a87a  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.LinkEntityExpression::set_TableAlias(string)
0x19a87f  ldc.i4.2
0x19a880  newarr   [mscorlib]System.String
0x19a885  dup
0x19a886  ldc.i4.0
0x19a887  ldstr    aDependentcompo// "dependentcomponentobjectid"
0x19a88c  stelem.ref
0x19a88d  dup
0x19a88e  ldc.i4.1
0x19a88f  ldstr    aRequiredcompon// "requiredcomponentobjectid"
0x19a894  stelem.ref
0x19a895  stloc.s  4
0x19a897  ldloc.3
0x19a898  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.LinkEntityExpression::get_ColumnSet()
0x19a89d  ldloc.s  4
0x19a89f  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumns(string[])
0x19a8a4  ldarg.1
0x19a8a5  ldloc.2
0x19a8a6  ldarg.2
0x19a8a7  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::RetrieveMultiple(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x19a8ac  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.CollectionBase::GetEnumerator()
0x19a8b1  stloc.s  5
0x19a8b3  br       loc_19A956
0x19a8b8  ldloc.s  5
0x19a8ba  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x19a8bf  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity
0x19a8c4  stloc.s  6
0x19a8c6  ldnull
0x19a8c7  stloc.s  7
0x19a8c9  ldloc.s  6
0x19a8cb  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfoCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Attributes()
0x19a8d0  ldloc.0
0x19a8d1  ldstr    aDependentcompo_10// ".dependentcomponentobjectid"
0x19a8d6  call     string [mscorlib]System.String::Concat(string, string)
0x19a8db  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfo [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfoCollection::get_Item(string)
0x19a8e0  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfo::get_Value()
0x19a8e5  call     string [mscorlib]System.Convert::ToString(object)
0x19a8ea  ldloca.s 8
0x19a8ec  call     bool [mscorlib]System.Guid::TryParse(string, valuetype [mscorlib]System.Guid&)
0x19a8f1  brfalse.s loc_19A956
0x19a8f3  ldloc.s  6
0x19a8f5  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfoCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Attributes()
0x19a8fa  ldloc.0
0x19a8fb  ldstr    aRequiredcompon_15// ".requiredcomponentobjectid"
0x19a900  call     string [mscorlib]System.String::Concat(string, string)
0x19a905  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfo [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfoCollection::get_Item(string)
0x19a90a  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfo::get_Value()
0x19a90f  call     string [mscorlib]System.Convert::ToString(object)
0x19a914  ldloca.s 9
0x19a916  call     bool [mscorlib]System.Guid::TryParse(string, valuetype [mscorlib]System.Guid&)
0x19a91b  brfalse.s loc_19A956
0x19a91d  ldloc.1
0x19a91e  ldloc.s  8
0x19a920  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>>::ContainsKey(var<u1>)
0x19a925  brtrue.s loc_19A92E
0x19a927  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::.ctor()
0x19a92c  br.s     loc_19A936
0x19a92e  ldloc.1
0x19a92f  ldloc.s  8
0x19a931  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>>::get_Item(void)
0x19a936  stloc.s  7
0x19a938  ldloc.s  7
0x19a93a  ldloc.s  9
0x19a93c  callvirt instance bool class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::Contains(var<u1>)
0x19a941  brtrue.s loc_19A94C
0x19a943  ldloc.s  7
0x19a945  ldloc.s  9
0x19a947  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::Add(var<u1>)
0x19a94c  ldloc.1
0x19a94d  ldloc.s  8
0x19a94f  ldloc.s  7
0x19a951  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>>::set_Item(var<u1>, !!T0)
0x19a956  ldloc.s  5
0x19a958  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x19a95d  brtrue   loc_19A8B8
0x19a962  leave.s  loc_19A979
0x19a964  ldloc.s  5
0x19a966  isinst   [mscorlib]System.IDisposable
0x19a96b  stloc.s  0xA
0x19a96d  ldloc.s  0xA
0x19a96f  brfalse.s loc_19A978
0x19a971  ldloc.s  0xA
0x19a973  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x19a978  endfinally
0x19a979  ldloc.1
0x19a97a  ret
```
