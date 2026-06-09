# Microsoft.Crm.Asynchronous.SqlTraceWriter::Dispose_0

- ea: `0x62f0`
- end: `0x630f`
- name: `Microsoft.Crm.Asynchronous.SqlTraceWriter::Dispose_0`
- size: `31`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x62e0`

## callees

- `0x62f0`

## pseudocode

```c

```

## disassembly

```asm
0x62f0  ldarg.0
0x62f1  ldfld    bool Microsoft.Crm.Asynchronous.SqlTraceWriter::_disposed
0x62f6  brfalse.s loc_62F9
0x62f8  ret
0x62f9  ldarg.1
0x62fa  brfalse.s loc_6307
0x62fc  ldarg.0
0x62fd  ldfld    class [mscorlib]System.IO.StreamWriter Microsoft.Crm.Asynchronous.SqlTraceWriter::_writer
0x6302  callvirt instance void [mscorlib]System.IO.TextWriter::Dispose()
0x6307  ldarg.0
0x6308  ldc.i4.1
0x6309  stfld    bool Microsoft.Crm.Asynchronous.SqlTraceWriter::_disposed
0x630e  ret
```
