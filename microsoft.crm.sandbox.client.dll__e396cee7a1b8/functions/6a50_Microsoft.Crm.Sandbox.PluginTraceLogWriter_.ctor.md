# Microsoft.Crm.Sandbox.PluginTraceLogWriter::.ctor

- ea: `0x6a50`
- end: `0x6a80`
- name: `Microsoft.Crm.Sandbox.PluginTraceLogWriter::.ctor`
- size: `48`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x67d0`

## string_xrefs

- `0x6a6e`: `pluginTraceLogRecord`
- `0x6a5d`: `PluginTraceLogWriter.ctor: enter`

## pseudocode

```c

```

## disassembly

```asm
0x6a50  ldarg.0
0x6a51  call     instance void [mscorlib]System.Object::.ctor()
0x6a56  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x6a5b  ldc.i4.s 0x28
0x6a5d  ldstr    aPlugintracelog_13// "PluginTraceLogWriter.ctor: enter"
0x6a62  ldc.i4.0
0x6a63  newarr   [mscorlib]System.Object
0x6a68  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x6a6d  ldarg.1
0x6a6e  ldstr    aPlugintracelog_3// "pluginTraceLogRecord"
0x6a73  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x6a78  ldarg.0
0x6a79  ldarg.1
0x6a7a  stfld    class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.PluginTraceLogRecord Microsoft.Crm.Sandbox.PluginTraceLogWriter::_ptlr
0x6a7f  ret
```
