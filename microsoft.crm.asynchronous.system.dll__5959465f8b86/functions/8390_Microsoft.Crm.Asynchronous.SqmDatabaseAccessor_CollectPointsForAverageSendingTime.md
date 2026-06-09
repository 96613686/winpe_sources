# Microsoft.Crm.Asynchronous.SqmDatabaseAccessor::CollectPointsForAverageSendingTime

- ea: `0x8390`
- end: `0x83e0`
- name: `Microsoft.Crm.Asynchronous.SqmDatabaseAccessor::CollectPointsForAverageSendingTime`
- size: `80`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x8240`

## callees

- `0x8390`
- `0xf0f0`

## pseudocode

```c

```

## disassembly

```asm
0x8390  newobj   instance void <>c__DisplayClass49_0::.ctor()
0x8395  stloc.0
0x8396  ldloc.0
0x8397  ldc.i4.0
0x8398  stfld    int32 <>c__DisplayClass49_0::AverageSendingTime
0x839d  call     class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::NewCommand()
0x83a2  stloc.1
0x83a3  ldloc.1
0x83a4  ldstr    aSelectCastAvgC// "SELECT  CAST(AVG(CAST(ActualEnd as Floa"...
0x83a9  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x83ae  ldarg.0
0x83af  ldloc.1
0x83b0  ldloc.0
0x83b1  ldftn    instance void <>c__DisplayClass49_0::<CollectPointsForAverageSendingTime>b__0(object[] values)
0x83b7  newobj   instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase/RecordProcessor::.ctor(object, native int)
0x83bc  call     instance int32 [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase::ExecuteSqlCommandAndProcessRecords(class [System.Data]System.Data.IDbCommand, class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase/RecordProcessor)
0x83c1  pop
0x83c2  leave.s  loc_83CE
0x83c4  ldloc.1
0x83c5  brfalse.s loc_83CD
0x83c7  ldloc.1
0x83c8  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x83cd  endfinally
0x83ce  ldarg.1
0x83cf  ldc.i4   0x23D
0x83d4  ldloc.0
0x83d5  ldfld    int32 <>c__DisplayClass49_0::AverageSendingTime
0x83da  callvirt instance void [Microsoft.Crm]Microsoft.Crm.ISqmSession::set_Item(valuetype [Microsoft.Crm]Microsoft.Crm.SqmDataPointId, int32)
0x83df  ret
```
