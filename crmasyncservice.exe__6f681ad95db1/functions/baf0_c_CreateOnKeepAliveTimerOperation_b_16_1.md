# <>c::<CreateOnKeepAliveTimerOperation>b__16_1

- ea: `0xbaf0`
- end: `0xbafc`
- name: `<>c::<CreateOnKeepAliveTimerOperation>b__16_1`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x7f10`

## pseudocode

```c

```

## disassembly

```asm
0xbaf0  ldarg.1
0xbaf1  castclass Microsoft.Crm.Asynchronous.EmailConnector.MailboxQueueDataAccess
0xbaf6  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.MailboxQueueDataAccess::KeepAlive()
0xbafb  ret
```
