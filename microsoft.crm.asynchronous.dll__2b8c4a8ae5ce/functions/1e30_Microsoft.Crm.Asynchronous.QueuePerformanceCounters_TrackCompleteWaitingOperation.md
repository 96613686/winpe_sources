# Microsoft.Crm.Asynchronous.QueuePerformanceCounters::TrackCompleteWaitingOperation

- ea: `0x1e30`
- end: `0x1e4f`
- name: `Microsoft.Crm.Asynchronous.QueuePerformanceCounters::TrackCompleteWaitingOperation`
- size: `31`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x1e30`
- `0x2050`
- `0x20d0`
- `0x16010`

## pseudocode

```c

```

## disassembly

```asm
0x1e30  ldarg.0
0x1e31  callvirt instance class AsyncOperationPerformanceCounters Microsoft.Crm.Asynchronous.QueuePerformanceCounters::get_TotalCounters()
0x1e36  ldarg.2
0x1e37  callvirt instance void AsyncOperationPerformanceCounters::TrackCompleteWaitingOperation(valuetype [mscorlib]System.TimeSpan elapsedTime)
0x1e3c  ldarg.0
0x1e3d  ldarg.1
0x1e3e  call     instance class AsyncOperationPerformanceCounters Microsoft.Crm.Asynchronous.QueuePerformanceCounters::GetCounterSet(int32 operationType)
0x1e43  stloc.0
0x1e44  ldloc.0
0x1e45  brfalse.s loc_1E4E
0x1e47  ldloc.0
0x1e48  ldarg.2
0x1e49  callvirt instance void AsyncOperationPerformanceCounters::TrackCompleteWaitingOperation(valuetype [mscorlib]System.TimeSpan elapsedTime)
0x1e4e  ret
```
