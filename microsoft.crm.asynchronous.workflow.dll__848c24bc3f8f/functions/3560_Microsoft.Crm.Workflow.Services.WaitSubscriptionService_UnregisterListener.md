# Microsoft.Crm.Workflow.Services.WaitSubscriptionService::UnregisterListener

- ea: `0x3560`
- end: `0x3593`
- name: `Microsoft.Crm.Workflow.Services.WaitSubscriptionService::UnregisterListener`
- size: `51`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x1370`
- `0x16e0`

## pseudocode

```c

```

## disassembly

```asm
0x3560  ldarg.1
0x3561  ldstr    aSubscriptionid_0// "subscriptionId"
0x3566  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfGuidEmpty(valuetype [mscorlib]System.Guid, string)
0x356b  ldarg.1
0x356c  ldstr    aWorkflowinstan// "workflowInstanceId"
0x3571  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfGuidEmpty(valuetype [mscorlib]System.Guid, string)
0x3576  ldarg.0
0x3577  ldfld    class [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.IWorkflowInstanceService Microsoft.Crm.Workflow.Services.WaitSubscriptionService::_instanceService
0x357c  ldarg.0
0x357d  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Workflow.Services.WaitSubscriptionService::_workflowInstanceId
0x3582  callvirt instance class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.IWorkflowInstanceService::GetOrganizationConfiguration(valuetype [mscorlib]System.Guid)
0x3587  newobj   instance void Microsoft.Crm.Workflow.WaitSubscriptionDataAccess::.ctor(class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration config)
0x358c  ldarg.1
0x358d  callvirt instance void Microsoft.Crm.Workflow.WaitSubscriptionDataAccess::Unsubscribe(valuetype [mscorlib]System.Guid subscriptionId)
0x3592  ret
```
