# Microsoft.Crm.Asynchronous.SqmDatabaseAccessor::CollectSQMUserStats

- ea: `0x6d50`
- end: `0x6d8f`
- name: `Microsoft.Crm.Asynchronous.SqmDatabaseAccessor::CollectSQMUserStats`
- size: `63`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x4e70`

## callees

- `0x6d50`
- `0xea60`

## pseudocode

```c

```

## disassembly

```asm
0x6d50  newobj   instance void <>c__DisplayClass27_0::.ctor()
0x6d55  stloc.0
0x6d56  ldloc.0
0x6d57  ldarg.1
0x6d58  stfld    class [Microsoft.Crm]Microsoft.Crm.ISqmSession <>c__DisplayClass27_0::session
0x6d5d  call     class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::NewCommand()
0x6d62  stloc.1
0x6d63  ldloc.1
0x6d64  ldstr    aSelectIsdisabl// "select isdisabled, count(*) from system"...
0x6d69  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x6d6e  ldarg.0
0x6d6f  ldloc.1
0x6d70  ldloc.0
0x6d71  ldftn    instance void <>c__DisplayClass27_0::<CollectSQMUserStats>b__0(object[] values)
0x6d77  newobj   instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase/RecordProcessor::.ctor(object, native int)
0x6d7c  call     instance int32 [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase::ExecuteSqlCommandAndProcessRecords(class [System.Data]System.Data.IDbCommand, class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase/RecordProcessor)
0x6d81  pop
0x6d82  leave.s  loc_6D8E
0x6d84  ldloc.1
0x6d85  brfalse.s loc_6D8D
0x6d87  ldloc.1
0x6d88  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x6d8d  endfinally
0x6d8e  ret
```
