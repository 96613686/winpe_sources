# Microsoft.Crm.Sandbox.Service.PluginSecureStoreServiceProvider::TryBeginRequest

- ea: `0x7dd0`
- end: `0x7ddb`
- name: `Microsoft.Crm.Sandbox.Service.PluginSecureStoreServiceProvider::TryBeginRequest`
- size: `11`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x7d10`

## callees

- `0x7dd0`

## pseudocode

```c

```

## disassembly

```asm
0x7dd0  ldarg.1
0x7dd1  brfalse.s loc_7DDA
0x7dd3  ldarg.1
0x7dd4  ldarg.2
0x7dd5  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::OnBeginRequest(bool)
0x7dda  ret
```
