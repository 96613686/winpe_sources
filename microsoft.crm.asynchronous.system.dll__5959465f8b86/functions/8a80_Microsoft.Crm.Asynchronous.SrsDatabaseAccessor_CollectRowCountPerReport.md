# Microsoft.Crm.Asynchronous.SrsDatabaseAccessor::CollectRowCountPerReport

- ea: `0x8a80`
- end: `0x8abf`
- name: `Microsoft.Crm.Asynchronous.SrsDatabaseAccessor::CollectRowCountPerReport`
- size: `63`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x4de0`

## callees

- `0x8a80`
- `0xf670`

## pseudocode

```c

```

## disassembly

```asm
0x8a80  newobj   instance void <>c__DisplayClass3_0::.ctor()
0x8a85  stloc.0
0x8a86  ldloc.0
0x8a87  ldarg.1
0x8a88  stfld    class [Microsoft.Crm]Microsoft.Crm.ISqmSession <>c__DisplayClass3_0::session
0x8a8d  call     class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::NewCommand()
0x8a92  stloc.1
0x8a93  ldloc.1
0x8a94  ldstr    aSelectRowcount// "SELECT [RowCount] FROM ExecutionLog WHE"...
0x8a99  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x8a9e  ldarg.0
0x8a9f  ldloc.1
0x8aa0  ldloc.0
0x8aa1  ldftn    instance void <>c__DisplayClass3_0::<CollectRowCountPerReport>b__0(object[] values)
0x8aa7  newobj   instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase/RecordProcessor::.ctor(object, native int)
0x8aac  call     instance int32 [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase::ExecuteSqlCommandAndProcessRecords(class [System.Data]System.Data.IDbCommand, class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase/RecordProcessor)
0x8ab1  pop
0x8ab2  leave.s  loc_8ABE
0x8ab4  ldloc.1
0x8ab5  brfalse.s loc_8ABD
0x8ab7  ldloc.1
0x8ab8  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x8abd  endfinally
0x8abe  ret
```
