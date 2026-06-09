# Microsoft.Crm.Common.Application.Platform.QueryDecorators.ActivityQueryDecorator::AddDateFilter

- ea: `0x6f20`
- end: `0x6fe7`
- name: `Microsoft.Crm.Common.Application.Platform.QueryDecorators.ActivityQueryDecorator::AddDateFilter`
- size: `199`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x6ef0`

## callees

- `0x6f20`
- `0x71f0`

## string_xrefs

- `0x6f48`: `scheduledend`
- `0x6f87`: `scheduledend`
- `0x6fb8`: `scheduledend`
- `0x6fd7`: `scheduledend`

## pseudocode

```c

```

## disassembly

```asm
0x6f20  ldarg.0
0x6f21  ldfld    string Microsoft.Crm.Common.Application.Platform.QueryDecorators.ActivityQueryDecorator::_dateFilter
0x6f26  stloc.0
0x6f27  ldloc.0
0x6f28  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x6f2d  brtrue.s loc_6F3C
0x6f2f  ldloc.0
0x6f30  ldstr    aAll// "All"
0x6f35  call     bool [mscorlib]System.String::op_Equality(string, string)
0x6f3a  brfalse.s loc_6F3D
0x6f3c  ret
0x6f3d  ldarg.0
0x6f3e  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata Microsoft.Crm.Common.Application.Platform.QueryDecorators.ActivityQueryDecorator::_entityMetadata
0x6f43  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IAttributeMetadataCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_AttributesByName()
0x6f48  ldstr    aScheduledend// "scheduledend"
0x6f4d  callvirt instance bool [mscorlib]System.Collections.IDictionary::Contains(object)
0x6f52  brfalse  loc_6FE6
0x6f57  ldarg.0
0x6f58  ldfld    string Microsoft.Crm.Common.Application.Platform.QueryDecorators.ActivityQueryDecorator::_stateGroup
0x6f5d  ldstr    aInactive// "inactive"
0x6f62  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x6f67  brfalse.s loc_6FE6
0x6f69  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression::.ctor()
0x6f6e  stloc.1
0x6f6f  ldloc.1
0x6f70  ldc.i4.1
0x6f71  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression::set_FilterOperator(valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.LogicalOperator)
0x6f76  ldarg.1
0x6f77  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::get_Criteria()
0x6f7c  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression::get_Filters()
0x6f81  ldloc.1
0x6f82  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression>::Add(var<u1>)
0x6f87  ldstr    aScheduledend// "scheduledend"
0x6f8c  ldc.i4.3
0x6f8d  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::get_LocalDateTimeAsString()
0x6f92  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression::.ctor(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x6f97  stloc.2
0x6f98  ldloc.1
0x6f99  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression::get_Conditions()
0x6f9e  ldloc.2
0x6f9f  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression>::Add(var<u1>)
0x6fa4  ldloc.0
0x6fa5  ldstr    aOverdue// "Overdue"
0x6faa  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x6faf  brfalse.s loc_6FC3
0x6fb1  ldarg.0
0x6fb2  ldloc.1
0x6fb3  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression::get_Conditions()
0x6fb8  ldstr    aScheduledend// "scheduledend"
0x6fbd  ldloc.0
0x6fbe  call     instance void Microsoft.Crm.Common.Application.Platform.QueryDecorators.ActivityQueryDecorator::AddDateCondition(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression> conditions, string column, string dateOperator)
0x6fc3  ldloc.0
0x6fc4  ldstr    aTomorrow// "Tomorrow"
0x6fc9  call     bool [mscorlib]System.String::op_Equality(string, string)
0x6fce  brfalse.s loc_6FE6
0x6fd0  ldarg.0
0x6fd1  ldloc.1
0x6fd2  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression::get_Conditions()
0x6fd7  ldstr    aScheduledend// "scheduledend"
0x6fdc  ldstr    aToday// "Today"
0x6fe1  call     instance void Microsoft.Crm.Common.Application.Platform.QueryDecorators.ActivityQueryDecorator::AddDateCondition(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression> conditions, string column, string dateOperator)
0x6fe6  ret
```
