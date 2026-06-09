# Microsoft.Crm.Application.Platform.SolutionAdapter::AppendOtherEntities

- ea: `0x6efc0`
- end: `0x6f061`
- name: `Microsoft.Crm.Application.Platform.SolutionAdapter::AppendOtherEntities`
- size: `161`
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
- `0x6efc0`

## string_xrefs

- `0x6efec`: `componenttype`
- `0x6f021`: `componenttype`
- `0x6efc0`: `solutioncomponent`
- `0x6efd4`: `solutioncomponentid`

## pseudocode

```c

```

## disassembly

```asm
0x6efc0  ldstr    aSolutioncompon// "solutioncomponent"
0x6efc5  newobj   instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryExpression::.ctor(string)
0x6efca  stloc.0
0x6efcb  ldloc.0
0x6efcc  ldc.i4.5
0x6efcd  newarr   [mscorlib]System.String
0x6efd2  dup
0x6efd3  ldc.i4.0
0x6efd4  ldstr    aSolutioncompon_0// "solutioncomponentid"
0x6efd9  stelem.ref
0x6efda  dup
0x6efdb  ldc.i4.1
0x6efdc  ldstr    aSolutionid_0// "solutionid"
0x6efe1  stelem.ref
0x6efe2  dup
0x6efe3  ldc.i4.2
0x6efe4  ldstr    aIsmetadata// "ismetadata"
0x6efe9  stelem.ref
0x6efea  dup
0x6efeb  ldc.i4.3
0x6efec  ldstr    aComponenttype// "componenttype"
0x6eff1  stelem.ref
0x6eff2  dup
0x6eff3  ldc.i4.4
0x6eff4  ldstr    aObjectid_0// "objectid"
0x6eff9  stelem.ref
0x6effa  newobj   instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ColumnSet::.ctor(string[])
0x6efff  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryBase::set_ColumnSet(class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ColumnSetBase)
0x6f004  ldloc.0
0x6f005  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryExpression::get_Criteria()
0x6f00a  ldstr    aSolutionid_0// "solutionid"
0x6f00f  ldc.i4.0
0x6f010  ldarg.2
0x6f011  box      [mscorlib]System.Guid
0x6f016  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ConditionOperator, object)
0x6f01b  ldloc.0
0x6f01c  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryExpression::get_Criteria()
0x6f021  ldstr    aComponenttype// "componenttype"
0x6f026  ldc.i4.0
0x6f027  ldarg.s  5
0x6f029  box      [mscorlib]System.Int32
0x6f02e  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ConditionOperator, object)
0x6f033  ldloc.0
0x6f034  ldarg.3
0x6f035  ldstr    aObjectid_0// "objectid"
0x6f03a  ldarg.s  4
0x6f03c  ldc.i4.0
0x6f03d  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.LinkEntity [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryExpression::AddLink(string, string, string, valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.JoinOperator)
0x6f042  pop
0x6f043  ldloc.0
0x6f044  ldarg.0
0x6f045  call     instance class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext Microsoft.Crm.Application.Platform.SolutionAdapter::get_Context()
0x6f04a  call     class Microsoft.Crm.Application.Platform.ApplicationEntityCollection Microsoft.Crm.Application.Platform.DataSource::RetrieveMultiple(class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryExpression query, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x6f04f  stloc.1
0x6f050  ldloc.1
0x6f051  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.Crm.Application.Platform.Entity>::get_Count()
0x6f056  ldc.i4.0
0x6f057  ble.s    loc_6F060
0x6f059  ldarg.1
0x6f05a  ldloc.1
0x6f05b  callvirt instance void Microsoft.Crm.Application.Platform.ApplicationEntityCollection::AddRange(class [mscorlib]System.Collections.ICollection entities)
0x6f060  ret
```
