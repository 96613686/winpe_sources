# Microsoft.Crm.Asynchronous.AsyncOperationQueueManagerBase::CreateLostJobDetectionTimer

- ea: `0x4d70`
- end: `0x4da7`
- name: `Microsoft.Crm.Asynchronous.AsyncOperationQueueManagerBase::CreateLostJobDetectionTimer`
- size: `55`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x4c20`

## callees

- `0x4db0`
- `0x6e60`
- `0xd060`

## pseudocode

```c

```

## disassembly

```asm
0x4d70  ldstr    aAsyncsemaphore// "AsyncSemaphoreDiagnosticRunIntervalInHo"...
0x4d75  ldc.i4.1
0x4d76  call     int32 Microsoft.Crm.Asynchronous.ServerConfiguration::GetDeploymentSettingOrDefault(string settingName, int32 defaultValue)
0x4d7b  ldc.i4.s 0x3C
0x4d7d  mul
0x4d7e  conv.r8
0x4d7f  ldc.r8   60.0
0x4d88  mul
0x4d89  ldc.r8   1000.0
0x4d92  mul
0x4d93  stloc.0
0x4d94  ldarg.1
0x4d95  ldarg.0
0x4d96  call     instance class Microsoft.Crm.Asynchronous.Operations.IServiceOperation Microsoft.Crm.Asynchronous.AsyncOperationQueueManagerBase::CreateLongLockedEventDetectionTimerOperation()
0x4d9b  ldloc.0
0x4d9c  newobj   instance void Microsoft.Crm.Asynchronous.TimerBasedExecutionEngine::.ctor(class Microsoft.Crm.Asynchronous.Operations.IServiceOperation operation, float64 interval)
0x4da1  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<class Microsoft.Crm.Asynchronous.TimerBasedExecutionEngine>::Add(var<u1>)
0x4da6  ret
```
