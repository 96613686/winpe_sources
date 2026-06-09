# Microsoft.Crm.Workflow.Services.WaitSubscriptionService::UnregisterAllListeners_0

- ea: `0x35b0`
- end: `0x35e4`
- name: `Microsoft.Crm.Workflow.Services.WaitSubscriptionService::UnregisterAllListeners_0`
- size: `52`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x6e0`
- `0x35a0`

## callees

- `0x1370`
- `0x1690`
- `0x1760`
- `0x35b0`

## pseudocode

```c

```

## disassembly

```asm
0x35b0  ldarg.0
0x35b1  ldfld    class [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.IWorkflowInstanceService Microsoft.Crm.Workflow.Services.WaitSubscriptionService::_instanceService
0x35b6  ldarg.0
0x35b7  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Workflow.Services.WaitSubscriptionService::_workflowInstanceId
0x35bc  callvirt instance class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.IWorkflowInstanceService::GetOrganizationConfiguration(valuetype [mscorlib]System.Guid)
0x35c1  newobj   instance void Microsoft.Crm.Workflow.WaitSubscriptionDataAccess::.ctor(class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration config)
0x35c6  stloc.0
0x35c7  ldarg.1
0x35c8  brfalse.s loc_35D7
0x35ca  ldloc.0
0x35cb  ldarg.0
0x35cc  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Workflow.Services.WaitSubscriptionService::_workflowInstanceId
0x35d1  callvirt instance void Microsoft.Crm.Workflow.WaitSubscriptionDataAccess::TryUnsubscribeAll(valuetype [mscorlib]System.Guid workflowInstanceId)
0x35d6  ret
0x35d7  ldloc.0
0x35d8  ldarg.0
0x35d9  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Workflow.Services.WaitSubscriptionService::_workflowInstanceId
0x35de  callvirt instance void Microsoft.Crm.Workflow.WaitSubscriptionDataAccess::UnsubscribeAll(valuetype [mscorlib]System.Guid workflowInstanceId)
0x35e3  ret
```
