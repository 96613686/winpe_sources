# Microsoft.Crm.Sandbox.SandboxPlugin::.ctor

- ea: `0x1fd0`
- end: `0x1fe6`
- name: `Microsoft.Crm.Sandbox.SandboxPlugin::.ctor`
- size: `22`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x17f0`

## callees

- `0x2200`

## pseudocode

```c

```

## disassembly

```asm
0x1fd0  ldarg.0
0x1fd1  ldarg.1
0x1fd2  ldarg.2
0x1fd3  ldarg.s  5
0x1fd5  ldarg.3
0x1fd6  ldarg.s  4
0x1fd8  ldarg.s  6
0x1fda  ldarg.s  7
0x1fdc  ldarg.s  8
0x1fde  ldarg.s  9
0x1fe0  call     instance void Microsoft.Crm.Sandbox.SandboxCodeUnit::.ctor(valuetype [mscorlib]System.Guid pluginTypeId, string pluginTypeName, valuetype [mscorlib]System.Guid pluginAssemblyId, string pluginConfig, string pluginSecureConfig, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IPluginAssemblyData assemblyData, class Microsoft.Crm.Sandbox.SandboxClient client, int32 attemptNumber, int32 maxAttempts)
0x1fe5  ret
```
