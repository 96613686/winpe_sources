# Microsoft.Crm.Workflow.WorkflowLogCachePersistentStrategy::Enqueue

- ea: `0x2ec0`
- end: `0x2efc`
- name: `Microsoft.Crm.Workflow.WorkflowLogCachePersistentStrategy::Enqueue`
- size: `60`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x2f00`
- `0x2f20`

## callees

- `0x2e20`
- `0x2ec0`
- `0x2f30`

## pseudocode

```c

```

## disassembly

```asm
0x2ec0  ldarg.1
0x2ec1  ldarg.2
0x2ec2  newobj   instance void Microsoft.Crm.Workflow.WorkflowLogDescriptor::.ctor(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity entity, valuetype Microsoft.Crm.Workflow.OperationType operation)
0x2ec7  stloc.0
0x2ec8  ldarg.0
0x2ec9  ldfld    class [System]System.Collections.Generic.Queue`1<class Microsoft.Crm.Workflow.WorkflowLogDescriptor> Microsoft.Crm.Workflow.WorkflowLogCachePersistentStrategy::operations
0x2ece  ldloc.0
0x2ecf  callvirt instance void class [System]System.Collections.Generic.Queue`1<class Microsoft.Crm.Workflow.WorkflowLogDescriptor>::Enqueue(var<u1>)
0x2ed4  ldarg.0
0x2ed5  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Workflow.WorkflowLogDescriptor> Microsoft.Crm.Workflow.WorkflowLogCachePersistentStrategy::logOperation
0x2eda  ldarg.1
0x2edb  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Id()
0x2ee0  ldloc.0
0x2ee1  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Workflow.WorkflowLogDescriptor>::set_Item(var<u1>, !!T0)
0x2ee6  ldarg.0
0x2ee7  ldfld    class [System]System.Collections.Generic.Queue`1<class Microsoft.Crm.Workflow.WorkflowLogDescriptor> Microsoft.Crm.Workflow.WorkflowLogCachePersistentStrategy::operations
0x2eec  callvirt instance int32 class [System]System.Collections.Generic.Queue`1<class Microsoft.Crm.Workflow.WorkflowLogDescriptor>::get_Count()
0x2ef1  ldc.i4.s 0x64
0x2ef3  blt.s    loc_2EFB
0x2ef5  ldarg.0
0x2ef6  call     instance void Microsoft.Crm.Workflow.WorkflowLogCachePersistentStrategy::Flush()
0x2efb  ret
```
