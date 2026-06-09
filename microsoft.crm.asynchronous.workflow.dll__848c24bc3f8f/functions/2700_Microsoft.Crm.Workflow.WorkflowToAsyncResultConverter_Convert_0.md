# Microsoft.Crm.Workflow.WorkflowToAsyncResultConverter::Convert_0

- ea: `0x2700`
- end: `0x2723`
- name: `Microsoft.Crm.Workflow.WorkflowToAsyncResultConverter::Convert_0`
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
0x2700  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor()
0x2705  newobj   instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncFailedResult::.ctor(class [mscorlib]System.Exception)
0x270a  dup
0x270b  ldarg.1
0x270c  callvirt instance int32 [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.WorkflowHandlerResultWithError::get_ErrorCode()
0x2711  ldarg.1
0x2712  callvirt instance string [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.WorkflowHandlerResultWithError::get_ErrorMessage()
0x2717  ldarg.1
0x2718  callvirt instance string [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.WorkflowHandlerResultWithError::get_FriendlyMessage()
0x271d  callvirt instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncHandlerResultWithError::setInternalData(int32, string, string)
0x2722  ret
```
