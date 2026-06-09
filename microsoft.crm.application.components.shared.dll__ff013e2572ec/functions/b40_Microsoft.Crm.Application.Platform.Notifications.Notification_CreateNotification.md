# Microsoft.Crm.Application.Platform.Notifications.Notification::CreateNotification

- ea: `0xb40`
- end: `0xb48`
- name: `Microsoft.Crm.Application.Platform.Notifications.Notification::CreateNotification`
- size: `8`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0xa60`

## pseudocode

```c

```

## disassembly

```asm
0xb40  ldarg.0
0xb41  ldarg.1
0xb42  newobj   instance void Microsoft.Crm.Application.Platform.Notifications.Notification::.ctor(int32 severity, string text)
0xb47  ret
```
