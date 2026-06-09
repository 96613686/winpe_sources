# Microsoft.Crm.Asynchronous.ImportDataAccess::RetrieveParsedDataSet_0

- ea: `0x4800`
- end: `0x4815`
- name: `Microsoft.Crm.Asynchronous.ImportDataAccess::RetrieveParsedDataSet_0`
- size: `21`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x16f30`

## callees

- `0x4840`

## pseudocode

```c

```

## disassembly

```asm
0x4800  ldarg.0
0x4801  ldarg.1
0x4802  ldarg.2
0x4803  ldarg.3
0x4804  ldarg.s  4
0x4806  ldnull
0x4807  ldarg.s  5
0x4809  ldarg.s  6
0x480b  ldarg.s  7
0x480d  ldarg.s  8
0x480f  call     instance class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.ParsedDataRow> Microsoft.Crm.Asynchronous.ImportDataAccess::RetrieveParsedDataSet(string tableName, string parsedTableColumnPrefix, string[] columnNames, bool addIsExistingRecordCheck, class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> parseTableColumnNewValueToParseTableColumnOldValueDictionary, string[] fullNameParseTableColumnNames, int64 lowerBound, int64 upperBound, int32 importFileStatusCode)
0x4814  ret
```
