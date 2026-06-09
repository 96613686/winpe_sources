# Microsoft.Crm.Asynchronous.SqlTraceWriter::UnparameterizeSql

- ea: `0x6330`
- end: `0x6337`
- name: `Microsoft.Crm.Asynchronous.SqlTraceWriter::UnparameterizeSql`
- size: `7`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x6290`

## callees

- `0x63d0`

## pseudocode

```c

```

## disassembly

```asm
0x6330  ldarg.1
0x6331  call     string Microsoft.Crm.Asynchronous.SqlUnparameterizer::UnparameterizeSql(string sql)
0x6336  ret
```
