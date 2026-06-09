# Microsoft.Crm.Asynchronous.QueuePerformanceCounters::AddCommonCountersForInstall

- ea: `0x1fb0`
- end: `0x1fd0`
- name: `Microsoft.Crm.Asynchronous.QueuePerformanceCounters::AddCommonCountersForInstall`
- size: `32`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callers

- `0x850`

## callees

- `0x2000`
- `0x15c70`
- `0x164a0`

## pseudocode

```c

```

## disassembly

```asm
0x1fb0  newobj   instance void <>c__DisplayClass36_0::.ctor()
0x1fb5  stloc.0
0x1fb6  ldloc.0
0x1fb7  ldarg.0
0x1fb8  stfld    class [System]System.Diagnostics.CounterCreationDataCollection <>c__DisplayClass36_0::collection
0x1fbd  ldarg.1
0x1fbe  ldloc.0
0x1fbf  ldftn    instance void <>c__DisplayClass36_0::<AddCommonCountersForInstall>b__0(int32 operationType, string operationName)
0x1fc5  newobj   instance void AsyncOperationTypeProcessor::.ctor(object object, native int method)
0x1fca  call     void Microsoft.Crm.Asynchronous.QueuePerformanceCounters::ProcessForEachOperationType(class [mscorlib]System.Type operationTypesType, class AsyncOperationTypeProcessor processor)
0x1fcf  ret
```
