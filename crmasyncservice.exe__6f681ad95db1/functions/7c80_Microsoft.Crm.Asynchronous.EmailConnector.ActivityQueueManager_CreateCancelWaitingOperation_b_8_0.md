# Microsoft.Crm.Asynchronous.EmailConnector.ActivityQueueManager::<CreateCancelWaitingOperation>b__8_0

- ea: `0x7c80`
- end: `0x7c8d`
- name: `Microsoft.Crm.Asynchronous.EmailConnector.ActivityQueueManager::<CreateCancelWaitingOperation>b__8_0`
- size: `13`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x7c60`

## pseudocode

```c

```

## disassembly

```asm
0x7c80  ldarg.0
0x7c81  ldarg.1
0x7c82  callvirt instance valuetype [mscorlib]System.Threading.CancellationToken [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.Operations.IServiceOperation::get_CancellationToken()
0x7c87  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.ActivityQueueManager::OnCancelWaitingTimerEvent(valuetype [mscorlib]System.Threading.CancellationToken token)
0x7c8c  ret
```
