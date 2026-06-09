# Microsoft.Crm.Asynchronous.ErrorHandlerFactory::CreateWorkflowDefault

- ea: `0x3d0`
- end: `0x406`
- name: `Microsoft.Crm.Asynchronous.ErrorHandlerFactory::CreateWorkflowDefault`
- size: `54`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x4d50`

## callees

- `0x420`
- `0x480`
- `0x4f0`
- `0x590`
- `0x620`
- `0x6e0`
- `0x760`
- `0x8f0`
- `0xae0`
- `0xb40`

## pseudocode

```c

```

## disassembly

```asm
0x3d0  ldc.i4.3
0x3d1  ldc.i4.3
0x3d2  ldnull
0x3d3  newobj   instance void Microsoft.Crm.Asynchronous.GeneralErrorHandler::.ctor(class Microsoft.Crm.Asynchronous.ErrorHandler nextHandler)
0x3d8  newobj   instance void Microsoft.Crm.Asynchronous.WebErrorHandler::.ctor(class Microsoft.Crm.Asynchronous.ErrorHandler nextHandler)
0x3dd  newobj   instance void Microsoft.Crm.Asynchronous.CrmErrorHandler::.ctor(valuetype Microsoft.Crm.Asynchronous.ErrorActionType defaultActionType, class Microsoft.Crm.Asynchronous.ErrorHandler nextHandler)
0x3e2  newobj   instance void Microsoft.Crm.Asynchronous.SqlErrorHandler::.ctor(class Microsoft.Crm.Asynchronous.ErrorHandler nextHandler)
0x3e7  newobj   instance void Microsoft.Crm.Asynchronous.SoapErrorHandler::.ctor(valuetype Microsoft.Crm.Asynchronous.ErrorActionType defaultActionType, class Microsoft.Crm.Asynchronous.ErrorHandler nextHandler)
0x3ec  newobj   instance void Microsoft.Crm.Asynchronous.StopWorkflowExceptionCrmHandler::.ctor(class Microsoft.Crm.Asynchronous.ErrorHandler nextHandler)
0x3f1  newobj   instance void Microsoft.Crm.Asynchronous.InvalidPluginExecutionExceptionHandler::.ctor(class Microsoft.Crm.Asynchronous.ErrorHandler nextHandler)
0x3f6  newobj   instance void Microsoft.Crm.Asynchronous.WorkflowApplicationTerminatedExceptionHandler::.ctor(class Microsoft.Crm.Asynchronous.ErrorHandler nextHandler)
0x3fb  newobj   instance void Microsoft.Crm.Asynchronous.WorkflowTerminatedExceptionHandler::.ctor(class Microsoft.Crm.Asynchronous.ErrorHandler nextHandler)
0x400  newobj   instance void Microsoft.Crm.Asynchronous.TargetInvocationErrorHandler::.ctor(class Microsoft.Crm.Asynchronous.ErrorHandler nextHandler)
0x405  ret
```
