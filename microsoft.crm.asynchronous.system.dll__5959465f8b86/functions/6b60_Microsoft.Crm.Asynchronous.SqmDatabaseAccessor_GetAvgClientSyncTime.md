# Microsoft.Crm.Asynchronous.SqmDatabaseAccessor::GetAvgClientSyncTime

- ea: `0x6b60`
- end: `0x6bc7`
- name: `Microsoft.Crm.Asynchronous.SqmDatabaseAccessor::GetAvgClientSyncTime`
- size: `103`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x4cf0`

## callees

- `0x6b60`
- `0xe880`

## pseudocode

```c

```

## disassembly

```asm
0x6b60  newobj   instance void <>c__DisplayClass25_0::.ctor()
0x6b65  stloc.0
0x6b66  ldloc.0
0x6b67  ldarg.0
0x6b68  stfld    class Microsoft.Crm.Asynchronous.SqmDatabaseAccessor <>c__DisplayClass25_0::<>4__this
0x6b6d  ldloc.0
0x6b6e  ldc.i4.0
0x6b6f  stfld    int32 <>c__DisplayClass25_0::result
0x6b74  call     class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::NewCommand()
0x6b79  stloc.1
0x6b7a  ldstr    aSelectAvgDated// "select AVG(datediff(ss, starttime,endti"...
0x6b7f  stloc.2
0x6b80  ldloc.1
0x6b81  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x6b86  ldloc.2
0x6b87  ldc.i4.1
0x6b88  newarr   [mscorlib]System.Object
0x6b8d  dup
0x6b8e  ldc.i4.0
0x6b8f  ldarg.1
0x6b90  box      [mscorlib]System.Int32
0x6b95  stelem.ref
0x6b96  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x6b9b  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x6ba0  ldarg.0
0x6ba1  ldloc.1
0x6ba2  ldloc.0
0x6ba3  ldftn    instance void <>c__DisplayClass25_0::<GetAvgClientSyncTime>b__0(object[] values)
0x6ba9  newobj   instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase/RecordProcessor::.ctor(object, native int)
0x6bae  call     instance int32 [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase::ExecuteSqlCommandAndProcessRecords(class [System.Data]System.Data.IDbCommand, class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase/RecordProcessor)
0x6bb3  pop
0x6bb4  leave.s  loc_6BC0
0x6bb6  ldloc.1
0x6bb7  brfalse.s loc_6BBF
0x6bb9  ldloc.1
0x6bba  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x6bbf  endfinally
0x6bc0  ldloc.0
0x6bc1  ldfld    int32 <>c__DisplayClass25_0::result
0x6bc6  ret
```
