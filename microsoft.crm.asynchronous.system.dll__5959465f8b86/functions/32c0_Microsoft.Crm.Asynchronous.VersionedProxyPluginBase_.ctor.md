# Microsoft.Crm.Asynchronous.VersionedProxyPluginBase::.ctor

- ea: `0x32c0`
- end: `0x32ce`
- name: `Microsoft.Crm.Asynchronous.VersionedProxyPluginBase::.ctor`
- size: `14`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x33e0`
- `0x3450`

## pseudocode

```c

```

## disassembly

```asm
0x32c0  ldarg.0
0x32c1  call     instance void [mscorlib]System.Object::.ctor()
0x32c6  ldarg.0
0x32c7  ldarg.1
0x32c8  stfld    class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncExecutionContext Microsoft.Crm.Asynchronous.VersionedProxyPluginBase::_context
0x32cd  ret
```
