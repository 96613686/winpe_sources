# Microsoft.Crm.Workflow.Services.AsyncExpressionService::GetEntityProperty

- ea: `0x3450`
- end: `0x34a5`
- name: `Microsoft.Crm.Workflow.Services.AsyncExpressionService::GetEntityProperty`
- size: `85`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x3450`
- `0x3600`

## pseudocode

```c

```

## disassembly

```asm
0x3450  ldarg.0
0x3451  ldarg.1
0x3452  ldarg.2
0x3453  call     instance void [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.Services.ExpressionServiceBase::GetEntityProperty(class [System.Activities]System.Activities.ActivityContext, class [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.Activities.GetEntityProperty)
0x3458  ldarg.2
0x3459  callvirt instance class [System.Activities]System.Activities.InArgument`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity> [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.Activities.GetEntityProperty::get_Entity()
0x345e  ldarg.1
0x345f  callvirt instance var<u1> class [System.Activities]System.Activities.InArgument`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::Get(!!T0)
0x3464  stloc.0
0x3465  ldarg.2
0x3466  callvirt instance class [System.Activities]System.Activities.InArgument`1<string> [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.Activities.GetEntityProperty::get_Attribute()
0x346b  ldarg.1
0x346c  callvirt instance var<u1> class [System.Activities]System.Activities.InArgument`1<string>::Get(!!T0)
0x3471  stloc.1
0x3472  ldloc.0
0x3473  brfalse.s loc_34A4
0x3475  ldloc.0
0x3476  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Id()
0x347b  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x3480  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x3485  brfalse.s loc_34A4
0x3487  ldarg.1
0x3488  callvirt T0x2B000005
0x348d  ldloc.0
0x348e  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_LogicalName()
0x3493  ldloc.0
0x3494  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Id()
0x3499  ldloc.1
0x349a  newobj   instance void [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.WaitSubscription::.ctor(string, valuetype [mscorlib]System.Guid, string)
0x349f  callvirt instance void Microsoft.Crm.Workflow.Services.WaitSubscriptionService::set_SubscriptionToRegister(class [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.WaitSubscription value)
0x34a4  ret
```
