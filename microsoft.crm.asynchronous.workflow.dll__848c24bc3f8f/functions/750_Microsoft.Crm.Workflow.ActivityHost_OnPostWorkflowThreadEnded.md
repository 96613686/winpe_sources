# Microsoft.Crm.Workflow.ActivityHost::OnPostWorkflowThreadEnded

- ea: `0x750`
- end: `0x770`
- name: `Microsoft.Crm.Workflow.ActivityHost::OnPostWorkflowThreadEnded`
- size: `32`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x750`

## pseudocode

```c

```

## disassembly

```asm
0x750  ldarg.0
0x751  ldarg.1
0x752  call     instance void [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.ActivityHostBase::OnPostWorkflowThreadEnded(class [Microsoft.Crm]Microsoft.Crm.IGenericHandlerResult)
0x757  ldarg.1
0x758  isinst   [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncHandlerResult
0x75d  stloc.0
0x75e  ldloc.0
0x75f  brfalse.s loc_76F
0x761  ldloc.0
0x762  ldc.i4.0
0x763  callvirt instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncHandlerResult::set_ThreadStarted(bool)
0x768  ldloc.0
0x769  ldc.i4.1
0x76a  callvirt instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncHandlerResult::set_ThreadCompleted(bool)
0x76f  ret
```
