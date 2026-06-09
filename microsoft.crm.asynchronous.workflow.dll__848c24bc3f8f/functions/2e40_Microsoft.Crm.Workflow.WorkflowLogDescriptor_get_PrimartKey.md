# Microsoft.Crm.Workflow.WorkflowLogDescriptor::get_PrimartKey

- ea: `0x2e40`
- end: `0x2e4c`
- name: `Microsoft.Crm.Workflow.WorkflowLogDescriptor::get_PrimartKey`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## pseudocode

```c

```

## disassembly

```asm
0x2e40  ldarg.0
0x2e41  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity Microsoft.Crm.Workflow.WorkflowLogDescriptor::_entity
0x2e46  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Id()
0x2e4b  ret
```
