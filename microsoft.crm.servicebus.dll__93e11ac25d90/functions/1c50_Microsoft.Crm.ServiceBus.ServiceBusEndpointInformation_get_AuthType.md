# Microsoft.Crm.ServiceBus.ServiceBusEndpointInformation::get_AuthType

- ea: `0x1c50`
- end: `0x1c57`
- name: `Microsoft.Crm.ServiceBus.ServiceBusEndpointInformation::get_AuthType`
- size: `7`
- prototype: ``
- caller_count: `3`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0xbb0`
- `0x1db0`
- `0x6c10`

## pseudocode

```c

```

## disassembly

```asm
0x1c50  ldarg.0
0x1c51  ldfld    valuetype AuthenticationType Microsoft.Crm.ServiceBus.ServiceBusEndpointInformation::<AuthType>k__BackingField
0x1c56  ret
```
