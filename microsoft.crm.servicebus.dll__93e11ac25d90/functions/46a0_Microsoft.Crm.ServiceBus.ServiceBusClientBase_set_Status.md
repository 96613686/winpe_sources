# Microsoft.Crm.ServiceBus.ServiceBusClientBase::set_Status

- ea: `0x46a0`
- end: `0x46a8`
- name: `Microsoft.Crm.ServiceBus.ServiceBusClientBase::set_Status`
- size: `8`
- prototype: ``
- caller_count: `7`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x4420`
- `0x4940`
- `0x4980`
- `0x4ab0`
- `0x4b50`
- `0x4c90`
- `0x4d10`

## pseudocode

```c

```

## disassembly

```asm
0x46a0  ldarg.0
0x46a1  ldarg.1
0x46a2  stfld    valuetype Microsoft.Crm.ServiceBus.ClientStatus Microsoft.Crm.ServiceBus.ServiceBusClientBase::<Status>k__BackingField
0x46a7  ret
```
