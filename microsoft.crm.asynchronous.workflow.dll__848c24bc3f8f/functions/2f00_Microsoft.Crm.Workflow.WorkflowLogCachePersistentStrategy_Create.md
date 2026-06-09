# Microsoft.Crm.Workflow.WorkflowLogCachePersistentStrategy::Create

- ea: `0x2f00`
- end: `0x2f14`
- name: `Microsoft.Crm.Workflow.WorkflowLogCachePersistentStrategy::Create`
- size: `20`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x2ec0`

## pseudocode

```c

```

## disassembly

```asm
0x2f00  ldarg.1
0x2f01  call     valuetype [mscorlib]System.Guid [mscorlib]System.Guid::NewGuid()
0x2f06  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_Id(valuetype [mscorlib]System.Guid)
0x2f0b  ldarg.0
0x2f0c  ldarg.1
0x2f0d  ldc.i4.0
0x2f0e  call     instance void Microsoft.Crm.Workflow.WorkflowLogCachePersistentStrategy::Enqueue(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity entity, valuetype Microsoft.Crm.Workflow.OperationType operation)
0x2f13  ret
```
