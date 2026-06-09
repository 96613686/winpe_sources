# Microsoft.Crm.Sandbox.PluginTraceLogWriter::ConfirmWrite

- ea: `0x6ce0`
- end: `0x6d14`
- name: `Microsoft.Crm.Sandbox.PluginTraceLogWriter::ConfirmWrite`
- size: `52`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `loader_planting, broker_com_uri`

## string_xrefs

- `0x6ce7`: `PluginTraceLogWriter.ConfirmWrite: enter`

## pseudocode

```c

```

## disassembly

```asm
0x6ce0  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x6ce5  ldc.i4.s 0x28
0x6ce7  ldstr    aPlugintracelog_17// "PluginTraceLogWriter.ConfirmWrite: ente"...
0x6cec  ldc.i4.0
0x6ced  newarr   [mscorlib]System.Object
0x6cf2  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x6cf7  ldarg.0
0x6cf8  ldfld    class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.PluginTraceLogRecord Microsoft.Crm.Sandbox.PluginTraceLogWriter::_ptlr
0x6cfd  ldstr    aPtlr// "_ptlr"
0x6d02  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x6d07  ldarg.0
0x6d08  ldfld    class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.PluginTraceLogRecord Microsoft.Crm.Sandbox.PluginTraceLogWriter::_ptlr
0x6d0d  ldc.i4.1
0x6d0e  callvirt instance void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.PluginTraceLogRecord::set_WrittenToStorage(bool)
0x6d13  ret
```
