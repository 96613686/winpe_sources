# Microsoft.Crm.Asynchronous.QueueManager::CreateTimers

- ea: `0x9d30`
- end: `0x9d63`
- name: `Microsoft.Crm.Asynchronous.QueueManager::CreateTimers`
- size: `51`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x4a00`

## callees

- `0x6e60`
- `0x9d70`
- `0x9de0`
- `0x13610`

## pseudocode

```c

```

## disassembly

```asm
0x9d30  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.TimerBasedExecutionEngine>::.ctor()
0x9d35  stloc.0
0x9d36  ldloc.0
0x9d37  ldarg.0
0x9d38  call     instance class Microsoft.Crm.Asynchronous.Operations.IServiceOperation Microsoft.Crm.Asynchronous.QueueManager::CreateSelectTimerOperation()
0x9d3d  ldarg.0
0x9d3e  ldfld    class Microsoft.Crm.Asynchronous.IQueueConfiguration Microsoft.Crm.Asynchronous.QueueManager::_config
0x9d43  callvirt instance valuetype [mscorlib]System.TimeSpan Microsoft.Crm.Asynchronous.IQueueConfiguration::get_SelectInterval()
0x9d48  stloc.1
0x9d49  ldloca.s 1
0x9d4b  call     instance float64 [mscorlib]System.TimeSpan::get_TotalMilliseconds()
0x9d50  newobj   instance void Microsoft.Crm.Asynchronous.TimerBasedExecutionEngine::.ctor(class Microsoft.Crm.Asynchronous.Operations.IServiceOperation operation, float64 interval)
0x9d55  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.TimerBasedExecutionEngine>::Add(var<u1>)
0x9d5a  ldarg.0
0x9d5b  ldloc.0
0x9d5c  call     instance void Microsoft.Crm.Asynchronous.QueueManager::AddDiagnosticModeTimerEvent(class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.TimerBasedExecutionEngine> timers)
0x9d61  ldloc.0
0x9d62  ret
```
