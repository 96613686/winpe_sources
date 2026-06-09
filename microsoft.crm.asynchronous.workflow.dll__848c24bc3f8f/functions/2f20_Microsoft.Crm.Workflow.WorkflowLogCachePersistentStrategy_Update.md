# Microsoft.Crm.Workflow.WorkflowLogCachePersistentStrategy::Update

- ea: `0x2f20`
- end: `0x2f29`
- name: `Microsoft.Crm.Workflow.WorkflowLogCachePersistentStrategy::Update`
- size: `9`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callees

- `0x2ec0`

## pseudocode

```c

```

## disassembly

```asm
0x2f20  ldarg.0
0x2f21  ldarg.1
0x2f22  ldc.i4.1
0x2f23  call     instance void Microsoft.Crm.Workflow.WorkflowLogCachePersistentStrategy::Enqueue(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity entity, valuetype Microsoft.Crm.Workflow.OperationType operation)
0x2f28  ret
```
