# Microsoft.Crm.Asynchronous.TraceResultsProcessor::Initialize

- ea: `0x9b30`
- end: `0x9b55`
- name: `Microsoft.Crm.Asynchronous.TraceResultsProcessor::Initialize`
- size: `37`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x9a70`

## string_xrefs

- `0x9b3c`: `traceFullPath`

## pseudocode

```c

```

## disassembly

```asm
0x9b30  ldarg.1
0x9b31  ldstr    aConnection// "connection"
0x9b36  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x9b3b  ldarg.2
0x9b3c  ldstr    aTracefullpath// "traceFullPath"
0x9b41  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x9b46  ldarg.0
0x9b47  ldarg.1
0x9b48  stfld    class [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection Microsoft.Crm.Asynchronous.TraceResultsProcessor::_connection
0x9b4d  ldarg.0
0x9b4e  ldarg.2
0x9b4f  stfld    string Microsoft.Crm.Asynchronous.TraceResultsProcessor::_fullTracePath
0x9b54  ret
```
