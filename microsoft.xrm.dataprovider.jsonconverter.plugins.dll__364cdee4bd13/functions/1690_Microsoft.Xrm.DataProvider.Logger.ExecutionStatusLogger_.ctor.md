# Microsoft.Xrm.DataProvider.Logger.ExecutionStatusLogger::.ctor

- ea: `0x1690`
- end: `0x16ae`
- name: `Microsoft.Xrm.DataProvider.Logger.ExecutionStatusLogger::.ctor`
- size: `30`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x290`

## pseudocode

```c

```

## disassembly

```asm
0x1690  ldarg.0
0x1691  call     instance void [mscorlib]System.Object::.ctor()
0x1696  nop
0x1697  nop
0x1698  ldarg.0
0x1699  ldarg.1
0x169a  stfld    class [Microsoft.Xrm.Log]Microsoft.Xrm.Log.ILogger Microsoft.Xrm.DataProvider.Logger.ExecutionStatusLogger::executionlogger
0x169f  ldarg.0
0x16a0  ldarg.2
0x16a1  stfld    class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger Microsoft.Xrm.DataProvider.Logger.ExecutionStatusLogger::xrmLogger
0x16a6  ldarg.0
0x16a7  ldarg.3
0x16a8  stfld    class Microsoft.Xrm.DataProvider.Logger.IExceptionAnalyzer Microsoft.Xrm.DataProvider.Logger.ExecutionStatusLogger::exceptionAnalyzer
0x16ad  ret
```
