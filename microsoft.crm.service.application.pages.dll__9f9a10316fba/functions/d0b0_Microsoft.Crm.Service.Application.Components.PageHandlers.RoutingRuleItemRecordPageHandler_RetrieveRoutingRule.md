# Microsoft.Crm.Service.Application.Components.PageHandlers.RoutingRuleItemRecordPageHandler::RetrieveRoutingRuleStateCode

- ea: `0xd0b0`
- end: `0xd14e`
- name: `Microsoft.Crm.Service.Application.Components.PageHandlers.RoutingRuleItemRecordPageHandler::RetrieveRoutingRuleStateCode`
- size: `158`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0xcfb0`

## callees

- `0xd0b0`

## pseudocode

```c

```

## disassembly

```asm
0xd0b0  ldstr    aRoutingrule// "routingrule"
0xd0b5  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::.ctor(string)
0xd0ba  stloc.0
0xd0bb  ldloc.0
0xd0bc  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::get_ColumnSet()
0xd0c1  ldstr    aStatecode// "statecode"
0xd0c6  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet::AddColumn(string)
0xd0cb  ldloc.0
0xd0cc  ldstr    aRoutingruleite_1// "routingruleitem"
0xd0d1  ldstr    aRoutingruleid// "routingruleid"
0xd0d6  ldstr    aRoutingruleid// "routingruleid"
0xd0db  ldc.i4.0
0xd0dc  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.LinkEntity [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::AddLink(string, string, string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.JoinOperator)
0xd0e1  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.LinkEntity::get_LinkCriteria()
0xd0e6  ldstr    aRoutingruleite_2// "routingruleitemid"
0xd0eb  ldc.i4.0
0xd0ec  ldc.i4.1
0xd0ed  newarr   [mscorlib]System.Object
0xd0f2  dup
0xd0f3  ldc.i4.0
0xd0f4  ldarg.1
0xd0f5  stelem.ref
0xd0f6  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object[])
0xd0fb  ldloc.0
0xd0fc  ldarg.0
0xd0fd  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_CurrentType()
0xd102  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::get_Context()
0xd107  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ApplicationEntityCollection [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.DataSource::RetrieveMultiple(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xd10c  stloc.1
0xd10d  ldloc.1
0xd10e  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity>::get_Count()
0xd113  ldc.i4.0
0xd114  ble.s    loc_D14C
0xd116  ldloc.1
0xd117  ldc.i4.0
0xd118  callvirt instance var<u1> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity>::get_Item(!!T0)
0xd11d  stloc.2
0xd11e  ldloc.2
0xd11f  brfalse.s loc_D14C
0xd121  ldloc.2
0xd122  ldstr    aStatecode// "statecode"
0xd127  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0xd12c  brfalse.s loc_D14C
0xd12e  ldloc.2
0xd12f  ldstr    aStatecode// "statecode"
0xd134  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0xd139  callvirt instance string [mscorlib]System.Object::ToString()
0xd13e  ldstr    aActive// "Active"
0xd143  call     bool [mscorlib]System.String::op_Equality(string, string)
0xd148  brfalse.s loc_D14C
0xd14a  ldc.i4.1
0xd14b  ret
0xd14c  ldc.i4.0
0xd14d  ret
```
