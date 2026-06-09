# ContextService::.ctor

- ea: `0x3620`
- end: `0x363c`
- name: `ContextService::.ctor`
- size: `28`
- prototype: ``
- caller_count: `3`
- callee_count: `0`
- tags: `service_task`

## callers

- `0x3c0`
- `0x5d0`
- `0x6e0`

## pseudocode

```c

```

## disassembly

```asm
0x3620  ldarg.0
0x3621  call     instance void [mscorlib]System.Object::.ctor()
0x3626  ldarg.0
0x3627  ldarg.2
0x3628  stfld    valuetype [mscorlib]System.Guid ContextService::_instanceId
0x362d  ldarg.0
0x362e  ldarg.1
0x362f  stfld    class [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.WorkflowResolveOrganizationConfiguration ContextService::_organizationConfigurationResolver
0x3634  ldarg.0
0x3635  ldarg.3
0x3636  stfld    class [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.ICommonWorkflowContext ContextService::_context
0x363b  ret
```
