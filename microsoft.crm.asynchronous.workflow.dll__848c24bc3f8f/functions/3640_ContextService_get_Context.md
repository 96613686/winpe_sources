# ContextService::get_Context

- ea: `0x3640`
- end: `0x364c`
- name: `ContextService::get_Context`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task`

## pseudocode

```c

```

## disassembly

```asm
0x3640  ldarg.0
0x3641  ldfld    class [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.ICommonWorkflowContext ContextService::_context
0x3646  callvirt instance class [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.ILegacyWorkflowContext [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.ICommonWorkflowContext::get_LegacyContext()
0x364b  ret
```
