# Microsoft.Crm.Asynchronous.SqlTraceWriter::.ctor

- ea: `0x6260`
- end: `0x6278`
- name: `Microsoft.Crm.Asynchronous.SqlTraceWriter::.ctor`
- size: `24`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1f60`

## callees

- `0x2230`
- `0x6340`

## pseudocode

```c

```

## disassembly

```asm
0x6260  ldarg.0
0x6261  call     instance void [mscorlib]System.Object::.ctor()
0x6266  ldarg.0
0x6267  ldarg.1
0x6268  ldstr    aSql// ".sql"
0x626d  call     string Microsoft.Crm.Asynchronous.DatabaseTuningUtility::GenerateUniqueFileName(string suffix)
0x6272  call     instance void Microsoft.Crm.Asynchronous.SqlTraceWriter::Initialize(string traceDirectory, string sqlFileName)
0x6277  ret
```
