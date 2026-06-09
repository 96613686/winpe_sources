# Microsoft.Crm.Asynchronous.SqmDatabaseAccessor::GetSubscriptionIds

- ea: `0x6920`
- end: `0x6970`
- name: `Microsoft.Crm.Asynchronous.SqmDatabaseAccessor::GetSubscriptionIds`
- size: `80`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x4c40`

## callees

- `0x6920`
- `0xe720`

## pseudocode

```c

```

## disassembly

```asm
0x6920  newobj   instance void <>c__DisplayClass17_0::.ctor()
0x6925  stloc.0
0x6926  ldloc.0
0x6927  ldarg.0
0x6928  stfld    class Microsoft.Crm.Asynchronous.SqmDatabaseAccessor <>c__DisplayClass17_0::<>4__this
0x692d  ldloc.0
0x692e  newobj   instance void [mscorlib]System.Collections.ArrayList::.ctor()
0x6933  stfld    class [mscorlib]System.Collections.ArrayList <>c__DisplayClass17_0::result
0x6938  call     class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::NewCommand()
0x693d  stloc.1
0x693e  ldloc.1
0x693f  ldstr    aSelectDistinct// "SELECT DISTINCT CONVERT(varchar(64), Su"...
0x6944  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x6949  ldarg.0
0x694a  ldloc.1
0x694b  ldloc.0
0x694c  ldftn    instance void <>c__DisplayClass17_0::<GetSubscriptionIds>b__0(object[] values)
0x6952  newobj   instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase/RecordProcessor::.ctor(object, native int)
0x6957  call     instance int32 [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase::ExecuteSqlCommandAndProcessRecords(class [System.Data]System.Data.IDbCommand, class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase/RecordProcessor)
0x695c  pop
0x695d  leave.s  loc_6969
0x695f  ldloc.1
0x6960  brfalse.s loc_6968
0x6962  ldloc.1
0x6963  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x6968  endfinally
0x6969  ldloc.0
0x696a  ldfld    class [mscorlib]System.Collections.ArrayList <>c__DisplayClass17_0::result
0x696f  ret
```
