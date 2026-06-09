# Microsoft.Crm.Workflow.Services.WaitSubscriptionService::RegisterListener

- ea: `0x34f0`
- end: `0x3553`
- name: `Microsoft.Crm.Workflow.Services.WaitSubscriptionService::RegisterListener`
- size: `99`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x1370`
- `0x1390`
- `0x34f0`

## pseudocode

```c

```

## disassembly

```asm
0x34f0  ldarg.2
0x34f1  ldstr    aEntityname// "entityName"
0x34f6  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x34fb  ldarg.1
0x34fc  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x3501  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x3506  brfalse.s loc_3513
0x3508  ldstr    aQueueidMustBeE// "queueId must be empty."
0x350d  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmArgumentException::.ctor(string)
0x3512  throw
0x3513  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.SequentialGuid::CreateGuid()
0x3518  stloc.0
0x3519  ldarg.3
0x351a  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x351f  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x3524  brfalse.s loc_3551
0x3526  ldarg.0
0x3527  ldfld    class [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.IWorkflowInstanceService Microsoft.Crm.Workflow.Services.WaitSubscriptionService::_instanceService
0x352c  ldarg.0
0x352d  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Workflow.Services.WaitSubscriptionService::_workflowInstanceId
0x3532  callvirt instance class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.IWorkflowInstanceService::GetOrganizationConfiguration(valuetype [mscorlib]System.Guid)
0x3537  newobj   instance void Microsoft.Crm.Workflow.WaitSubscriptionDataAccess::.ctor(class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration config)
0x353c  ldloc.0
0x353d  ldarg.0
0x353e  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Workflow.Services.WaitSubscriptionService::_workflowInstanceId
0x3543  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x3548  ldarg.2
0x3549  ldarg.3
0x354a  ldarg.s  4
0x354c  callvirt instance void Microsoft.Crm.Workflow.WaitSubscriptionDataAccess::Subscribe(valuetype [mscorlib]System.Guid subscriptionId, valuetype [mscorlib]System.Guid workflowInstanceId, valuetype [mscorlib]System.Guid queueId, string entityName, valuetype [mscorlib]System.Guid entityId, string attributeName)
0x3551  ldloc.0
0x3552  ret
```
