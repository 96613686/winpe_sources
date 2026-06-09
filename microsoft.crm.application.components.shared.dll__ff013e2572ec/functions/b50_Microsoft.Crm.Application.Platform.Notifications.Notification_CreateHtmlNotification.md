# Microsoft.Crm.Application.Platform.Notifications.Notification::CreateHtmlNotification

- ea: `0xb50`
- end: `0xb60`
- name: `Microsoft.Crm.Application.Platform.Notifications.Notification::CreateHtmlNotification`
- size: `16`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0xa90`

## pseudocode

```c

```

## disassembly

```asm
0xb50  ldarg.2
0xb51  ldarg.0
0xb52  ldarg.1
0xb53  newobj   instance void Microsoft.Crm.Application.Platform.Notifications.Notification::.ctor(string plaintext, int32 severity, string text)
0xb58  dup
0xb59  ldc.i4.1
0xb5a  stfld    bool Microsoft.Crm.Application.Platform.Notifications.Notification::HasHtmlContent
0xb5f  ret
```
