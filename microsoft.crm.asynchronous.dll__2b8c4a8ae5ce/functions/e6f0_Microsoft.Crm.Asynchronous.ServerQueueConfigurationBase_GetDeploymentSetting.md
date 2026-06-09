# Microsoft.Crm.Asynchronous.ServerQueueConfigurationBase::GetDeploymentSetting

- ea: `0xe6f0`
- end: `0xe6fd`
- name: `Microsoft.Crm.Asynchronous.ServerQueueConfigurationBase::GetDeploymentSetting`
- size: `13`
- prototype: ``
- caller_count: `46`
- callee_count: `0`
- tags: `registry_config, broker_com_uri`

## callers

- `0xe980`
- `0xe9a0`
- `0xe9c0`
- `0xe9e0`
- `0xea00`
- `0xea30`
- `0xea60`
- `0xea80`
- `0xeaa0`
- `0xeac0`
- `0xeaf0`
- `0xeb10`
- `0xecd0`
- `0xecf0`
- `0xed10`
- `0xed30`
- `0xed50`
- `0xed70`
- `0xed90`
- `0xedb0`
- `0xedd0`
- `0xedf0`
- `0xee10`
- `0xee40`
- `0xee60`
- `0xee80`
- `0xeea0`
- `0xeec0`
- `0xeee0`
- `0xef10`
- `0xef30`
- `0xef50`
- `0xef80`
- `0xefa0`
- `0xf050`
- `0xf070`
- `0xf090`
- `0xf0e0`
- `0xf100`
- `0xf130`
- `0xf160`
- `0xf180`
- `0xf1a0`
- `0xf1c0`
- `0xf1f0`
- `0xf210`

## pseudocode

```c

```

## disassembly

```asm
0xe6f0  ldarg.0
0xe6f1  ldfld    class [Microsoft.Crm.Core]Microsoft.Crm.ILocatorService Microsoft.Crm.Asynchronous.ServerQueueConfigurationBase::_locatorService
0xe6f6  ldarg.1
0xe6f7  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.ILocatorService::GetDeploymentSetting(string)
0xe6fc  ret
```
