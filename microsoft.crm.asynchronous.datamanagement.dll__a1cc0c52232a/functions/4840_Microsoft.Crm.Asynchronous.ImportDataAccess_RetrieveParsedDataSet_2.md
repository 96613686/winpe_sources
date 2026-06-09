# Microsoft.Crm.Asynchronous.ImportDataAccess::RetrieveParsedDataSet_2

- ea: `0x4840`
- end: `0x48ef`
- name: `Microsoft.Crm.Asynchronous.ImportDataAccess::RetrieveParsedDataSet_2`
- size: `175`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x47e0`
- `0x4800`
- `0x4820`

## callees

- `0x4840`
- `0x48f0`
- `0x1fca0`

## pseudocode

```c

```

## disassembly

```asm
0x4840  newobj   instance void <>c__DisplayClass32_0::.ctor()
0x4845  stloc.0
0x4846  ldloc.0
0x4847  ldarg.3
0x4848  stfld    string[] <>c__DisplayClass32_0::columnNames
0x484d  ldloc.0
0x484e  ldarg.s  5
0x4850  stfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> <>c__DisplayClass32_0::parseTableColumnNewValueToParseTableColumnOldValueDictionary
0x4855  ldloc.0
0x4856  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x485b  ldstr    a00// "{0}0"
0x4860  ldc.i4.1
0x4861  newarr   [mscorlib]System.Object
0x4866  dup
0x4867  ldc.i4.0
0x4868  ldarg.2
0x4869  stelem.ref
0x486a  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x486f  stfld    string <>c__DisplayClass32_0::primaryKeyColumnName
0x4874  ldloc.0
0x4875  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::.ctor()
0x487a  stfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <>c__DisplayClass32_0::headerColumnForOldValueToColumnIndexDictionary
0x487f  ldarg.0
0x4880  ldloc.0
0x4881  ldfld    string[] <>c__DisplayClass32_0::columnNames
0x4886  ldarg.s  6
0x4888  ldarg.s  4
0x488a  ldloc.0
0x488b  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> <>c__DisplayClass32_0::parseTableColumnNewValueToParseTableColumnOldValueDictionary
0x4890  ldloc.0
0x4891  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <>c__DisplayClass32_0::headerColumnForOldValueToColumnIndexDictionary
0x4896  ldloc.0
0x4897  ldfld    string <>c__DisplayClass32_0::primaryKeyColumnName
0x489c  ldarg.1
0x489d  ldarg.s  7
0x489f  ldarg.s  8
0x48a1  ldarg.s  9
0x48a3  call     instance string Microsoft.Crm.Asynchronous.ImportDataAccess::ConstructCommandStringForParseDataSetRetrieval(string[] columnNames, string[] fullNameParseTableColumnNames, bool addIsExistingRecordCheck, class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> parseTableColumnNewValueToParseTableColumnOldValueDictionary, class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> headerColumnForOldValueToColumnIndexDictionary, string primaryKeyColumnName, string tableName, int64 lowerBound, int64 upperBound, int32 importFileStatusCode)
0x48a8  ldloc.0
0x48a9  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.ParsedDataRow>::.ctor()
0x48ae  stfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.ParsedDataRow> <>c__DisplayClass32_0::parsedDataRowArrayList
0x48b3  ldloc.0
0x48b4  ldloc.0
0x48b5  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> <>c__DisplayClass32_0::parseTableColumnNewValueToParseTableColumnOldValueDictionary
0x48ba  ldnull
0x48bb  ceq
0x48bd  stfld    bool <>c__DisplayClass32_0::maintainLegacyBehavior
0x48c2  call     class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::NewCommand(string)
0x48c7  stloc.1
0x48c8  ldarg.0
0x48c9  ldloc.1
0x48ca  ldloc.0
0x48cb  ldftn    instance void <>c__DisplayClass32_0::<RetrieveParsedDataSet>b__0(object[] values)
0x48d1  newobj   instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase/RecordProcessor::.ctor(object, native int)
0x48d6  call     instance int32 [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase::ExecuteSqlCommandAndProcessRecords(class [System.Data]System.Data.IDbCommand, class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase/RecordProcessor)
0x48db  pop
0x48dc  leave.s  loc_48E8
0x48de  ldloc.1
0x48df  brfalse.s loc_48E7
0x48e1  ldloc.1
0x48e2  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x48e7  endfinally
0x48e8  ldloc.0
0x48e9  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.ParsedDataRow> <>c__DisplayClass32_0::parsedDataRowArrayList
0x48ee  ret
```
