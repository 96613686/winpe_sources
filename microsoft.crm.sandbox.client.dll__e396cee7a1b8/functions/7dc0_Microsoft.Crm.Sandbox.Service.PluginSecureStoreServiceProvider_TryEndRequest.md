# Microsoft.Crm.Sandbox.Service.PluginSecureStoreServiceProvider::TryEndRequest

- ea: `0x7dc0`
- end: `0x7dca`
- name: `Microsoft.Crm.Sandbox.Service.PluginSecureStoreServiceProvider::TryEndRequest`
- size: `10`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x7d10`

## callees

- `0x7dc0`

## pseudocode

```c

```

## disassembly

```asm
0x7dc0  ldarg.1
0x7dc1  brfalse.s loc_7DC9
0x7dc3  ldarg.1
0x7dc4  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::OnEndRequest()
0x7dc9  ret
```
