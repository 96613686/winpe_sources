# Microsoft.Crm.Asynchronous.ImportDataAccess::RetrieveParsedDataSet_1

- ea: `0x4820`
- end: `0x4835`
- name: `Microsoft.Crm.Asynchronous.ImportDataAccess::RetrieveParsedDataSet_1`
- size: `21`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x19b90`
- `0x1b1e0`

## callees

- `0x4840`

## pseudocode

```c

```

## disassembly

```asm
0x4820  ldarg.0
0x4821  ldarg.1
0x4822  ldarg.2
0x4823  ldarg.3
0x4824  ldarg.s  4
0x4826  ldarg.s  5
0x4828  ldnull
0x4829  ldarg.s  6
0x482b  ldarg.s  7
0x482d  ldarg.s  8
0x482f  call     instance class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.ParsedDataRow> Microsoft.Crm.Asynchronous.ImportDataAccess::RetrieveParsedDataSet(string tableName, string parsedTableColumnPrefix, string[] columnNames, bool addIsExistingRecordCheck, class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> parseTableColumnNewValueToParseTableColumnOldValueDictionary, string[] fullNameParseTableColumnNames, int64 lowerBound, int64 upperBound, int32 importFileStatusCode)
0x4834  ret
```
