# Microsoft.Crm.ServiceBus.RouterClient::Finalize

- ea: `0x110`
- end: `0x120`
- name: `Microsoft.Crm.ServiceBus.RouterClient::Finalize`
- size: `16`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x110`
- `0x350`

## pseudocode

```c

```

## disassembly

```asm
0x110  ldarg.0
0x111  call     instance void Microsoft.Crm.ServiceBus.RouterClient::Close()
0x116  leave.s  loc_11F
0x118  ldarg.0
0x119  call     instance void [mscorlib]System.Object::Finalize()
0x11e  endfinally
0x11f  ret
```
