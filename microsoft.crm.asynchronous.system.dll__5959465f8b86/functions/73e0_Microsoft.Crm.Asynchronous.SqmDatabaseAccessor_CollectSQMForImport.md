# Microsoft.Crm.Asynchronous.SqmDatabaseAccessor::CollectSQMForImport

- ea: `0x73e0`
- end: `0x7559`
- name: `Microsoft.Crm.Asynchronous.SqmDatabaseAccessor::CollectSQMForImport`
- size: `377`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x5250`

## callees

- `0x73e0`
- `0xec80`

## pseudocode

```c

```

## disassembly

```asm
0x73e0  newobj   instance void <>c__DisplayClass33_0::.ctor()
0x73e5  stloc.0
0x73e6  ldloc.0
0x73e7  ldarg.1
0x73e8  stfld    class [Microsoft.Crm]Microsoft.Crm.ISqmSession <>c__DisplayClass33_0::session
0x73ed  call     class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::NewCommand()
0x73f2  stloc.1
0x73f3  ldloc.1
0x73f4  ldstr    aSelectCountFro_13// "select count(*) from importfilebase,imp"...
0x73f9  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x73fe  ldarg.0
0x73ff  ldloc.1
0x7400  ldloc.0
0x7401  ldftn    instance void <>c__DisplayClass33_0::<CollectSQMForImport>b__0(object[] values)
0x7407  newobj   instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase/RecordProcessor::.ctor(object, native int)
0x740c  call     instance int32 [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase::ExecuteSqlCommandAndProcessRecords(class [System.Data]System.Data.IDbCommand, class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase/RecordProcessor)
0x7411  pop
0x7412  leave.s  loc_741E
0x7414  ldloc.1
0x7415  brfalse.s loc_741D
0x7417  ldloc.1
0x7418  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x741d  endfinally
0x741e  call     class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::NewCommand()
0x7423  stloc.2
0x7424  ldloc.2
0x7425  ldstr    aSelectCountFro_14// "select count(*) from importfilebase,imp"...
0x742a  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x742f  ldarg.0
0x7430  ldloc.2
0x7431  ldloc.0
0x7432  ldftn    instance void <>c__DisplayClass33_0::<CollectSQMForImport>b__1(object[] values)
0x7438  newobj   instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase/RecordProcessor::.ctor(object, native int)
0x743d  call     instance int32 [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase::ExecuteSqlCommandAndProcessRecords(class [System.Data]System.Data.IDbCommand, class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase/RecordProcessor)
0x7442  pop
0x7443  leave.s  loc_744F
0x7445  ldloc.2
0x7446  brfalse.s loc_744E
0x7448  ldloc.2
0x7449  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x744e  endfinally
0x744f  call     class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::NewCommand()
0x7454  stloc.3
0x7455  ldloc.3
0x7456  ldstr    aSelectCountFro_15// "select count(*) from importfilebase,imp"...
0x745b  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x7460  ldarg.0
0x7461  ldloc.3
0x7462  ldloc.0
0x7463  ldftn    instance void <>c__DisplayClass33_0::<CollectSQMForImport>b__2(object[] values)
0x7469  newobj   instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase/RecordProcessor::.ctor(object, native int)
0x746e  call     instance int32 [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase::ExecuteSqlCommandAndProcessRecords(class [System.Data]System.Data.IDbCommand, class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase/RecordProcessor)
0x7473  pop
0x7474  leave.s  loc_7480
0x7476  ldloc.3
0x7477  brfalse.s loc_747F
0x7479  ldloc.3
0x747a  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x747f  endfinally
0x7480  call     class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::NewCommand()
0x7485  stloc.s  4
0x7487  ldloc.s  4
0x7489  ldstr    aSelectSumTotal// "select sum(TotalCount) from importfileb"...
0x748e  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x7493  ldarg.0
0x7494  ldloc.s  4
0x7496  ldloc.0
0x7497  ldftn    instance void <>c__DisplayClass33_0::<CollectSQMForImport>b__3(object[] values)
0x749d  newobj   instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase/RecordProcessor::.ctor(object, native int)
0x74a2  call     instance int32 [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase::ExecuteSqlCommandAndProcessRecords(class [System.Data]System.Data.IDbCommand, class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase/RecordProcessor)
0x74a7  pop
0x74a8  leave.s  loc_74B6
0x74aa  ldloc.s  4
0x74ac  brfalse.s loc_74B5
0x74ae  ldloc.s  4
0x74b0  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x74b5  endfinally
0x74b6  call     class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::NewCommand()
0x74bb  stloc.s  5
0x74bd  ldloc.s  5
0x74bf  ldstr    aSelectObjectty_0// "select ObjectTypeCode as entityCode,cou"...
0x74c4  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x74c9  ldarg.0
0x74ca  ldloc.s  5
0x74cc  ldloc.0
0x74cd  ldftn    instance void <>c__DisplayClass33_0::<CollectSQMForImport>b__4(object[] values)
0x74d3  newobj   instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase/RecordProcessor::.ctor(object, native int)
0x74d8  call     instance int32 [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase::ExecuteSqlCommandAndProcessRecords(class [System.Data]System.Data.IDbCommand, class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase/RecordProcessor)
0x74dd  pop
0x74de  leave.s  loc_74EC
0x74e0  ldloc.s  5
0x74e2  brfalse.s loc_74EB
0x74e4  ldloc.s  5
0x74e6  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x74eb  endfinally
0x74ec  call     class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::NewCommand()
0x74f1  stloc.s  6
0x74f3  ldloc.s  6
0x74f5  ldstr    aSelectCountFro_16// "select count(*) from importfilebase,imp"...
0x74fa  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x74ff  ldarg.0
0x7500  ldloc.s  6
0x7502  ldloc.0
0x7503  ldftn    instance void <>c__DisplayClass33_0::<CollectSQMForImport>b__5(object[] values)
0x7509  newobj   instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase/RecordProcessor::.ctor(object, native int)
0x750e  call     instance int32 [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase::ExecuteSqlCommandAndProcessRecords(class [System.Data]System.Data.IDbCommand, class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase/RecordProcessor)
0x7513  pop
0x7514  leave.s  loc_7522
0x7516  ldloc.s  6
0x7518  brfalse.s loc_7521
0x751a  ldloc.s  6
0x751c  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x7521  endfinally
0x7522  call     class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::NewCommand()
0x7527  stloc.s  7
0x7529  ldloc.s  7
0x752b  ldstr    aSelectCountFro_17// "select count(*) from importmapbase wher"...
0x7530  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x7535  ldarg.0
0x7536  ldloc.s  7
0x7538  ldloc.0
0x7539  ldftn    instance void <>c__DisplayClass33_0::<CollectSQMForImport>b__6(object[] values)
0x753f  newobj   instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase/RecordProcessor::.ctor(object, native int)
0x7544  call     instance int32 [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase::ExecuteSqlCommandAndProcessRecords(class [System.Data]System.Data.IDbCommand, class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase/RecordProcessor)
0x7549  pop
0x754a  leave.s  loc_7558
0x754c  ldloc.s  7
0x754e  brfalse.s loc_7557
0x7550  ldloc.s  7
0x7552  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x7557  endfinally
0x7558  ret
```
