# Microsoft.Crm.Asynchronous.ImportOperationParse::FlushParseTables

- ea: `0x15f30`
- end: `0x15f3e`
- name: `Microsoft.Crm.Asynchronous.ImportOperationParse::FlushParseTables`
- size: `14`
- prototype: ``
- caller_count: `7`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14940`
- `0x14cb0`
- `0x15220`
- `0x156f0`
- `0x15b80`
- `0x15d20`
- `0x163d0`

## callees

- `0x15f40`
- `0x15f80`

## pseudocode

```c

```

## disassembly

```asm
0x15f30  ldarg.0
0x15f31  call     instance void Microsoft.Crm.Asynchronous.ImportOperationParse::FlushImportDataTable()
0x15f36  ldarg.0
0x15f37  ldarg.1
0x15f38  call     instance void Microsoft.Crm.Asynchronous.ImportOperationParse::FlushParseDataTable(string parsedTableName)
0x15f3d  ret
```
