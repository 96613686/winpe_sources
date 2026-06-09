# Microsoft.Crm.Sandbox.SandboxStatistics::CreateInitial

- ea: `0x5bb0`
- end: `0x5bda`
- name: `Microsoft.Crm.Sandbox.SandboxStatistics::CreateInitial`
- size: `42`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x5a90`

## string_xrefs

- `0x5bb7`: `SandboxStatistics.CreateInitial: enter`

## pseudocode

```c

```

## disassembly

```asm
0x5bb0  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x5bb5  ldc.i4.s 0x28
0x5bb7  ldstr    aSandboxstatist_2// "SandboxStatistics.CreateInitial: enter"
0x5bbc  ldc.i4.0
0x5bbd  newarr   [mscorlib]System.Object
0x5bc2  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x5bc7  ldarg.1
0x5bc8  ldstr    aEntity// "entity"
0x5bcd  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x5bd2  ldarg.0
0x5bd3  ldarg.1
0x5bd4  call     instance void Microsoft.Crm.Sandbox.SandboxStatistics::WriteCounts(class [Microsoft.Crm.Entities]Microsoft.Crm.Entities.PluginTypeStatistic entity)
0x5bd9  ret
```
