# Microsoft.Crm.Application.Platform.SolutionAdapter::AppendSdkMessageProcessingStep

- ea: `0x6eef0`
- end: `0x6efb2`
- name: `Microsoft.Crm.Application.Platform.SolutionAdapter::AppendSdkMessageProcessingStep`
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
- `0x6eef0`

## string_xrefs

- `0x6ef1c`: `componenttype`
- `0x6ef51`: `componenttype`
- `0x6eef0`: `solutioncomponent`
- `0x6ef04`: `solutioncomponentid`

## pseudocode

```c

```

## disassembly

```asm
0x6eef0  ldstr    aSolutioncompon// "solutioncomponent"
0x6eef5  newobj   instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryExpression::.ctor(string)
0x6eefa  stloc.0
0x6eefb  ldloc.0
0x6eefc  ldc.i4.5
0x6eefd  newarr   [mscorlib]System.String
0x6ef02  dup
0x6ef03  ldc.i4.0
0x6ef04  ldstr    aSolutioncompon_0// "solutioncomponentid"
0x6ef09  stelem.ref
0x6ef0a  dup
0x6ef0b  ldc.i4.1
0x6ef0c  ldstr    aSolutionid_0// "solutionid"
0x6ef11  stelem.ref
0x6ef12  dup
0x6ef13  ldc.i4.2
0x6ef14  ldstr    aIsmetadata// "ismetadata"
0x6ef19  stelem.ref
0x6ef1a  dup
0x6ef1b  ldc.i4.3
0x6ef1c  ldstr    aComponenttype// "componenttype"
0x6ef21  stelem.ref
0x6ef22  dup
0x6ef23  ldc.i4.4
0x6ef24  ldstr    aObjectid_0// "objectid"
0x6ef29  stelem.ref
0x6ef2a  newobj   instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ColumnSet::.ctor(string[])
0x6ef2f  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryBase::set_ColumnSet(class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ColumnSetBase)
0x6ef34  ldloc.0
0x6ef35  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryExpression::get_Criteria()
0x6ef3a  ldstr    aSolutionid_0// "solutionid"
0x6ef3f  ldc.i4.0
0x6ef40  ldarg.2
0x6ef41  box      [mscorlib]System.Guid
0x6ef46  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ConditionOperator, object)
0x6ef4b  ldloc.0
0x6ef4c  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryExpression::get_Criteria()
0x6ef51  ldstr    aComponenttype// "componenttype"
0x6ef56  ldc.i4.0
0x6ef57  ldc.i4.s 0x5C
0x6ef59  box      [mscorlib]System.Int32
0x6ef5e  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ConditionOperator, object)
0x6ef63  ldloc.0
0x6ef64  ldstr    aSdkmessageproc// "sdkmessageprocessingstep"
0x6ef69  ldstr    aObjectid_0// "objectid"
0x6ef6e  ldstr    aSdkmessageproc_2// "sdkmessageprocessingstepid"
0x6ef73  ldc.i4.0
0x6ef74  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.LinkEntity [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryExpression::AddLink(string, string, string, valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.JoinOperator)
0x6ef79  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.LinkEntity::get_LinkCriteria()
0x6ef7e  ldstr    aIshidden// "ishidden"
0x6ef83  ldc.i4.1
0x6ef84  ldc.i4.1
0x6ef85  box      [mscorlib]System.Boolean
0x6ef8a  newobj   instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ConditionExpression::.ctor(string, valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ConditionOperator, object)
0x6ef8f  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression::AddCondition(class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ConditionExpression)
0x6ef94  ldloc.0
0x6ef95  ldarg.0
0x6ef96  call     instance class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext Microsoft.Crm.Application.Platform.SolutionAdapter::get_Context()
0x6ef9b  call     class Microsoft.Crm.Application.Platform.ApplicationEntityCollection Microsoft.Crm.Application.Platform.DataSource::RetrieveMultiple(class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryExpression query, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x6efa0  stloc.1
0x6efa1  ldloc.1
0x6efa2  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.Crm.Application.Platform.Entity>::get_Count()
0x6efa7  ldc.i4.0
0x6efa8  ble.s    loc_6EFB1
0x6efaa  ldarg.1
0x6efab  ldloc.1
0x6efac  callvirt instance void Microsoft.Crm.Application.Platform.ApplicationEntityCollection::AddRange(class [mscorlib]System.Collections.ICollection entities)
0x6efb1  ret
```
