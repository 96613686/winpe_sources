# Microsoft.Crm.Asynchronous.SqlTraceWriter::WriteSql

- ea: `0x6290`
- end: `0x62b6`
- name: `Microsoft.Crm.Asynchronous.SqlTraceWriter::WriteSql`
- size: `38`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x6290`
- `0x6320`
- `0x6330`

## pseudocode

```c

```

## disassembly

```asm
0x6290  ldarg.1
0x6291  brtrue.s loc_6294
0x6293  ret
0x6294  ldc.i4.s 0xA
0x6296  ldarg.2
0x6297  beq.s    loc_62A1
0x6299  ldarg.0
0x629a  ldarg.1
0x629b  call     instance void Microsoft.Crm.Asynchronous.SqlTraceWriter::WriteToFile(string sql)
0x62a0  ret
0x62a1  ldarg.0
0x62a2  ldarg.1
0x62a3  call     instance string Microsoft.Crm.Asynchronous.SqlTraceWriter::UnparameterizeSql(string sql)
0x62a8  stloc.0
0x62a9  ldloc.0
0x62aa  brtrue.s loc_62AE
0x62ac  ldarg.1
0x62ad  stloc.0
0x62ae  ldarg.0
0x62af  ldloc.0
0x62b0  call     instance void Microsoft.Crm.Asynchronous.SqlTraceWriter::WriteToFile(string sql)
0x62b5  ret
```
