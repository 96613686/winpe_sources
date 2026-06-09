# Microsoft.Crm.Asynchronous.QueuePerformanceCounters::TrackCompleteThrottledOperation

- ea: `0x1e50`
- end: `0x1e6f`
- name: `Microsoft.Crm.Asynchronous.QueuePerformanceCounters::TrackCompleteThrottledOperation`
- size: `31`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x1e50`
- `0x2050`
- `0x20d0`
- `0x16040`

## pseudocode

```c

```

## disassembly

```asm
0x1e50  ldarg.0
0x1e51  callvirt instance class AsyncOperationPerformanceCounters Microsoft.Crm.Asynchronous.QueuePerformanceCounters::get_TotalCounters()
0x1e56  ldarg.2
0x1e57  callvirt instance void AsyncOperationPerformanceCounters::TrackCompleteThrottledOperation(valuetype [mscorlib]System.TimeSpan elapsedTime)
0x1e5c  ldarg.0
0x1e5d  ldarg.1
0x1e5e  call     instance class AsyncOperationPerformanceCounters Microsoft.Crm.Asynchronous.QueuePerformanceCounters::GetCounterSet(int32 operationType)
0x1e63  stloc.0
0x1e64  ldloc.0
0x1e65  brfalse.s loc_1E6E
0x1e67  ldloc.0
0x1e68  ldarg.2
0x1e69  callvirt instance void AsyncOperationPerformanceCounters::TrackCompleteThrottledOperation(valuetype [mscorlib]System.TimeSpan elapsedTime)
0x1e6e  ret
```
