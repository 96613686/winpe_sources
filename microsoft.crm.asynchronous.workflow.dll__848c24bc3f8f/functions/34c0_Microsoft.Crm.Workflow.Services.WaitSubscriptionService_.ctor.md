# Microsoft.Crm.Workflow.Services.WaitSubscriptionService::.ctor

- ea: `0x34c0`
- end: `0x34e5`
- name: `Microsoft.Crm.Workflow.Services.WaitSubscriptionService::.ctor`
- size: `37`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x3c0`
- `0x6e0`

## pseudocode

```c

```

## disassembly

```asm
0x34c0  ldarg.0
0x34c1  call     instance void [mscorlib]System.Object::.ctor()
0x34c6  ldarg.1
0x34c7  box      [mscorlib]System.Guid
0x34cc  ldstr    aWorkflowinstan// "workflowInstanceId"
0x34d1  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x34d6  ldarg.0
0x34d7  ldarg.1
0x34d8  stfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Workflow.Services.WaitSubscriptionService::_workflowInstanceId
0x34dd  ldarg.0
0x34de  ldarg.2
0x34df  stfld    class [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.IWorkflowInstanceService Microsoft.Crm.Workflow.Services.WaitSubscriptionService::_instanceService
0x34e4  ret
```
