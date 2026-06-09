# Microsoft.Crm.ObjectModel.RetrieveDependenciesForExport::PrepareJoinQueryExpression

- ea: `0x16c9b0`
- end: `0x16cac1`
- name: `Microsoft.Crm.ObjectModel.RetrieveDependenciesForExport::PrepareJoinQueryExpression`
- size: `273`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x16c940`

## string_xrefs

- `0x16ca91`: `componenttype`
- `0x16c9cb`: `requiredcomponentobjectid`
- `0x16ca47`: `requiredcomponentobjectid`
- `0x16c9d3`: `requiredcomponenttype`
- `0x16c9f3`: `dependentcomponentobjectid`
- `0x16ca2a`: `dependentcomponentobjectid`
- `0x16c9fb`: `dependentcomponenttype`
- `0x16ca0b`: `dependentcomponentbasesolutionid`
- `0x16ca03`: `dependentcomponentparentid`
- `0x16c9db`: `requiredcomponentparentid`
- `0x16c9e3`: `requiredcomponentbasesolutionid`
- `0x16ca14`: `requiredcomponentintroducedversion`
- `0x16ca20`: `SolutionComponent`
- `0x16ca3d`: `SolutionComponent`
- `0x16ca31`: `DependentSolutionComponent`
- `0x16ca4e`: `RequiredSolutionComponent`

## pseudocode

```c

```

## disassembly

```asm
0x16c9b0  ldstr    aDependency_0// "Dependency"
0x16c9b5  ldarg.2
0x16c9b6  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext)
0x16c9bb  stloc.0
0x16c9bc  ldloc.0
0x16c9bd  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x16c9c2  ldc.i4.s 0xA
0x16c9c4  newarr   [mscorlib]System.String
0x16c9c9  dup
0x16c9ca  ldc.i4.0
0x16c9cb  ldstr    aRequiredcompon// "requiredcomponentobjectid"
0x16c9d0  stelem.ref
0x16c9d1  dup
0x16c9d2  ldc.i4.1
0x16c9d3  ldstr    aRequiredcompon_0// "requiredcomponenttype"
0x16c9d8  stelem.ref
0x16c9d9  dup
0x16c9da  ldc.i4.2
0x16c9db  ldstr    aRequiredcompon_11// "requiredcomponentparentid"
0x16c9e0  stelem.ref
0x16c9e1  dup
0x16c9e2  ldc.i4.3
0x16c9e3  ldstr    aRequiredcompon_12// "requiredcomponentbasesolutionid"
0x16c9e8  stelem.ref
0x16c9e9  dup
0x16c9ea  ldc.i4.4
0x16c9eb  ldstr    aDependencytype// "dependencytype"
0x16c9f0  stelem.ref
0x16c9f1  dup
0x16c9f2  ldc.i4.5
0x16c9f3  ldstr    aDependentcompo// "dependentcomponentobjectid"
0x16c9f8  stelem.ref
0x16c9f9  dup
0x16c9fa  ldc.i4.6
0x16c9fb  ldstr    aDependentcompo_0// "dependentcomponenttype"
0x16ca00  stelem.ref
0x16ca01  dup
0x16ca02  ldc.i4.7
0x16ca03  ldstr    aDependentcompo_4// "dependentcomponentparentid"
0x16ca08  stelem.ref
0x16ca09  dup
0x16ca0a  ldc.i4.8
0x16ca0b  ldstr    aDependentcompo_3// "dependentcomponentbasesolutionid"
0x16ca10  stelem.ref
0x16ca11  dup
0x16ca12  ldc.i4.s 9
0x16ca14  ldstr    aRequiredcompon_13// "requiredcomponentintroducedversion"
0x16ca19  stelem.ref
0x16ca1a  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumns(string[])
0x16ca1f  ldloc.0
0x16ca20  ldstr    aSolutioncompon// "SolutionComponent"
0x16ca25  ldstr    aObjectid// "objectid"
0x16ca2a  ldstr    aDependentcompo// "dependentcomponentobjectid"
0x16ca2f  ldc.i4.0
0x16ca30  ldc.i4.0
0x16ca31  ldstr    aDependentsolut// "DependentSolutionComponent"
0x16ca36  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.LinkEntityExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::AddLinkEntity(string, string, string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.JoinOperator, string)
0x16ca3b  stloc.1
0x16ca3c  ldloc.0
0x16ca3d  ldstr    aSolutioncompon// "SolutionComponent"
0x16ca42  ldstr    aObjectid// "objectid"
0x16ca47  ldstr    aRequiredcompon// "requiredcomponentobjectid"
0x16ca4c  ldc.i4.0
0x16ca4d  ldc.i4.1
0x16ca4e  ldstr    aRequiredsoluti// "RequiredSolutionComponent"
0x16ca53  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.LinkEntityExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::AddLinkEntity(string, string, string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.JoinOperator, string)
0x16ca58  stloc.2
0x16ca59  ldloc.2
0x16ca5a  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.LinkEntityExpression::get_LinkCriteria()
0x16ca5f  ldstr    aSolutionid// "solutionid"
0x16ca64  ldc.i4.0
0x16ca65  ldarg.1
0x16ca66  box      [mscorlib]System.Guid
0x16ca6b  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x16ca70  pop
0x16ca71  ldloc.0
0x16ca72  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x16ca77  ldloc.1
0x16ca78  ldstr    aSolutionid// "solutionid"
0x16ca7d  ldc.i4.0
0x16ca7e  ldarg.1
0x16ca7f  box      [mscorlib]System.Guid
0x16ca84  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.LinkEntityExpression, string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x16ca89  pop
0x16ca8a  ldloc.0
0x16ca8b  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x16ca90  ldloc.1
0x16ca91  ldstr    aComponenttype// "componenttype"
0x16ca96  ldc.i4.0
0x16ca97  ldc.i4.s 0x42
0x16ca99  box      [mscorlib]System.Int32
0x16ca9e  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.LinkEntityExpression, string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x16caa3  pop
0x16caa4  ldloc.0
0x16caa5  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x16caaa  ldloc.2
0x16caab  ldstr    aObjectid// "objectid"
0x16cab0  ldc.i4.s 0xC
0x16cab2  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.LinkEntityExpression, string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator)
0x16cab7  pop
0x16cab8  ldloc.0
0x16cab9  ldc.i4.1
0x16caba  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::set_Distinct(bool)
0x16cabf  ldloc.0
0x16cac0  ret
```
