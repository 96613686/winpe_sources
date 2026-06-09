# Microsoft.Crm.Asynchronous.ImportDataAccess::RetrieveSourceUsersFromParseTable

- ea: `0x55f0`
- end: `0x5660`
- name: `Microsoft.Crm.Asynchronous.ImportDataAccess::RetrieveSourceUsersFromParseTable`
- size: `112`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x55f0`
- `0x1fff0`

## pseudocode

```c

```

## disassembly

```asm
0x55f0  newobj   instance void <>c__DisplayClass42_0::.ctor()
0x55f5  stloc.0
0x55f6  ldloc.0
0x55f7  ldarg.3
0x55f8  stfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, bool> <>c__DisplayClass42_0::sourceUserMappingInformation
0x55fd  ldarg.1
0x55fe  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x5603  brtrue.s loc_560D
0x5605  ldarg.2
0x5606  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x560b  brfalse.s loc_560E
0x560d  ret
0x560e  ldstr    aSelectDistinct// "SELECT DISTINCT "
0x5613  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor(string)
0x5618  dup
0x5619  ldarg.2
0x561a  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x561f  pop
0x5620  dup
0x5621  ldstr    aFrom// " FROM "
0x5626  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x562b  pop
0x562c  dup
0x562d  ldarg.1
0x562e  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x5633  pop
0x5634  callvirt instance string [mscorlib]System.Object::ToString()
0x5639  call     class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::NewCommand(string)
0x563e  stloc.1
0x563f  ldarg.0
0x5640  ldloc.1
0x5641  ldloc.0
0x5642  ldftn    instance void <>c__DisplayClass42_0::<RetrieveSourceUsersFromParseTable>b__0(object[] values)
0x5648  newobj   instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase/RecordProcessor::.ctor(object, native int)
0x564d  call     instance int32 [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase::ExecuteSqlCommandAndProcessRecords(class [System.Data]System.Data.IDbCommand, class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase/RecordProcessor)
0x5652  pop
0x5653  leave.s  loc_565F
0x5655  ldloc.1
0x5656  brfalse.s loc_565E
0x5658  ldloc.1
0x5659  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x565e  endfinally
0x565f  ret
```
