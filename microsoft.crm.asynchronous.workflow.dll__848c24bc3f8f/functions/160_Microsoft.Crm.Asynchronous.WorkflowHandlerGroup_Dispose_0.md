# Microsoft.Crm.Asynchronous.WorkflowHandlerGroup::Dispose_0

- ea: `0x160`
- end: `0x17e`
- name: `Microsoft.Crm.Asynchronous.WorkflowHandlerGroup::Dispose_0`
- size: `30`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x130`
- `0x150`

## callees

- `0x160`

## pseudocode

```c

```

## disassembly

```asm
0x160  ldarg.0
0x161  ldfld    bool Microsoft.Crm.Asynchronous.WorkflowHandlerGroup::_disposed
0x166  brtrue.s loc_176
0x168  ldarg.1
0x169  brfalse.s loc_176
0x16b  ldarg.0
0x16c  ldfld    class Microsoft.Crm.Workflow.ActivityHost Microsoft.Crm.Asynchronous.WorkflowHandlerGroup::_activityHost
0x171  callvirt instance void [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.ActivityHostBase::Dispose()
0x176  ldarg.0
0x177  ldc.i4.1
0x178  stfld    bool Microsoft.Crm.Asynchronous.WorkflowHandlerGroup::_disposed
0x17d  ret
```
