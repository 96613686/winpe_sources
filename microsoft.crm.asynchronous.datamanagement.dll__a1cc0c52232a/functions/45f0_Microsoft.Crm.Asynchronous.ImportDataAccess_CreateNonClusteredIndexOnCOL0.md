# Microsoft.Crm.Asynchronous.ImportDataAccess::CreateNonClusteredIndexOnCOL0

- ea: `0x45f0`
- end: `0x4627`
- name: `Microsoft.Crm.Asynchronous.ImportDataAccess::CreateNonClusteredIndexOnCOL0`
- size: `55`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x16690`

## callees

- `0x4540`
- `0x45f0`

## string_xrefs

- `0x45f5`: `if not exists (select 1 from sysindexes\n where id=object_id('{0}') and name='_dta_index_{0}_{1}0')\nCREATE NONCLUSTERED INDEX [_dta_index_{0}_{1}0] ON {0}({1}0) WITH (SORT_IN_TEMPDB = OFF, DROP_EXISTING = OFF, ONLINE = OFF)`

## pseudocode

```c

```

## disassembly

```asm
0x45f0  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x45f5  ldstr    aIfNotExistsSel_3// "if not exists (select 1 from sysindexes"...
0x45fa  ldc.i4.2
0x45fb  newarr   [mscorlib]System.Object
0x4600  dup
0x4601  ldc.i4.0
0x4602  ldarg.1
0x4603  stelem.ref
0x4604  dup
0x4605  ldc.i4.1
0x4606  ldarg.2
0x4607  stelem.ref
0x4608  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x460d  call     class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::NewCommand(string)
0x4612  stloc.0
0x4613  ldarg.0
0x4614  ldloc.0
0x4615  call     instance void Microsoft.Crm.Asynchronous.ImportDataAccess::ExecuteSqlCommandWithNoExpectedRecords(class [System.Data]System.Data.IDbCommand sqlCommand)
0x461a  leave.s  loc_4626
0x461c  ldloc.0
0x461d  brfalse.s loc_4625
0x461f  ldloc.0
0x4620  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x4625  endfinally
0x4626  ret
```
