# Microsoft.Crm.Asynchronous.SqmDatabaseAccessor::CollectSQMForDocumentManagement

- ea: `0x76e0`
- end: `0x77ed`
- name: `Microsoft.Crm.Asynchronous.SqmDatabaseAccessor::CollectSQMForDocumentManagement`
- size: `269`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x5210`

## callees

- `0x76e0`
- `0xeda0`

## pseudocode

```c

```

## disassembly

```asm
0x76e0  newobj   instance void <>c__DisplayClass35_0::.ctor()
0x76e5  stloc.0
0x76e6  ldloc.0
0x76e7  ldarg.1
0x76e8  stfld    class [Microsoft.Crm]Microsoft.Crm.ISqmSession <>c__DisplayClass35_0::session
0x76ed  call     class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::NewCommand()
0x76f2  stloc.1
0x76f3  ldloc.1
0x76f4  ldstr    aSelectCountFro_18// "select count(*) from SharePointSiteBase"...
0x76f9  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x76fe  ldarg.0
0x76ff  ldloc.1
0x7700  ldloc.0
0x7701  ldftn    instance void <>c__DisplayClass35_0::<CollectSQMForDocumentManagement>b__0(object[] values)
0x7707  newobj   instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase/RecordProcessor::.ctor(object, native int)
0x770c  call     instance int32 [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase::ExecuteSqlCommandAndProcessRecords(class [System.Data]System.Data.IDbCommand, class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase/RecordProcessor)
0x7711  pop
0x7712  leave.s  loc_771E
0x7714  ldloc.1
0x7715  brfalse.s loc_771D
0x7717  ldloc.1
0x7718  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x771d  endfinally
0x771e  call     class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::NewCommand()
0x7723  stloc.2
0x7724  ldloc.2
0x7725  ldstr    aSelectCountFro_19// "select count(*) from SharePointSiteBase"
0x772a  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x772f  ldarg.0
0x7730  ldloc.2
0x7731  ldloc.0
0x7732  ldftn    instance void <>c__DisplayClass35_0::<CollectSQMForDocumentManagement>b__1(object[] values)
0x7738  newobj   instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase/RecordProcessor::.ctor(object, native int)
0x773d  call     instance int32 [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase::ExecuteSqlCommandAndProcessRecords(class [System.Data]System.Data.IDbCommand, class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase/RecordProcessor)
0x7742  pop
0x7743  leave.s  loc_774F
0x7745  ldloc.2
0x7746  brfalse.s loc_774E
0x7748  ldloc.2
0x7749  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x774e  endfinally
0x774f  call     class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::NewCommand()
0x7754  stloc.3
0x7755  ldloc.3
0x7756  ldstr    aSelectCountFro_20// "select count(*) from SharePointDocument"...
0x775b  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x7760  ldarg.0
0x7761  ldloc.3
0x7762  ldloc.0
0x7763  ldftn    instance void <>c__DisplayClass35_0::<CollectSQMForDocumentManagement>b__2(object[] values)
0x7769  newobj   instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase/RecordProcessor::.ctor(object, native int)
0x776e  call     instance int32 [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase::ExecuteSqlCommandAndProcessRecords(class [System.Data]System.Data.IDbCommand, class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase/RecordProcessor)
0x7773  pop
0x7774  leave.s  loc_7780
0x7776  ldloc.3
0x7777  brfalse.s loc_777F
0x7779  ldloc.3
0x777a  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x777f  endfinally
0x7780  call     class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::NewCommand()
0x7785  stloc.s  4
0x7787  ldloc.s  4
0x7789  ldstr    aSelectCountFro_21// "select count(*) from SharePointDocument"...
0x778e  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x7793  ldarg.0
0x7794  ldloc.s  4
0x7796  ldloc.0
0x7797  ldftn    instance void <>c__DisplayClass35_0::<CollectSQMForDocumentManagement>b__3(object[] values)
0x779d  newobj   instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase/RecordProcessor::.ctor(object, native int)
0x77a2  call     instance int32 [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase::ExecuteSqlCommandAndProcessRecords(class [System.Data]System.Data.IDbCommand, class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase/RecordProcessor)
0x77a7  pop
0x77a8  leave.s  loc_77B6
0x77aa  ldloc.s  4
0x77ac  brfalse.s loc_77B5
0x77ae  ldloc.s  4
0x77b0  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x77b5  endfinally
0x77b6  call     class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::NewCommand()
0x77bb  stloc.s  5
0x77bd  ldloc.s  5
0x77bf  ldstr    aSelectCountFro_22// "select count(*) from SharePointSiteBase"...
0x77c4  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x77c9  ldarg.0
0x77ca  ldloc.s  5
0x77cc  ldloc.0
0x77cd  ldftn    instance void <>c__DisplayClass35_0::<CollectSQMForDocumentManagement>b__4(object[] values)
0x77d3  newobj   instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase/RecordProcessor::.ctor(object, native int)
0x77d8  call     instance int32 [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase::ExecuteSqlCommandAndProcessRecords(class [System.Data]System.Data.IDbCommand, class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase/RecordProcessor)
0x77dd  pop
0x77de  leave.s  loc_77EC
0x77e0  ldloc.s  5
0x77e2  brfalse.s loc_77EB
0x77e4  ldloc.s  5
0x77e6  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x77eb  endfinally
0x77ec  ret
```
