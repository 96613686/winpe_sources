# Microsoft.Crm.Sandbox.SandboxPluginExecutionRecord::.ctor

- ea: `0x6c70`
- end: `0x6c94`
- name: `Microsoft.Crm.Sandbox.SandboxPluginExecutionRecord::.ctor`
- size: `36`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x6bd0`
- `0x6bf0`
- `0x6c60`
- `0x6ed0`

## pseudocode

```c

```

## disassembly

```asm
0x6c70  ldarg.0
0x6c71  call     instance void Microsoft.Crm.Sandbox.SandboxRequestCounter::.ctor()
0x6c76  ldarg.0
0x6c77  ldarg.1
0x6c78  call     instance void Microsoft.Crm.Sandbox.SandboxPluginExecutionRecord::set_PluginTypeId(valuetype [mscorlib]System.Guid value)
0x6c7d  ldarg.0
0x6c7e  ldarg.2
0x6c7f  call     instance void Microsoft.Crm.Sandbox.SandboxPluginExecutionRecord::set_PluginAssemblyName(string value)
0x6c84  ldarg.0
0x6c85  ldarg.3
0x6c86  call     instance void Microsoft.Crm.Sandbox.SandboxPluginExecutionRecord::set_PluginTypeName(string value)
0x6c8b  ldarg.0
0x6c8c  ldarg.s  4
0x6c8e  stfld    class Microsoft.Crm.Sandbox.SandboxRequestCounter Microsoft.Crm.Sandbox.SandboxRequestCounter::_nextCounter
0x6c93  ret
```
