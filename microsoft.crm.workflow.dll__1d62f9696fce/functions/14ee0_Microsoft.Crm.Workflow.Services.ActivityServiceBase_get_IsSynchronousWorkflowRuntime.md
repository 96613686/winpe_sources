# Microsoft.Crm.Workflow.Services.ActivityServiceBase::get_IsSynchronousWorkflowRuntime

- ea: `0x14ee0`
- end: `0x14eef`
- name: `Microsoft.Crm.Workflow.Services.ActivityServiceBase::get_IsSynchronousWorkflowRuntime`
- size: `15`
- prototype: ``
- caller_count: `6`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x14ec0`
- `0x196a0`
- `0x19860`
- `0x19930`
- `0x19b10`
- `0x19d30`

## callees

- `0x14770`

## pseudocode

```c

```

## disassembly

```asm
0x14ee0  ldarg.0
0x14ee1  call     instance class Microsoft.Crm.Workflow.ICommonWorkflowContext Microsoft.Crm.Workflow.Services.ActivityServiceBase::get_WorkflowContext()
0x14ee6  isinst   Microsoft.Crm.Workflow.SynchronousRuntime.SynchronousWorkflowContext
0x14eeb  ldnull
0x14eec  cgt.un
0x14eee  ret
```
