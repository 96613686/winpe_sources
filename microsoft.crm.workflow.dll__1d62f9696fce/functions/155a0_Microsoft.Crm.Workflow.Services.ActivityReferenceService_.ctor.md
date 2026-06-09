# Microsoft.Crm.Workflow.Services.ActivityReferenceService::.ctor

- ea: `0x155a0`
- end: `0x155c5`
- name: `Microsoft.Crm.Workflow.Services.ActivityReferenceService::.ctor`
- size: `37`
- prototype: ``
- caller_count: `5`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x51a0`
- `0x10c20`
- `0x120a0`
- `0x12360`
- `0x14f40`

## callees

- `0x8f40`
- `0x14760`
- `0x1b250`

## pseudocode

```c

```

## disassembly

```asm
0x155a0  ldarg.0
0x155a1  ldarg.1
0x155a2  call     instance void Microsoft.Crm.Workflow.Services.ActivityServiceBase::.ctor(class Microsoft.Crm.Workflow.ICommonWorkflowContext context)
0x155a7  ldarg.0
0x155a8  ldarg.1
0x155a9  newobj   instance void Microsoft.Crm.Workflow.AsyncCustomActivityLoaderDirect::.ctor(class Microsoft.Crm.Workflow.ICommonWorkflowContext context)
0x155ae  stfld    class Microsoft.Crm.Workflow.ObjectModel.ICustomActivityLoader Microsoft.Crm.Workflow.Services.ActivityReferenceService::_activityLoader
0x155b3  ldarg.0
0x155b4  ldarg.0
0x155b5  ldfld    class Microsoft.Crm.Workflow.ObjectModel.ICustomActivityLoader Microsoft.Crm.Workflow.Services.ActivityReferenceService::_activityLoader
0x155ba  newobj   instance void Microsoft.Crm.Workflow.ObjectModel.WorkflowAssemblyResolverHelper::.ctor(class Microsoft.Crm.Workflow.ObjectModel.ICustomActivityLoader activityLoader)
0x155bf  stfld    class Microsoft.Crm.Workflow.ObjectModel.WorkflowAssemblyResolverHelper Microsoft.Crm.Workflow.Services.ActivityReferenceService::_resolverHelper
0x155c4  ret
```
