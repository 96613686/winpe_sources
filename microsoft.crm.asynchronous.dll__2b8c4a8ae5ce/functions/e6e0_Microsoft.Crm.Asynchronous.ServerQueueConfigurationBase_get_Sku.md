# Microsoft.Crm.Asynchronous.ServerQueueConfigurationBase::get_Sku

- ea: `0xe6e0`
- end: `0xe6ec`
- name: `Microsoft.Crm.Asynchronous.ServerQueueConfigurationBase::get_Sku`
- size: `12`
- prototype: ``
- caller_count: `6`
- callee_count: `0`
- tags: `registry_config, broker_com_uri`

## callers

- `0xea00`
- `0xea30`
- `0xeb10`
- `0xf100`
- `0xf130`
- `0xf210`

## pseudocode

```c

```

## disassembly

```asm
0xe6e0  ldarg.0
0xe6e1  ldfld    class [Microsoft.Crm.Core]Microsoft.Crm.ILocatorService Microsoft.Crm.Asynchronous.ServerQueueConfigurationBase::_locatorService
0xe6e6  callvirt instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.ConfigSku [Microsoft.Crm.Core]Microsoft.Crm.ILocatorService::GetSku()
0xe6eb  ret
```
