# Microsoft.Crm.Asynchronous.SqmDatabaseAccessor::CollectListMemberCountPerMarketingList

- ea: `0x68e0`
- end: `0x691f`
- name: `Microsoft.Crm.Asynchronous.SqmDatabaseAccessor::CollectListMemberCountPerMarketingList`
- size: `63`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x4eb0`

## callees

- `0x68e0`
- `0xe6e0`

## pseudocode

```c

```

## disassembly

```asm
0x68e0  newobj   instance void <>c__DisplayClass16_0::.ctor()
0x68e5  stloc.0
0x68e6  ldloc.0
0x68e7  ldarg.1
0x68e8  stfld    class [Microsoft.Crm]Microsoft.Crm.ISqmSession <>c__DisplayClass16_0::session
0x68ed  call     class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::NewCommand()
0x68f2  stloc.1
0x68f3  ldloc.1
0x68f4  ldstr    aSelectCountCon// "SELECT COUNT(CONVERT(varchar(64),ListMe"...
0x68f9  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x68fe  ldarg.0
0x68ff  ldloc.1
0x6900  ldloc.0
0x6901  ldftn    instance void <>c__DisplayClass16_0::<CollectListMemberCountPerMarketingList>b__0(object[] values)
0x6907  newobj   instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase/RecordProcessor::.ctor(object, native int)
0x690c  call     instance int32 [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase::ExecuteSqlCommandAndProcessRecords(class [System.Data]System.Data.IDbCommand, class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase/RecordProcessor)
0x6911  pop
0x6912  leave.s  loc_691E
0x6914  ldloc.1
0x6915  brfalse.s loc_691D
0x6917  ldloc.1
0x6918  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x691d  endfinally
0x691e  ret
```
