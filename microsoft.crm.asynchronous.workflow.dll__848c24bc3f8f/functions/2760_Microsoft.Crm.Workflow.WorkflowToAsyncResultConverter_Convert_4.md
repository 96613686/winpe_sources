# Microsoft.Crm.Workflow.WorkflowToAsyncResultConverter::Convert_4

- ea: `0x2760`
- end: `0x2783`
- name: `Microsoft.Crm.Workflow.WorkflowToAsyncResultConverter::Convert_4`
- size: `35`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x25c0`

## pseudocode

```c

```

## disassembly

```asm
0x2760  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor()
0x2765  newobj   instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncSystemPausedResult::.ctor(class [mscorlib]System.Exception)
0x276a  dup
0x276b  ldarg.1
0x276c  callvirt instance int32 [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.WorkflowHandlerResultWithError::get_ErrorCode()
0x2771  ldarg.1
0x2772  callvirt instance string [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.WorkflowHandlerResultWithError::get_ErrorMessage()
0x2777  ldarg.1
0x2778  callvirt instance string [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.WorkflowHandlerResultWithError::get_FriendlyMessage()
0x277d  callvirt instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncHandlerResultWithError::setInternalData(int32, string, string)
0x2782  ret
```
