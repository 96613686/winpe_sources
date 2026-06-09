# AsyncOperationPerformanceCounters::TrackCompleteOutstandingOperation

- ea: `0x15f50`
- end: `0x1600a`
- name: `AsyncOperationPerformanceCounters::TrackCompleteOutstandingOperation`
- size: `186`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1e00`

## callees

- `0x15f50`
- `0x16080`

## pseudocode

```c

```

## disassembly

```asm
0x15f50  ldarg.0
0x15f51  ldfld    class [System]System.Diagnostics.PerformanceCounter AsyncOperationPerformanceCounters::_itemsOutstanding
0x15f56  callvirt instance int64 [System]System.Diagnostics.PerformanceCounter::Decrement()
0x15f5b  pop
0x15f5c  ldarg.0
0x15f5d  ldfld    class [System]System.Diagnostics.PerformanceCounter AsyncOperationPerformanceCounters::_itemsCompleted
0x15f62  callvirt instance int64 [System]System.Diagnostics.PerformanceCounter::Increment()
0x15f67  stloc.0
0x15f68  ldarg.0
0x15f69  ldfld    class [System]System.Diagnostics.PerformanceCounter AsyncOperationPerformanceCounters::_itemsCompletedThroughput
0x15f6e  callvirt instance int64 [System]System.Diagnostics.PerformanceCounter::Increment()
0x15f73  pop
0x15f74  ldloc.0
0x15f75  ldc.i4.1
0x15f76  conv.i8
0x15f77  bge.s    loc_15F7C
0x15f79  ldc.i4.1
0x15f7a  conv.i8
0x15f7b  stloc.0
0x15f7c  ldarg.1
0x15f7d  isinst   Microsoft.Crm.Asynchronous.AsyncFailedResult
0x15f82  brfalse.s loc_15F92
0x15f84  ldarg.0
0x15f85  ldfld    class [System]System.Diagnostics.PerformanceCounter AsyncOperationPerformanceCounters::_itemsFailedWithException
0x15f8a  callvirt instance int64 [System]System.Diagnostics.PerformanceCounter::Increment()
0x15f8f  pop
0x15f90  br.s     loc_15FA6
0x15f92  ldarg.1
0x15f93  isinst   Microsoft.Crm.Asynchronous.AsyncRetryResult
0x15f98  brfalse.s loc_15FA6
0x15f9a  ldarg.0
0x15f9b  ldfld    class [System]System.Diagnostics.PerformanceCounter AsyncOperationPerformanceCounters::_itemsFailedWithRetry
0x15fa0  callvirt instance int64 [System]System.Diagnostics.PerformanceCounter::Increment()
0x15fa5  pop
0x15fa6  ldarg.0
0x15fa7  ldfld    class [System]System.Diagnostics.PerformanceCounter AsyncOperationPerformanceCounters::_rateFailedWithException
0x15fac  ldarg.0
0x15fad  ldfld    class [System]System.Diagnostics.PerformanceCounter AsyncOperationPerformanceCounters::_itemsFailedWithException
0x15fb2  callvirt instance int64 [System]System.Diagnostics.PerformanceCounter::get_RawValue()
0x15fb7  conv.r8
0x15fb8  ldloc.0
0x15fb9  conv.r8
0x15fba  div
0x15fbb  ldc.r8   100.0
0x15fc4  mul
0x15fc5  conv.i8
0x15fc6  callvirt instance void [System]System.Diagnostics.PerformanceCounter::set_RawValue(int64)
0x15fcb  ldarg.0
0x15fcc  ldfld    class [System]System.Diagnostics.PerformanceCounter AsyncOperationPerformanceCounters::_rateFailedWithRetry
0x15fd1  ldarg.0
0x15fd2  ldfld    class [System]System.Diagnostics.PerformanceCounter AsyncOperationPerformanceCounters::_itemsFailedWithRetry
0x15fd7  callvirt instance int64 [System]System.Diagnostics.PerformanceCounter::get_RawValue()
0x15fdc  conv.r8
0x15fdd  ldloc.0
0x15fde  conv.r8
0x15fdf  div
0x15fe0  ldc.r8   100.0
0x15fe9  mul
0x15fea  conv.i8
0x15feb  callvirt instance void [System]System.Diagnostics.PerformanceCounter::set_RawValue(int64)
0x15ff0  ldarg.0
0x15ff1  ldarg.0
0x15ff2  ldfld    class [System]System.Diagnostics.PerformanceCounter AsyncOperationPerformanceCounters::_averageExecutionTime
0x15ff7  ldarg.0
0x15ff8  ldflda   int64 AsyncOperationPerformanceCounters::_totalExecutionCount
0x15ffd  ldarg.0
0x15ffe  ldflda   int64 AsyncOperationPerformanceCounters::_totalExecutionTime
0x16003  ldarg.2
0x16004  call     instance void AsyncOperationPerformanceCounters::UpdateTimeBasedCounter(class [System]System.Diagnostics.PerformanceCounter counter, int64& totalCount, int64& totalTime, valuetype [mscorlib]System.TimeSpan elapsedTime)
0x16009  ret
```
