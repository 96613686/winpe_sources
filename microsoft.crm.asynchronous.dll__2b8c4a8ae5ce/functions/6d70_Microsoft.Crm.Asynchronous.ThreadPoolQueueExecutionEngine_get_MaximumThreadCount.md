# Microsoft.Crm.Asynchronous.ThreadPoolQueueExecutionEngine::get_MaximumThreadCount

- ea: `0x6d70`
- end: `0x6da1`
- name: `Microsoft.Crm.Asynchronous.ThreadPoolQueueExecutionEngine::get_MaximumThreadCount`
- size: `49`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x67d0`
- `0xb280`

## callees

- `0x120c0`
- `0x120d0`

## pseudocode

```c

```

## disassembly

```asm
0x6d70  ldloca.s 0
0x6d72  ldloca.s 1
0x6d74  call     void [mscorlib]System.Threading.ThreadPool::GetMaxThreads(int32&, int32&)
0x6d79  ldarg.0
0x6d7a  ldfld    class Microsoft.Crm.Asynchronous.IThreadPoolThrottlingSettings Microsoft.Crm.Asynchronous.ThreadPoolQueueExecutionEngine::_settings
0x6d7f  callvirt instance float64 Microsoft.Crm.Asynchronous.IThreadPoolThrottlingSettings::get_MaximumThreadsPercent()
0x6d84  ldloc.0
0x6d85  conv.r8
0x6d86  mul
0x6d87  conv.i4
0x6d88  stloc.2
0x6d89  ldarg.0
0x6d8a  ldfld    class Microsoft.Crm.Asynchronous.IThreadPoolThrottlingSettings Microsoft.Crm.Asynchronous.ThreadPoolQueueExecutionEngine::_settings
0x6d8f  callvirt instance int32 Microsoft.Crm.Asynchronous.IThreadPoolThrottlingSettings::get_MaximumThreadsPerCPU()
0x6d94  call     int32 [mscorlib]System.Environment::get_ProcessorCount()
0x6d99  mul
0x6d9a  ldloc.2
0x6d9b  call     int32 [mscorlib]System.Math::Min(int32, int32)
0x6da0  ret
```
