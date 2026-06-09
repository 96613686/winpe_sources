# Microsoft.Crm.Workflow.WorkflowLogDescriptor::.ctor

- ea: `0x2e20`
- end: `0x2e35`
- name: `Microsoft.Crm.Workflow.WorkflowLogDescriptor::.ctor`
- size: `21`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x2ec0`

## pseudocode

```c

```

## disassembly

```asm
0x2e20  ldarg.0
0x2e21  call     instance void [mscorlib]System.Object::.ctor()
0x2e26  ldarg.0
0x2e27  ldarg.1
0x2e28  stfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity Microsoft.Crm.Workflow.WorkflowLogDescriptor::_entity
0x2e2d  ldarg.0
0x2e2e  ldarg.2
0x2e2f  stfld    valuetype Microsoft.Crm.Workflow.OperationType Microsoft.Crm.Workflow.WorkflowLogDescriptor::_operation
0x2e34  ret
```
