# Microsoft.Crm.Workflow.WorkflowToAsyncResultConverter::.ctor

- ea: `0x2580`
- end: `0x258e`
- name: `Microsoft.Crm.Workflow.WorkflowToAsyncResultConverter::.ctor`
- size: `14`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x280`
- `0x1d40`

## pseudocode

```c

```

## disassembly

```asm
0x2580  ldarg.0
0x2581  call     instance void [mscorlib]System.Object::.ctor()
0x2586  ldarg.0
0x2587  ldarg.1
0x2588  stfld    class [Microsoft.Crm]Microsoft.Crm.IGenericHandlerResult Microsoft.Crm.Workflow.WorkflowToAsyncResultConverter::_wfOperationStatus
0x258d  ret
```
