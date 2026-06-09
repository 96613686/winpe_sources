# Microsoft.Crm.Common.Application.Platform.ServiceCommands.RetrieveQueueByQueueItemCommand::.ctor

- ea: `0x6930`
- end: `0x6a44`
- name: `Microsoft.Crm.Common.Application.Platform.ServiceCommands.RetrieveQueueByQueueItemCommand::.ctor`
- size: `276`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x48d0`
- `0x4980`

## callees

- `0x6930`

## pseudocode

```c

```

## disassembly

```asm
0x6930  ldarg.0
0x6931  ldc.i4.1
0x6932  stfld    bool Microsoft.Crm.Common.Application.Platform.ServiceCommands.RetrieveQueueByQueueItemCommand::_queryValid
0x6937  ldarg.0
0x6938  ldstr    aQueue// "queue"
0x693d  ldarg.s  4
0x693f  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x6944  ldarg.s  4
0x6946  call     instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ServiceCommands.RetrieveMultipleCommand::.ctor(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x694b  ldstr    aQueueitem// "queueitem"
0x6950  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::.ctor(string)
0x6955  dup
0x6956  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::get_ColumnSet()
0x695b  ldstr    aQueueid// "queueid"
0x6960  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet::AddColumn(string)
0x6965  dup
0x6966  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::get_Criteria()
0x696b  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression::get_Conditions()
0x6970  ldstr    aObjectid// "objectid"
0x6975  ldc.i4.0
0x6976  ldarg.1
0x6977  box      [mscorlib]System.Guid
0x697c  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression::.ctor(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x6981  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression>::Add(var<u1>)
0x6986  dup
0x6987  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::get_Criteria()
0x698c  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression::get_Conditions()
0x6991  ldstr    aObjecttypecode// "objecttypecode"
0x6996  ldc.i4.0
0x6997  ldarg.2
0x6998  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression::.ctor(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x699d  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression>::Add(var<u1>)
0x69a2  ldarg.s  4
0x69a4  newobj   instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ServiceCommands.RetrieveMultipleCommand::.ctor(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x69a9  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ApplicationEntityCollection [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ServiceCommands.RetrieveMultipleCommand::Execute()
0x69ae  dup
0x69af  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity>::get_Count()
0x69b4  brtrue.s loc_69BD
0x69b6  ldarg.0
0x69b7  ldc.i4.0
0x69b8  stfld    bool Microsoft.Crm.Common.Application.Platform.ServiceCommands.RetrieveQueueByQueueItemCommand::_queryValid
0x69bd  dup
0x69be  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity>::get_Count()
0x69c3  newarr   [mscorlib]System.String
0x69c8  stloc.0
0x69c9  ldc.i4.0
0x69ca  stloc.1
0x69cb  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity>::GetEnumerator()
0x69d0  stloc.2
0x69d1  br.s     loc_69F6
0x69d3  ldloc.2
0x69d4  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity>::get_Current()
0x69d9  ldstr    aQueueid// "queueid"
0x69de  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x69e3  isinst   [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.LookupValue
0x69e8  stloc.3
0x69e9  ldloc.0
0x69ea  ldloc.1
0x69eb  dup
0x69ec  ldc.i4.1
0x69ed  add
0x69ee  stloc.1
0x69ef  ldloc.3
0x69f0  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.LookupValue::get_ID()
0x69f5  stelem.ref
0x69f6  ldloc.2
0x69f7  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x69fc  brtrue.s loc_69D3
0x69fe  leave.s  loc_6A0A
0x6a00  ldloc.2
0x6a01  brfalse.s loc_6A09
0x6a03  ldloc.2
0x6a04  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x6a09  endfinally
0x6a0a  ldarg.3
0x6a0b  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.OrderExpression> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::get_Orders()
0x6a10  ldstr    aName// "name"
0x6a15  ldc.i4.0
0x6a16  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.OrderExpression::.ctor(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.OrderType)
0x6a1b  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.OrderExpression>::Add(var<u1>)
0x6a20  ldarg.3
0x6a21  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::get_Criteria()
0x6a26  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression::get_Conditions()
0x6a2b  ldstr    aQueueid// "queueid"
0x6a30  ldc.i4.8
0x6a31  ldloc.0
0x6a32  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression::.ctor(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object[])
0x6a37  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression>::Add(var<u1>)
0x6a3c  ldarg.0
0x6a3d  ldarg.3
0x6a3e  call     instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ServiceCommands.RetrieveMultipleCommand::CreateQueryRequest(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryBase)
0x6a43  ret
```
