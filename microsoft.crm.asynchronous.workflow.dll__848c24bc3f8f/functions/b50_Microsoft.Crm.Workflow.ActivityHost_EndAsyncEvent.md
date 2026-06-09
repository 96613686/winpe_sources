# Microsoft.Crm.Workflow.ActivityHost::EndAsyncEvent

- ea: `0xb50`
- end: `0xb65`
- name: `Microsoft.Crm.Workflow.ActivityHost::EndAsyncEvent`
- size: `21`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x770`
- `0x910`

## callees

- `0xb50`
- `0x1d40`

## pseudocode

```c

```

## disassembly

```asm
0xb50  ldarg.1
0xb51  isinst   Microsoft.Crm.Workflow.WorkflowContext
0xb56  brfalse.s loc_B64
0xb58  ldarg.1
0xb59  isinst   Microsoft.Crm.Workflow.WorkflowContext
0xb5e  ldarg.2
0xb5f  callvirt instance void Microsoft.Crm.Workflow.WorkflowContext::EndAsyncEvent(class [Microsoft.Crm]Microsoft.Crm.IGenericHandlerResult result)
0xb64  ret
```
