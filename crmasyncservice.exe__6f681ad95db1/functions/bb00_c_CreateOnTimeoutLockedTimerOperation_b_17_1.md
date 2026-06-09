# <>c::<CreateOnTimeoutLockedTimerOperation>b__17_1

- ea: `0xbb00`
- end: `0xbb15`
- name: `<>c::<CreateOnTimeoutLockedTimerOperation>b__17_1`
- size: `21`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x7ff0`

## pseudocode

```c

```

## disassembly

```asm
0xbb00  ldarg.1
0xbb01  castclass Microsoft.Crm.Asynchronous.EmailConnector.MailboxQueueDataAccess
0xbb06  ldloca.s 0
0xbb08  initobj  valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>
0xbb0e  ldloc.0
0xbb0f  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.MailboxQueueDataAccess::TimeoutLocked([opt] valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime> unlockMailboxesStartedBefore)
0xbb14  ret
```
