# Microsoft.Crm.Workflow.WorkflowToAsyncResultConverter::Convert_5

- ea: `0x2790`
- end: `0x27b8`
- name: `Microsoft.Crm.Workflow.WorkflowToAsyncResultConverter::Convert_5`
- size: `40`
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
0x2790  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor()
0x2795  newobj   instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncFailedResult::.ctor(class [mscorlib]System.Exception)
0x279a  dup
0x279b  ldarg.1
0x279c  callvirt instance int32 [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.WorkflowHandlerResultWithError::get_ErrorCode()
0x27a1  ldarg.1
0x27a2  callvirt instance string [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.WorkflowHandlerResultWithError::get_ErrorMessage()
0x27a7  ldarg.1
0x27a8  callvirt instance string [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.WorkflowHandlerResultWithError::get_FriendlyMessage()
0x27ad  callvirt instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncHandlerResultWithError::setInternalData(int32, string, string)
0x27b2  newobj   instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncRetryResult::.ctor(class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncFailedResult)
0x27b7  ret
```
