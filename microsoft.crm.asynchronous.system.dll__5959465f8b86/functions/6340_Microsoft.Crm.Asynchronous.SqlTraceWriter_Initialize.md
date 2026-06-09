# Microsoft.Crm.Asynchronous.SqlTraceWriter::Initialize

- ea: `0x6340`
- end: `0x6371`
- name: `Microsoft.Crm.Asynchronous.SqlTraceWriter::Initialize`
- size: `49`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x6260`
- `0x6280`

## callees

- `0x6380`
- `0x63a0`

## string_xrefs

- `0x6341`: `traceDirectory`

## pseudocode

```c

```

## disassembly

```asm
0x6340  ldarg.1
0x6341  ldstr    aTracedirectory// "traceDirectory"
0x6346  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x634b  ldarg.2
0x634c  ldstr    aSqlfilename// "sqlFileName"
0x6351  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x6356  ldarg.0
0x6357  ldarg.1
0x6358  stfld    string Microsoft.Crm.Asynchronous.SqlTraceWriter::_traceDirectory
0x635d  ldarg.0
0x635e  ldarg.2
0x635f  stfld    string Microsoft.Crm.Asynchronous.SqlTraceWriter::_sqlFileName
0x6364  ldarg.0
0x6365  call     instance void Microsoft.Crm.Asynchronous.SqlTraceWriter::SetFullPath()
0x636a  ldarg.0
0x636b  call     instance void Microsoft.Crm.Asynchronous.SqlTraceWriter::SetStreamWriter()
0x6370  ret
```
