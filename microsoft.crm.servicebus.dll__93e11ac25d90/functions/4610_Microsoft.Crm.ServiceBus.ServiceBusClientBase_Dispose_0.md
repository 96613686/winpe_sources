# Microsoft.Crm.ServiceBus.ServiceBusClientBase::Dispose_0

- ea: `0x4610`
- end: `0x461a`
- name: `Microsoft.Crm.ServiceBus.ServiceBusClientBase::Dispose_0`
- size: `10`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x4600`

## callees

- `0x4610`
- `0x4620`

## pseudocode

```c

```

## disassembly

```asm
0x4610  ldarg.1
0x4611  brfalse.s loc_4619
0x4613  ldarg.0
0x4614  callvirt instance void Microsoft.Crm.ServiceBus.ServiceBusClientBase::Close()
0x4619  ret
```
