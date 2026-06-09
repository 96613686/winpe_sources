# Microsoft.Crm.Asynchronous.ImportDataAccess::CreateIndexOnParsedTable

- ea: `0x4630`
- end: `0x4663`
- name: `Microsoft.Crm.Asynchronous.ImportDataAccess::CreateIndexOnParsedTable`
- size: `51`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14370`

## callees

- `0x4540`
- `0x4630`

## string_xrefs

- `0x4635`: `CREATE UNIQUE INDEX importdataid_idx ON {0}(ImportDataId);\n																				CREATE NONCLUSTERED INDEX [idx_IsTransformed] ON {0}(IsTransformed)`

## pseudocode

```c

```

## disassembly

```asm
0x4630  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x4635  ldstr    aCreateUniqueIn// "CREATE UNIQUE INDEX importdataid_idx ON"...
0x463a  ldc.i4.1
0x463b  newarr   [mscorlib]System.Object
0x4640  dup
0x4641  ldc.i4.0
0x4642  ldarg.1
0x4643  stelem.ref
0x4644  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x4649  call     class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::NewCommand(string)
0x464e  stloc.0
0x464f  ldarg.0
0x4650  ldloc.0
0x4651  call     instance void Microsoft.Crm.Asynchronous.ImportDataAccess::ExecuteSqlCommandWithNoExpectedRecords(class [System.Data]System.Data.IDbCommand sqlCommand)
0x4656  leave.s  loc_4662
0x4658  ldloc.0
0x4659  brfalse.s loc_4661
0x465b  ldloc.0
0x465c  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x4661  endfinally
0x4662  ret
```
