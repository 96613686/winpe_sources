# Microsoft.Crm.Workflow.WorkflowToAsyncResultConverter::Convert

- ea: `0x2590`
- end: `0x25c0`
- name: `Microsoft.Crm.Workflow.WorkflowToAsyncResultConverter::Convert`
- size: `48`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x280`
- `0x1d40`

## callees

- `0x2590`
- `0x25c0`

## pseudocode

```c

```

## disassembly

```asm
0x2590  ldarg.0
0x2591  call     instance class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncHandlerResult Microsoft.Crm.Workflow.WorkflowToAsyncResultConverter::ConvertInternal()
0x2596  stloc.0
0x2597  ldarg.0
0x2598  ldfld    class [Microsoft.Crm]Microsoft.Crm.IGenericHandlerResult Microsoft.Crm.Workflow.WorkflowToAsyncResultConverter::_wfOperationStatus
0x259d  isinst   [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.WorkflowHandlerResult
0x25a2  stloc.1
0x25a3  ldloc.1
0x25a4  brfalse.s loc_25BE
0x25a6  ldloc.0
0x25a7  ldloc.1
0x25a8  callvirt instance bool [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.WorkflowHandlerResult::get_ThreadStarted()
0x25ad  callvirt instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncHandlerResult::set_ThreadStarted(bool)
0x25b2  ldloc.0
0x25b3  ldloc.1
0x25b4  callvirt instance bool [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.WorkflowHandlerResult::get_ThreadCompleted()
0x25b9  callvirt instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncHandlerResult::set_ThreadCompleted(bool)
0x25be  ldloc.0
0x25bf  ret
```
