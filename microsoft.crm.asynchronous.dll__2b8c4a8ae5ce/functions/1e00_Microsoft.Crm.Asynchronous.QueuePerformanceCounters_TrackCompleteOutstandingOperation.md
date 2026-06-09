# Microsoft.Crm.Asynchronous.QueuePerformanceCounters::TrackCompleteOutstandingOperation

- ea: `0x1e00`
- end: `0x1e21`
- name: `Microsoft.Crm.Asynchronous.QueuePerformanceCounters::TrackCompleteOutstandingOperation`
- size: `33`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x1e00`
- `0x2050`
- `0x20d0`
- `0x15f50`

## pseudocode

```c

```

## disassembly

```asm
0x1e00  ldarg.0
0x1e01  callvirt instance class AsyncOperationPerformanceCounters Microsoft.Crm.Asynchronous.QueuePerformanceCounters::get_TotalCounters()
0x1e06  ldarg.2
0x1e07  ldarg.3
0x1e08  callvirt instance void AsyncOperationPerformanceCounters::TrackCompleteOutstandingOperation(class Microsoft.Crm.Asynchronous.AsyncHandlerResult result, valuetype [mscorlib]System.TimeSpan completionTime)
0x1e0d  ldarg.0
0x1e0e  ldarg.1
0x1e0f  call     instance class AsyncOperationPerformanceCounters Microsoft.Crm.Asynchronous.QueuePerformanceCounters::GetCounterSet(int32 operationType)
0x1e14  stloc.0
0x1e15  ldloc.0
0x1e16  brfalse.s loc_1E20
0x1e18  ldloc.0
0x1e19  ldarg.2
0x1e1a  ldarg.3
0x1e1b  callvirt instance void AsyncOperationPerformanceCounters::TrackCompleteOutstandingOperation(class Microsoft.Crm.Asynchronous.AsyncHandlerResult result, valuetype [mscorlib]System.TimeSpan completionTime)
0x1e20  ret
```
