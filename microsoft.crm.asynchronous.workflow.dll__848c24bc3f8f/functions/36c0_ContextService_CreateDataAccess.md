# ContextService::CreateDataAccess

- ea: `0x36c0`
- end: `0x36cd`
- name: `ContextService::CreateDataAccess`
- size: `13`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task`

## callees

- `0x2290`
- `0x3660`

## pseudocode

```c

```

## disassembly

```asm
0x36c0  ldarg.0
0x36c1  ldarg.1
0x36c2  call     instance class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration ContextService::GetOrganizationConfiguration(valuetype [mscorlib]System.Guid instanceId)
0x36c7  newobj   instance void Microsoft.Crm.Workflow.WorkflowDataAccess::.ctor(class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration config)
0x36cc  ret
```
