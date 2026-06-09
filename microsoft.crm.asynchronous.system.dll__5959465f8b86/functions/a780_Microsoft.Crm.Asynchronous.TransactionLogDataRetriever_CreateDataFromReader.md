# Microsoft.Crm.Asynchronous.TransactionLogDataRetriever::CreateDataFromReader

- ea: `0xa780`
- end: `0xa7ed`
- name: `Microsoft.Crm.Asynchronous.TransactionLogDataRetriever::CreateDataFromReader`
- size: `109`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0xa6f0`

## callees

- `0xa350`
- `0xa3b0`
- `0xa3d0`
- `0xa3f0`
- `0xa410`

## pseudocode

```c

```

## disassembly

```asm
0xa780  newobj   instance void Microsoft.Crm.Asynchronous.TransactionLogData::.ctor()
0xa785  dup
0xa786  ldarg.0
0xa787  ldstr    aCurrentsizeinm// "CurrentSizeInMB"
0xa78c  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0xa791  unbox.any [mscorlib]System.Decimal
0xa796  call     float64 [mscorlib]System.Decimal::ToDouble(valuetype [mscorlib]System.Decimal)
0xa79b  callvirt instance void Microsoft.Crm.Asynchronous.TransactionLogData::set_CurrentSizeInMB(float64 value)
0xa7a0  dup
0xa7a1  ldarg.0
0xa7a2  ldstr    aFilesizeinmb// "FileSizeInMB"
0xa7a7  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0xa7ac  unbox.any [mscorlib]System.Decimal
0xa7b1  call     float64 [mscorlib]System.Decimal::ToDouble(valuetype [mscorlib]System.Decimal)
0xa7b6  callvirt instance void Microsoft.Crm.Asynchronous.TransactionLogData::set_FileSizeInMB(float64 value)
0xa7bb  dup
0xa7bc  ldarg.0
0xa7bd  ldstr    aTlogusage// "TLogUsage"
0xa7c2  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0xa7c7  unbox.any [mscorlib]System.Decimal
0xa7cc  call     float64 [mscorlib]System.Decimal::ToDouble(valuetype [mscorlib]System.Decimal)
0xa7d1  callvirt instance void Microsoft.Crm.Asynchronous.TransactionLogData::set_TLogUsage(float64 value)
0xa7d6  dup
0xa7d7  ldarg.0
0xa7d8  ldstr    aDatabasename// "DatabaseName"
0xa7dd  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0xa7e2  castclass [mscorlib]System.String
0xa7e7  callvirt instance void Microsoft.Crm.Asynchronous.TransactionLogData::set_DatabaseName(string value)
0xa7ec  ret
```
