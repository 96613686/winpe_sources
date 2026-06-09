# Microsoft.Crm.Asynchronous.ErrorHandlerFactory::CreateDefault

- ea: `0x3a0`
- end: `0x3c7`
- name: `Microsoft.Crm.Asynchronous.ErrorHandlerFactory::CreateDefault`
- size: `39`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x420`
- `0x4f0`
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
0x3a0  ldc.i4.2
0x3a1  ldc.i4.2
0x3a2  ldnull
0x3a3  newobj   instance void Microsoft.Crm.Asynchronous.GeneralErrorHandler::.ctor(class Microsoft.Crm.Asynchronous.ErrorHandler nextHandler)
0x3a8  newobj   instance void Microsoft.Crm.Asynchronous.InvalidPluginExecutionExceptionHandler::.ctor(class Microsoft.Crm.Asynchronous.ErrorHandler nextHandler)
0x3ad  newobj   instance void Microsoft.Crm.Asynchronous.WebErrorHandler::.ctor(class Microsoft.Crm.Asynchronous.ErrorHandler nextHandler)
0x3b2  newobj   instance void Microsoft.Crm.Asynchronous.CrmErrorHandler::.ctor(valuetype Microsoft.Crm.Asynchronous.ErrorActionType defaultActionType, class Microsoft.Crm.Asynchronous.ErrorHandler nextHandler)
0x3b7  newobj   instance void Microsoft.Crm.Asynchronous.SqlErrorHandler::.ctor(class Microsoft.Crm.Asynchronous.ErrorHandler nextHandler)
0x3bc  newobj   instance void Microsoft.Crm.Asynchronous.SoapErrorHandler::.ctor(valuetype Microsoft.Crm.Asynchronous.ErrorActionType defaultActionType, class Microsoft.Crm.Asynchronous.ErrorHandler nextHandler)
0x3c1  newobj   instance void Microsoft.Crm.Asynchronous.TargetInvocationErrorHandler::.ctor(class Microsoft.Crm.Asynchronous.ErrorHandler nextHandler)
0x3c6  ret
```
