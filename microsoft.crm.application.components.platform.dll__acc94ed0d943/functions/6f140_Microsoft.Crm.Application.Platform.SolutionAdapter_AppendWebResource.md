# Microsoft.Crm.Application.Platform.SolutionAdapter::AppendWebResource

- ea: `0x6f140`
- end: `0x6f202`
- name: `Microsoft.Crm.Application.Platform.SolutionAdapter::AppendWebResource`
- size: `194`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x6eb80`

## callees

- `0x57a30`
- `0x59800`
- `0x6e850`
- `0x6f140`

## string_xrefs

- `0x6f16c`: `componenttype`
- `0x6f1a1`: `componenttype`
- `0x6f140`: `solutioncomponent`
- `0x6f154`: `solutioncomponentid`

## pseudocode

```c

```

## disassembly

```asm
0x6f140  ldstr    aSolutioncompon// "solutioncomponent"
0x6f145  newobj   instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryExpression::.ctor(string)
0x6f14a  stloc.0
0x6f14b  ldloc.0
0x6f14c  ldc.i4.5
0x6f14d  newarr   [mscorlib]System.String
0x6f152  dup
0x6f153  ldc.i4.0
0x6f154  ldstr    aSolutioncompon_0// "solutioncomponentid"
0x6f159  stelem.ref
0x6f15a  dup
0x6f15b  ldc.i4.1
0x6f15c  ldstr    aSolutionid_0// "solutionid"
0x6f161  stelem.ref
0x6f162  dup
0x6f163  ldc.i4.2
0x6f164  ldstr    aIsmetadata// "ismetadata"
0x6f169  stelem.ref
0x6f16a  dup
0x6f16b  ldc.i4.3
0x6f16c  ldstr    aComponenttype// "componenttype"
0x6f171  stelem.ref
0x6f172  dup
0x6f173  ldc.i4.4
0x6f174  ldstr    aObjectid_0// "objectid"
0x6f179  stelem.ref
0x6f17a  newobj   instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ColumnSet::.ctor(string[])
0x6f17f  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryBase::set_ColumnSet(class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ColumnSetBase)
0x6f184  ldloc.0
0x6f185  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryExpression::get_Criteria()
0x6f18a  ldstr    aSolutionid_0// "solutionid"
0x6f18f  ldc.i4.0
0x6f190  ldarg.2
0x6f191  box      [mscorlib]System.Guid
0x6f196  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ConditionOperator, object)
0x6f19b  ldloc.0
0x6f19c  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryExpression::get_Criteria()
0x6f1a1  ldstr    aComponenttype// "componenttype"
0x6f1a6  ldc.i4.0
0x6f1a7  ldc.i4.s 0x3D
0x6f1a9  box      [mscorlib]System.Int32
0x6f1ae  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ConditionOperator, object)
0x6f1b3  ldloc.0
0x6f1b4  ldstr    aWebresource_0// "webresource"
0x6f1b9  ldstr    aObjectid_0// "objectid"
0x6f1be  ldstr    aWebresourceid// "webresourceid"
0x6f1c3  ldc.i4.0
0x6f1c4  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.LinkEntity [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryExpression::AddLink(string, string, string, valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.JoinOperator)
0x6f1c9  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.LinkEntity::get_LinkCriteria()
0x6f1ce  ldstr    aIshidden// "ishidden"
0x6f1d3  ldc.i4.1
0x6f1d4  ldc.i4.1
0x6f1d5  box      [mscorlib]System.Boolean
0x6f1da  newobj   instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ConditionExpression::.ctor(string, valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ConditionOperator, object)
0x6f1df  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression::AddCondition(class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ConditionExpression)
0x6f1e4  ldloc.0
0x6f1e5  ldarg.0
0x6f1e6  call     instance class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext Microsoft.Crm.Application.Platform.SolutionAdapter::get_Context()
0x6f1eb  call     class Microsoft.Crm.Application.Platform.ApplicationEntityCollection Microsoft.Crm.Application.Platform.DataSource::RetrieveMultiple(class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryExpression query, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x6f1f0  stloc.1
0x6f1f1  ldloc.1
0x6f1f2  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.Crm.Application.Platform.Entity>::get_Count()
0x6f1f7  ldc.i4.0
0x6f1f8  ble.s    loc_6F201
0x6f1fa  ldarg.1
0x6f1fb  ldloc.1
0x6f1fc  callvirt instance void Microsoft.Crm.Application.Platform.ApplicationEntityCollection::AddRange(class [mscorlib]System.Collections.ICollection entities)
0x6f201  ret
```
