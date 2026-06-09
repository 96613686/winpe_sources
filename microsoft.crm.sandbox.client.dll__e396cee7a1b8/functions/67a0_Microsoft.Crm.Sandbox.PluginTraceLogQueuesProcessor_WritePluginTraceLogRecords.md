# Microsoft.Crm.Sandbox.PluginTraceLogQueuesProcessor::WritePluginTraceLogRecords

- ea: `0x67a0`
- end: `0x67c9`
- name: `Microsoft.Crm.Sandbox.PluginTraceLogQueuesProcessor::WritePluginTraceLogRecords`
- size: `41`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x9370`

## callees

- `0x67a0`
- `0x67d0`

## string_xrefs

- `0x67b2`: `WritePluginTraceLogRecords: {0}`

## pseudocode

```c

```

## disassembly

```asm
0x67a0  ldarg.0
0x67a1  ldarg.1
0x67a2  call     instance void Microsoft.Crm.Sandbox.PluginTraceLogQueuesProcessor::InternalWritePluginTraceLogRecords(valuetype [mscorlib]System.Threading.CancellationToken cancellationToken)
0x67a7  leave.s  loc_67C8
0x67a9  stloc.0
0x67aa  ldloc.0
0x67ab  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x67b0  ldc.i4.s 0x28
0x67b2  ldstr    aWriteplugintra// "WritePluginTraceLogRecords: {0}"
0x67b7  ldc.i4.1
0x67b8  newarr   [mscorlib]System.Object
0x67bd  dup
0x67be  ldc.i4.0
0x67bf  ldloc.0
0x67c0  stelem.ref
0x67c1  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x67c6  leave.s  loc_67C8
0x67c8  ret
```
