# Microsoft.Crm.Common.Application.Platform.QueryDecorators.ActivityQueryDecorator::AddStateFilter

- ea: `0x6ff0`
- end: `0x71e9`
- name: `Microsoft.Crm.Common.Application.Platform.QueryDecorators.ActivityQueryDecorator::AddStateFilter`
- size: `505`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x6ef0`

## callees

- `0x6ff0`
- `0x71f0`

## string_xrefs

- `0x706b`: `serviceappointment`
- `0x7159`: `Completed`

## pseudocode

```c

```

## disassembly

```asm
0x6ff0  ldarg.0
0x6ff1  ldfld    string Microsoft.Crm.Common.Application.Platform.QueryDecorators.ActivityQueryDecorator::_stateGroup
0x6ff6  stloc.1
0x6ff7  ldloc.1
0x6ff8  ldstr    aAll_0// "all"
0x6ffd  call     bool [mscorlib]System.String::op_Equality(string, string)
0x7002  brtrue   loc_71E8
0x7007  ldloc.1
0x7008  ldstr    aActive// "active"
0x700d  call     bool [mscorlib]System.String::op_Equality(string, string)
0x7012  brtrue.s loc_7024
0x7014  ldloc.1
0x7015  ldstr    aInactive// "inactive"
0x701a  call     bool [mscorlib]System.String::op_Equality(string, string)
0x701f  brtrue   loc_7140
0x7024  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression::.ctor()
0x7029  stloc.0
0x702a  ldloc.0
0x702b  ldc.i4.1
0x702c  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression::set_FilterOperator(valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.LogicalOperator)
0x7031  ldloc.0
0x7032  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression::get_Conditions()
0x7037  ldstr    aStatecode// "statecode"
0x703c  ldc.i4.0
0x703d  ldstr    aActivitypointe// "activitypointer"
0x7042  ldc.i4.0
0x7043  stloc.3
0x7044  ldloca.s 3
0x7046  constrained. [Microsoft.Crm.Sdk.Reserved]Microsoft.Crm.Sdk.Types.ActivityPointerState
0x704c  callvirt instance string [mscorlib]System.Object::ToString()
0x7051  call     int32 [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityProxy::ConvertStateToNumber(string, string)
0x7056  box      [mscorlib]System.Int32
0x705b  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression::.ctor(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x7060  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression>::Add(var<u1>)
0x7065  ldarg.1
0x7066  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::get_EntityName()
0x706b  ldstr    aServiceappoint// "serviceappointment"
0x7070  ldc.i4.5
0x7071  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x7076  brtrue.s loc_70B1
0x7078  ldarg.1
0x7079  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::get_EntityName()
0x707e  ldstr    aAppointment// "appointment"
0x7083  ldc.i4.5
0x7084  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x7089  brtrue.s loc_70B1
0x708b  ldarg.1
0x708c  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::get_EntityName()
0x7091  ldstr    aRecurringappoi// "recurringappointmentmaster"
0x7096  ldc.i4.5
0x7097  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x709c  brtrue.s loc_70B1
0x709e  ldarg.1
0x709f  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::get_EntityName()
0x70a4  ldstr    aActivitypointe// "activitypointer"
0x70a9  ldc.i4.5
0x70aa  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x70af  brfalse.s loc_70E7
0x70b1  ldloc.0
0x70b2  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression::get_Conditions()
0x70b7  ldstr    aStatecode// "statecode"
0x70bc  ldc.i4.0
0x70bd  ldstr    aActivitypointe// "activitypointer"
0x70c2  ldc.i4.3
0x70c3  stloc.3
0x70c4  ldloca.s 3
0x70c6  constrained. [Microsoft.Crm.Sdk.Reserved]Microsoft.Crm.Sdk.Types.ActivityPointerState
0x70cc  callvirt instance string [mscorlib]System.Object::ToString()
0x70d1  call     int32 [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityProxy::ConvertStateToNumber(string, string)
0x70d6  box      [mscorlib]System.Int32
0x70db  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression::.ctor(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x70e0  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression>::Add(var<u1>)
0x70e5  br.s     loc_712E
0x70e7  ldarg.1
0x70e8  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::get_EntityName()
0x70ed  ldstr    aEmail// "email"
0x70f2  ldc.i4.5
0x70f3  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x70f8  brfalse.s loc_712E
0x70fa  ldloc.0
0x70fb  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression::get_Conditions()
0x7100  ldstr    aStatecode// "statecode"
0x7105  ldc.i4.0
0x7106  ldstr    aActivitypointe// "activitypointer"
0x710b  ldc.i4.1
0x710c  stloc.3
0x710d  ldloca.s 3
0x710f  constrained. [Microsoft.Crm.Sdk.Reserved]Microsoft.Crm.Sdk.Types.ActivityPointerState
0x7115  callvirt instance string [mscorlib]System.Object::ToString()
0x711a  call     int32 [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityProxy::ConvertStateToNumber(string, string)
0x711f  box      [mscorlib]System.Int32
0x7124  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression::.ctor(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x7129  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression>::Add(var<u1>)
0x712e  ldarg.1
0x712f  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::get_Criteria()
0x7134  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression::get_Filters()
0x7139  ldloc.0
0x713a  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression>::Add(var<u1>)
0x713f  ret
0x7140  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression::.ctor()
0x7145  stloc.0
0x7146  ldloc.0
0x7147  ldc.i4.1
0x7148  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression::set_FilterOperator(valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.LogicalOperator)
0x714d  ldloc.0
0x714e  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression::get_Conditions()
0x7153  ldstr    aStatecode// "statecode"
0x7158  ldc.i4.0
0x7159  ldstr    aCompleted// "Completed"
0x715e  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression::.ctor(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x7163  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression>::Add(var<u1>)
0x7168  ldloc.0
0x7169  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression::get_Conditions()
0x716e  ldstr    aStatecode// "statecode"
0x7173  ldc.i4.0
0x7174  ldstr    aCanceled// "Canceled"
0x7179  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression::.ctor(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x717e  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression>::Add(var<u1>)
0x7183  ldarg.1
0x7184  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::get_Criteria()
0x7189  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression::get_Filters()
0x718e  ldloc.0
0x718f  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression>::Add(var<u1>)
0x7194  ldarg.0
0x7195  ldfld    string Microsoft.Crm.Common.Application.Platform.QueryDecorators.ActivityQueryDecorator::_actualEnd
0x719a  stloc.2
0x719b  ldloc.2
0x719c  brfalse.s loc_71E8
0x719e  ldloc.2
0x719f  callvirt instance int32 [mscorlib]System.String::get_Length()
0x71a4  ldc.i4.0
0x71a5  ble.s    loc_71E8
0x71a7  ldloc.2
0x71a8  ldstr    aAll// "All"
0x71ad  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x71b2  brfalse.s loc_71E8
0x71b4  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression::.ctor()
0x71b9  stloc.s  4
0x71bb  ldloc.s  4
0x71bd  ldc.i4.0
0x71be  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression::set_FilterOperator(valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.LogicalOperator)
0x71c3  ldarg.1
0x71c4  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::get_Criteria()
0x71c9  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression::get_Filters()
0x71ce  ldloc.s  4
0x71d0  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression>::Add(var<u1>)
0x71d5  ldarg.0
0x71d6  ldloc.s  4
0x71d8  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression::get_Conditions()
0x71dd  ldstr    aActualend// "actualend"
0x71e2  ldloc.2
0x71e3  call     instance void Microsoft.Crm.Common.Application.Platform.QueryDecorators.ActivityQueryDecorator::AddDateCondition(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression> conditions, string column, string dateOperator)
0x71e8  ret
```
