# Microsoft.Crm.Application.Platform.SolutionAdapter::AppendPluginAssembly

- ea: `0x6f070`
- end: `0x6f132`
- name: `Microsoft.Crm.Application.Platform.SolutionAdapter::AppendPluginAssembly`
- size: `194`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x6eb80`

## callees

- `0x57a30`
- `0x59800`
- `0x6e850`
- `0x6f070`

## string_xrefs

- `0x6f0e4`: `pluginassembly`
- `0x6f09c`: `componenttype`
- `0x6f0d1`: `componenttype`
- `0x6f070`: `solutioncomponent`
- `0x6f084`: `solutioncomponentid`
- `0x6f0ee`: `pluginassemblyid`

## pseudocode

```c

```

## disassembly

```asm
0x6f070  ldstr    aSolutioncompon// "solutioncomponent"
0x6f075  newobj   instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryExpression::.ctor(string)
0x6f07a  stloc.0
0x6f07b  ldloc.0
0x6f07c  ldc.i4.5
0x6f07d  newarr   [mscorlib]System.String
0x6f082  dup
0x6f083  ldc.i4.0
0x6f084  ldstr    aSolutioncompon_0// "solutioncomponentid"
0x6f089  stelem.ref
0x6f08a  dup
0x6f08b  ldc.i4.1
0x6f08c  ldstr    aSolutionid_0// "solutionid"
0x6f091  stelem.ref
0x6f092  dup
0x6f093  ldc.i4.2
0x6f094  ldstr    aIsmetadata// "ismetadata"
0x6f099  stelem.ref
0x6f09a  dup
0x6f09b  ldc.i4.3
0x6f09c  ldstr    aComponenttype// "componenttype"
0x6f0a1  stelem.ref
0x6f0a2  dup
0x6f0a3  ldc.i4.4
0x6f0a4  ldstr    aObjectid_0// "objectid"
0x6f0a9  stelem.ref
0x6f0aa  newobj   instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ColumnSet::.ctor(string[])
0x6f0af  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryBase::set_ColumnSet(class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ColumnSetBase)
0x6f0b4  ldloc.0
0x6f0b5  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryExpression::get_Criteria()
0x6f0ba  ldstr    aSolutionid_0// "solutionid"
0x6f0bf  ldc.i4.0
0x6f0c0  ldarg.2
0x6f0c1  box      [mscorlib]System.Guid
0x6f0c6  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ConditionOperator, object)
0x6f0cb  ldloc.0
0x6f0cc  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryExpression::get_Criteria()
0x6f0d1  ldstr    aComponenttype// "componenttype"
0x6f0d6  ldc.i4.0
0x6f0d7  ldc.i4.s 0x5B
0x6f0d9  box      [mscorlib]System.Int32
0x6f0de  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ConditionOperator, object)
0x6f0e3  ldloc.0
0x6f0e4  ldstr    aPluginassembly// "pluginassembly"
0x6f0e9  ldstr    aObjectid_0// "objectid"
0x6f0ee  ldstr    aPluginassembly_0// "pluginassemblyid"
0x6f0f3  ldc.i4.0
0x6f0f4  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.LinkEntity [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryExpression::AddLink(string, string, string, valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.JoinOperator)
0x6f0f9  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.LinkEntity::get_LinkCriteria()
0x6f0fe  ldstr    aIshidden// "ishidden"
0x6f103  ldc.i4.1
0x6f104  ldc.i4.1
0x6f105  box      [mscorlib]System.Boolean
0x6f10a  newobj   instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ConditionExpression::.ctor(string, valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ConditionOperator, object)
0x6f10f  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression::AddCondition(class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ConditionExpression)
0x6f114  ldloc.0
0x6f115  ldarg.0
0x6f116  call     instance class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext Microsoft.Crm.Application.Platform.SolutionAdapter::get_Context()
0x6f11b  call     class Microsoft.Crm.Application.Platform.ApplicationEntityCollection Microsoft.Crm.Application.Platform.DataSource::RetrieveMultiple(class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryExpression query, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x6f120  stloc.1
0x6f121  ldloc.1
0x6f122  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.Crm.Application.Platform.Entity>::get_Count()
0x6f127  ldc.i4.0
0x6f128  ble.s    loc_6F131
0x6f12a  ldarg.1
0x6f12b  ldloc.1
0x6f12c  callvirt instance void Microsoft.Crm.Application.Platform.ApplicationEntityCollection::AddRange(class [mscorlib]System.Collections.ICollection entities)
0x6f131  ret
```
