# Microsoft.Crm.Workflow.WorkflowLogCachePersistentStrategy::.ctor

- ea: `0x2e90`
- end: `0x2eb4`
- name: `Microsoft.Crm.Workflow.WorkflowLogCachePersistentStrategy::.ctor`
- size: `36`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x2fe0`

## pseudocode

```c

```

## disassembly

```asm
0x2e90  ldarg.0
0x2e91  newobj   instance void class [System]System.Collections.Generic.Queue`1<class Microsoft.Crm.Workflow.WorkflowLogDescriptor>::.ctor()
0x2e96  stfld    class [System]System.Collections.Generic.Queue`1<class Microsoft.Crm.Workflow.WorkflowLogDescriptor> Microsoft.Crm.Workflow.WorkflowLogCachePersistentStrategy::operations
0x2e9b  ldarg.0
0x2e9c  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Workflow.WorkflowLogDescriptor>::.ctor()
0x2ea1  stfld    class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Workflow.WorkflowLogDescriptor> Microsoft.Crm.Workflow.WorkflowLogCachePersistentStrategy::logOperation
0x2ea6  ldarg.0
0x2ea7  call     instance void [mscorlib]System.Object::.ctor()
0x2eac  ldarg.0
0x2ead  ldarg.1
0x2eae  stfld    class Microsoft.Crm.Workflow.WorkflowContext Microsoft.Crm.Workflow.WorkflowLogCachePersistentStrategy::_context
0x2eb3  ret
```
