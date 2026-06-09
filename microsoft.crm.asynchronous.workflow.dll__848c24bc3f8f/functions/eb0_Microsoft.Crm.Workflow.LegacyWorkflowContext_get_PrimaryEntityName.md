# Microsoft.Crm.Workflow.LegacyWorkflowContext::get_PrimaryEntityName

- ea: `0xeb0`
- end: `0xebc`
- name: `Microsoft.Crm.Workflow.LegacyWorkflowContext::get_PrimaryEntityName`
- size: `12`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x1200`
- `0x1240`

## pseudocode

```c

```

## disassembly

```asm
0xeb0  ldarg.0
0xeb1  ldfld    class [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.ICommonWorkflowContext Microsoft.Crm.Workflow.LegacyWorkflowContext::_workflowContext
0xeb6  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_PrimaryEntityName()
0xebb  ret
```
