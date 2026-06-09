# Microsoft.Crm.Asynchronous.V4ProxyPlugin::.ctor

- ea: `0x33e0`
- end: `0x3405`
- name: `Microsoft.Crm.Asynchronous.V4ProxyPlugin::.ctor`
- size: `37`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x2db0`

## callees

- `0x32c0`
- `0x33e0`

## pseudocode

```c

```

## disassembly

```asm
0x33e0  ldarg.0
0x33e1  ldarg.2
0x33e2  call     instance void Microsoft.Crm.Asynchronous.VersionedProxyPluginBase::.ctor(class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncExecutionContext context)
0x33e7  ldarg.0
0x33e8  ldarg.0
0x33e9  ldarg.1
0x33ea  ldarg.2
0x33eb  call     T0x2B000006
0x33f0  stfld    class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.IPlugin Microsoft.Crm.Asynchronous.V4ProxyPlugin::_plugin
0x33f5  ldarg.0
0x33f6  ldfld    class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.IPlugin Microsoft.Crm.Asynchronous.V4ProxyPlugin::_plugin
0x33fb  brtrue.s loc_3401
0x33fd  ldarg.3
0x33fe  ldc.i4.0
0x33ff  stind.i1
0x3400  ret
0x3401  ldarg.3
0x3402  ldc.i4.1
0x3403  stind.i1
0x3404  ret
```
