# Microsoft.Crm.Asynchronous.SqmDatabaseAccessor::CollectSQMForDeDup

- ea: `0x6bd0`
- end: `0x6d50`
- name: `Microsoft.Crm.Asynchronous.SqmDatabaseAccessor::CollectSQMForDeDup`
- size: `384`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callers

- `0x51d0`

## callees

- `0x6bd0`
- `0xe8c0`

## string_xrefs

- `0x6be4`: `select IsDuplicateDetectionEnabled,IsDuplicateDetectionEnabledForOnlineCreateUpdate,IsDuplicateDetectionEnabledForOfflineSync,IsDuplicateDetectionEnabledForImport from organizationbase`

## pseudocode

```c

```

## disassembly

```asm
0x6bd0  newobj   instance void <>c__DisplayClass26_0::.ctor()
0x6bd5  stloc.0
0x6bd6  ldloc.0
0x6bd7  ldarg.1
0x6bd8  stfld    class [Microsoft.Crm]Microsoft.Crm.ISqmSession <>c__DisplayClass26_0::session
0x6bdd  call     class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::NewCommand()
0x6be2  stloc.1
0x6be3  ldloc.1
0x6be4  ldstr    aSelectIsduplic// "select IsDuplicateDetectionEnabled,IsDu"...
0x6be9  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x6bee  ldarg.0
0x6bef  ldloc.1
0x6bf0  ldloc.0
0x6bf1  ldftn    instance void <>c__DisplayClass26_0::<CollectSQMForDeDup>b__0(object[] values)
0x6bf7  newobj   instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase/RecordProcessor::.ctor(object, native int)
0x6bfc  call     instance int32 [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase::ExecuteSqlCommandAndProcessRecords(class [System.Data]System.Data.IDbCommand, class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase/RecordProcessor)
0x6c01  pop
0x6c02  leave.s  loc_6C0E
0x6c04  ldloc.1
0x6c05  brfalse.s loc_6C0D
0x6c07  ldloc.1
0x6c08  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x6c0d  endfinally
0x6c0e  call     class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::NewCommand()
0x6c13  stloc.2
0x6c14  ldloc.2
0x6c15  ldstr    aSelectCountFro_4// "select count(*) from duplicaterulebase "...
0x6c1a  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x6c1f  ldarg.0
0x6c20  ldloc.2
0x6c21  ldloc.0
0x6c22  ldftn    instance void <>c__DisplayClass26_0::<CollectSQMForDeDup>b__1(object[] values)
0x6c28  newobj   instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase/RecordProcessor::.ctor(object, native int)
0x6c2d  call     instance int32 [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase::ExecuteSqlCommandAndProcessRecords(class [System.Data]System.Data.IDbCommand, class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase/RecordProcessor)
0x6c32  pop
0x6c33  leave.s  loc_6C3F
0x6c35  ldloc.2
0x6c36  brfalse.s loc_6C3E
0x6c38  ldloc.2
0x6c39  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x6c3e  endfinally
0x6c3f  call     class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::NewCommand()
0x6c44  stloc.3
0x6c45  ldloc.3
0x6c46  ldstr    aSelectCountDis_2// "select count(distinct BaseEntityName) f"...
0x6c4b  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x6c50  ldarg.0
0x6c51  ldloc.3
0x6c52  ldloc.0
0x6c53  ldftn    instance void <>c__DisplayClass26_0::<CollectSQMForDeDup>b__2(object[] values)
0x6c59  newobj   instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase/RecordProcessor::.ctor(object, native int)
0x6c5e  call     instance int32 [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase::ExecuteSqlCommandAndProcessRecords(class [System.Data]System.Data.IDbCommand, class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase/RecordProcessor)
0x6c63  pop
0x6c64  leave.s  loc_6C70
0x6c66  ldloc.3
0x6c67  brfalse.s loc_6C6F
0x6c69  ldloc.3
0x6c6a  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x6c6f  endfinally
0x6c70  call     class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::NewCommand()
0x6c75  stloc.s  4
0x6c77  ldloc.s  4
0x6c79  ldstr    aSelectCountCou// "select count(*),count(distinct BaseEnti"...
0x6c7e  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x6c83  ldarg.0
0x6c84  ldloc.s  4
0x6c86  ldloc.0
0x6c87  ldftn    instance void <>c__DisplayClass26_0::<CollectSQMForDeDup>b__3(object[] values)
0x6c8d  newobj   instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase/RecordProcessor::.ctor(object, native int)
0x6c92  call     instance int32 [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase::ExecuteSqlCommandAndProcessRecords(class [System.Data]System.Data.IDbCommand, class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase/RecordProcessor)
0x6c97  pop
0x6c98  leave.s  loc_6CA6
0x6c9a  ldloc.s  4
0x6c9c  brfalse.s loc_6CA5
0x6c9e  ldloc.s  4
0x6ca0  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x6ca5  endfinally
0x6ca6  call     class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::NewCommand()
0x6cab  stloc.s  5
0x6cad  ldloc.s  5
0x6caf  ldstr    aSelectCountFro_5// "select count(*)  from duplicaterecordba"...
0x6cb4  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x6cb9  ldarg.0
0x6cba  ldloc.s  5
0x6cbc  ldloc.0
0x6cbd  ldftn    instance void <>c__DisplayClass26_0::<CollectSQMForDeDup>b__4(object[] values)
0x6cc3  newobj   instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase/RecordProcessor::.ctor(object, native int)
0x6cc8  call     instance int32 [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase::ExecuteSqlCommandAndProcessRecords(class [System.Data]System.Data.IDbCommand, class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase/RecordProcessor)
0x6ccd  pop
0x6cce  leave.s  loc_6CDC
0x6cd0  ldloc.s  5
0x6cd2  brfalse.s loc_6CDB
0x6cd4  ldloc.s  5
0x6cd6  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x6cdb  endfinally
0x6cdc  ldloc.0
0x6cdd  ldc.i4.0
0x6cde  stfld    int32 <>c__DisplayClass26_0::RecurringBulkDeletionJobs
0x6ce3  call     class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::NewCommand()
0x6ce8  stloc.s  6
0x6cea  ldloc.s  6
0x6cec  ldstr    aSelectCountFro_6// "select count(*) from asyncoperationbase"...
0x6cf1  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x6cf6  ldarg.0
0x6cf7  ldloc.s  6
0x6cf9  ldloc.0
0x6cfa  ldftn    instance void <>c__DisplayClass26_0::<CollectSQMForDeDup>b__5(object[] values)
0x6d00  newobj   instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase/RecordProcessor::.ctor(object, native int)
0x6d05  call     instance int32 [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase::ExecuteSqlCommandAndProcessRecords(class [System.Data]System.Data.IDbCommand, class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase/RecordProcessor)
0x6d0a  pop
0x6d0b  leave.s  loc_6D19
0x6d0d  ldloc.s  6
0x6d0f  brfalse.s loc_6D18
0x6d11  ldloc.s  6
0x6d13  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x6d18  endfinally
0x6d19  call     class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::NewCommand()
0x6d1e  stloc.s  7
0x6d20  ldloc.s  7
0x6d22  ldstr    aSelectCountFro_7// "select count(*) from asyncoperationbase"...
0x6d27  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x6d2c  ldarg.0
0x6d2d  ldloc.s  7
0x6d2f  ldloc.0
0x6d30  ldftn    instance void <>c__DisplayClass26_0::<CollectSQMForDeDup>b__6(object[] values)
0x6d36  newobj   instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase/RecordProcessor::.ctor(object, native int)
0x6d3b  call     instance int32 [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase::ExecuteSqlCommandAndProcessRecords(class [System.Data]System.Data.IDbCommand, class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase/RecordProcessor)
0x6d40  pop
0x6d41  leave.s  loc_6D4F
0x6d43  ldloc.s  7
0x6d45  brfalse.s loc_6D4E
0x6d47  ldloc.s  7
0x6d49  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x6d4e  endfinally
0x6d4f  ret
```
