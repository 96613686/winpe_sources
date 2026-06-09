# Microsoft.Crm.Asynchronous.ImportDataAccess::RetrieveParsedDataSet

- ea: `0x47e0`
- end: `0x47f4`
- name: `Microsoft.Crm.Asynchronous.ImportDataAccess::RetrieveParsedDataSet`
- size: `20`
- prototype: ``
- caller_count: `7`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x16f30`
- `0x17420`
- `0x17750`
- `0x19b90`
- `0x1b1e0`
- `0x1ba20`
- `0x1c630`

## callees

- `0x4840`

## pseudocode

```c

```

## disassembly

```asm
0x47e0  ldarg.0
0x47e1  ldarg.1
0x47e2  ldarg.2
0x47e3  ldarg.3
0x47e4  ldarg.s  4
0x47e6  ldnull
0x47e7  ldnull
0x47e8  ldarg.s  5
0x47ea  ldarg.s  6
0x47ec  ldarg.s  7
0x47ee  call     instance class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.ParsedDataRow> Microsoft.Crm.Asynchronous.ImportDataAccess::RetrieveParsedDataSet(string tableName, string parsedTableColumnPrefix, string[] columnNames, bool addIsExistingRecordCheck, class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> parseTableColumnNewValueToParseTableColumnOldValueDictionary, string[] fullNameParseTableColumnNames, int64 lowerBound, int64 upperBound, int32 importFileStatusCode)
0x47f3  ret
```
