# Microsoft.Crm.Asynchronous.EmailConnector.MailboxQueueManager::<CreateTimers>b__14_0

- ea: `0xa220`
- end: `0xa22d`
- name: `Microsoft.Crm.Asynchronous.EmailConnector.MailboxQueueManager::<CreateTimers>b__14_0`
- size: `13`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0xa200`

## pseudocode

```c

```

## disassembly

```asm
0xa220  ldarg.0
0xa221  ldarg.1
0xa222  callvirt instance valuetype [mscorlib]System.Threading.CancellationToken [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.Operations.IServiceOperation::get_CancellationToken()
0xa227  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.MailboxQueueManager::OnCancelWaitingTimerEvent(valuetype [mscorlib]System.Threading.CancellationToken token)
0xa22c  ret
```
