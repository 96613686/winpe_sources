# Microsoft.Crm.Application.Platform.SingletonSolutionAdapter::RetrieveDefaultSingletonId

- ea: `0x6e680`
- end: `0x6e832`
- name: `Microsoft.Crm.Application.Platform.SingletonSolutionAdapter::RetrieveDefaultSingletonId`
- size: `434`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x6e250`

## callees

- `0x11590`
- `0x115b0`
- `0x59800`
- `0x5e3f0`
- `0x6a330`
- `0x6a810`
- `0x6e680`

## string_xrefs

- `0x6e6bd`: `componenttype`
- `0x6e680`: `solutioncomponent`
- `0x6e804`: `There should be only one entry for component type {0} in the default solution`

## pseudocode

```c

```

## disassembly

```asm
0x6e680  ldstr    aSolutioncompon// "solutioncomponent"
0x6e685  ldarg.1
0x6e686  call     class Microsoft.Crm.Application.Platform.EntityType Microsoft.Crm.Application.Platform.EntityType::Create(string logicalName, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x6e68b  callvirt instance string Microsoft.Crm.Application.Platform.EntityType::get_LogicalName()
0x6e690  newobj   instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryExpression::.ctor(string)
0x6e695  stloc.0
0x6e696  ldloc.0
0x6e697  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ColumnSetBase [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryBase::get_ColumnSet()
0x6e69c  ldc.i4.2
0x6e69d  newarr   [mscorlib]System.String
0x6e6a2  dup
0x6e6a3  ldc.i4.0
0x6e6a4  ldstr    aObjectid_0// "objectid"
0x6e6a9  stelem.ref
0x6e6aa  dup
0x6e6ab  ldc.i4.1
0x6e6ac  ldstr    aSolutionid_0// "solutionid"
0x6e6b1  stelem.ref
0x6e6b2  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ColumnSetBase::AddColumns(string[])
0x6e6b7  ldloc.0
0x6e6b8  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryExpression::get_Criteria()
0x6e6bd  ldstr    aComponenttype// "componenttype"
0x6e6c2  ldc.i4.0
0x6e6c3  ldarg.0
0x6e6c4  box      [mscorlib]System.Int32
0x6e6c9  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ConditionOperator, object)
0x6e6ce  ldarg.0
0x6e6cf  ldc.i4.s 0x32
0x6e6d1  bne.un.s loc_6E6F4
0x6e6d3  ldc.i4.2
0x6e6d4  newarr   [mscorlib]System.Guid
0x6e6d9  dup
0x6e6da  ldc.i4.0
0x6e6db  ldsfld   valuetype [mscorlib]System.Guid [Microsoft.Crm.Constants]Microsoft.Crm.SolutionConstants::DefaultSolutionId
0x6e6e0  stelem   [mscorlib]System.Guid
0x6e6e5  dup
0x6e6e6  ldc.i4.1
0x6e6e7  ldsfld   valuetype [mscorlib]System.Guid [Microsoft.Crm.Constants]Microsoft.Crm.SolutionConstants::SystemSolutionId
0x6e6ec  stelem   [mscorlib]System.Guid
0x6e6f1  stloc.1
0x6e6f2  br.s     loc_6E707
0x6e6f4  ldc.i4.1
0x6e6f5  newarr   [mscorlib]System.Guid
0x6e6fa  dup
0x6e6fb  ldc.i4.0
0x6e6fc  ldsfld   valuetype [mscorlib]System.Guid [Microsoft.Crm.Constants]Microsoft.Crm.SolutionConstants::DefaultSolutionId
0x6e701  stelem   [mscorlib]System.Guid
0x6e706  stloc.1
0x6e707  ldloc.0
0x6e708  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryExpression::get_Criteria()
0x6e70d  ldstr    aSolutionid_0// "solutionid"
0x6e712  ldc.i4.8
0x6e713  ldloc.1
0x6e714  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ConditionOperator, class [mscorlib]System.Array)
0x6e719  ldloc.0
0x6e71a  ldarg.1
0x6e71b  call     class Microsoft.Crm.Application.Platform.ApplicationEntityCollection Microsoft.Crm.Application.Platform.DataSource::RetrieveMultiple(class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryExpression query, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x6e720  stloc.2
0x6e721  ldarg.0
0x6e722  ldc.i4.s 0x32
0x6e724  bne.un   loc_6E7FB
0x6e729  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x6e72e  stloc.3
0x6e72f  ldloc.2
0x6e730  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.Crm.Application.Platform.Entity>::GetEnumerator()
0x6e735  stloc.s  4
0x6e737  br.s     loc_6E771
0x6e739  ldloc.s  4
0x6e73b  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class Microsoft.Crm.Application.Platform.Entity>::get_Current()
0x6e740  stloc.s  5
0x6e742  ldloc.s  5
0x6e744  ldstr    aSolutionid_0// "solutionid"
0x6e749  callvirt instance string Microsoft.Crm.Application.Platform.EntityProxy::GetPropertyValue(string name)
0x6e74e  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x6e753  ldsfld   valuetype [mscorlib]System.Guid [Microsoft.Crm.Constants]Microsoft.Crm.SolutionConstants::SystemSolutionId
0x6e758  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x6e75d  brfalse.s loc_6E771
0x6e75f  ldloc.s  5
0x6e761  ldstr    aObjectid_0// "objectid"
0x6e766  callvirt instance string Microsoft.Crm.Application.Platform.EntityProxy::GetPropertyValue(string name)
0x6e76b  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x6e770  stloc.3
0x6e771  ldloc.s  4
0x6e773  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x6e778  brtrue.s loc_6E739
0x6e77a  leave.s  loc_6E788
0x6e77c  ldloc.s  4
0x6e77e  brfalse.s loc_6E787
0x6e780  ldloc.s  4
0x6e782  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x6e787  endfinally
0x6e788  ldloc.2
0x6e789  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.Crm.Application.Platform.Entity>::GetEnumerator()
0x6e78e  stloc.s  4
0x6e790  br.s     loc_6E7C4
0x6e792  ldloc.s  4
0x6e794  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class Microsoft.Crm.Application.Platform.Entity>::get_Current()
0x6e799  stloc.s  6
0x6e79b  ldloc.s  6
0x6e79d  ldstr    aObjectid_0// "objectid"
0x6e7a2  callvirt instance string Microsoft.Crm.Application.Platform.EntityProxy::GetPropertyValue(string name)
0x6e7a7  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x6e7ac  ldloc.3
0x6e7ad  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x6e7b2  brfalse.s loc_6E7C4
0x6e7b4  ldloc.s  6
0x6e7b6  ldstr    aObjectid_0// "objectid"
0x6e7bb  callvirt instance string Microsoft.Crm.Application.Platform.EntityProxy::GetPropertyValue(string name)
0x6e7c0  stloc.s  7
0x6e7c2  leave.s  loc_6E82F
0x6e7c4  ldloc.s  4
0x6e7c6  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x6e7cb  brtrue.s loc_6E792
0x6e7cd  leave.s  loc_6E7DB
0x6e7cf  ldloc.s  4
0x6e7d1  brfalse.s loc_6E7DA
0x6e7d3  ldloc.s  4
0x6e7d5  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x6e7da  endfinally
0x6e7db  ldc.i4.1
0x6e7dc  ldstr    aCouldNotFindRi// "Could not find ribbon customization ent"...
0x6e7e1  call     void Microsoft.Crm.Diagnostics.Debug::AssertEx(bool assert, string message)
0x6e7e6  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x6e7eb  stloc.s  8
0x6e7ed  ldloca.s 8
0x6e7ef  constrained. [mscorlib]System.Guid
0x6e7f5  callvirt instance string [mscorlib]System.Object::ToString()
0x6e7fa  ret
0x6e7fb  ldloc.2
0x6e7fc  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.Crm.Application.Platform.Entity>::get_Count()
0x6e801  ldc.i4.1
0x6e802  ceq
0x6e804  ldstr    aThereShouldBeO// "There should be only one entry for comp"...
0x6e809  ldc.i4.1
0x6e80a  newarr   [mscorlib]System.Object
0x6e80f  dup
0x6e810  ldc.i4.0
0x6e811  ldarg.0
0x6e812  box      [mscorlib]System.Int32
0x6e817  stelem.ref
0x6e818  call     void Microsoft.Crm.Diagnostics.Debug::AssertEx(bool assert, string message, object[] args)
0x6e81d  ldloc.2
0x6e81e  ldc.i4.0
0x6e81f  callvirt instance var<u1> class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.Crm.Application.Platform.Entity>::get_Item(!!T0)
0x6e824  ldstr    aObjectid_0// "objectid"
0x6e829  callvirt instance string Microsoft.Crm.Application.Platform.EntityProxy::GetPropertyValue(string name)
0x6e82e  ret
0x6e82f  ldloc.s  7
0x6e831  ret
```
