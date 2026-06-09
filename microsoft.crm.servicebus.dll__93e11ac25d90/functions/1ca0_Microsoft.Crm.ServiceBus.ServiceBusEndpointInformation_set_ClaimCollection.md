# Microsoft.Crm.ServiceBus.ServiceBusEndpointInformation::set_ClaimCollection

- ea: `0x1ca0`
- end: `0x1ca8`
- name: `Microsoft.Crm.ServiceBus.ServiceBusEndpointInformation::set_ClaimCollection`
- size: `8`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0xb60`
- `0x19d0`

## pseudocode

```c

```

## disassembly

```asm
0x1ca0  ldarg.0
0x1ca1  ldarg.1
0x1ca2  stfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.Crm.ServiceBus.ServiceBusEndpointInformation::<ClaimCollection>k__BackingField
0x1ca7  ret
```
