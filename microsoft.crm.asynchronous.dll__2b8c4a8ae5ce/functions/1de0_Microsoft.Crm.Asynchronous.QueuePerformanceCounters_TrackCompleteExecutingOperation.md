# Microsoft.Crm.Asynchronous.QueuePerformanceCounters::TrackCompleteExecutingOperation

- ea: `0x1de0`
- end: `0x1dfd`
- name: `Microsoft.Crm.Asynchronous.QueuePerformanceCounters::TrackCompleteExecutingOperation`
- size: `29`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x1de0`
- `0x2050`
- `0x20d0`
- `0x15f40`

## pseudocode

```c

```

## disassembly

```asm
0x1de0  ldarg.0
0x1de1  callvirt instance class AsyncOperationPerformanceCounters Microsoft.Crm.Asynchronous.QueuePerformanceCounters::get_TotalCounters()
0x1de6  callvirt instance void AsyncOperationPerformanceCounters::TrackCompleteExecutingOperation()
0x1deb  ldarg.0
0x1dec  ldarg.1
0x1ded  call     instance class AsyncOperationPerformanceCounters Microsoft.Crm.Asynchronous.QueuePerformanceCounters::GetCounterSet(int32 operationType)
0x1df2  stloc.0
0x1df3  ldloc.0
0x1df4  brfalse.s loc_1DFC
0x1df6  ldloc.0
0x1df7  callvirt instance void AsyncOperationPerformanceCounters::TrackCompleteExecutingOperation()
0x1dfc  ret
```
