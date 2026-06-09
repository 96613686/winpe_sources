# Microsoft.Crm.Asynchronous.SqmDatabaseAccessor::CollectMailboxPerProfile

- ea: `0x8800`
- end: `0x8899`
- name: `Microsoft.Crm.Asynchronous.SqmDatabaseAccessor::CollectMailboxPerProfile`
- size: `153`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x86c0`

## callees

- `0x8800`
- `0xf450`
- `0xf540`

## pseudocode

```c

```

## disassembly

```asm
0x8800  newobj   instance void <>c__DisplayClass58_1::.ctor()
0x8805  stloc.0
0x8806  ldloc.0
0x8807  ldarg.1
0x8808  stfld    class [Microsoft.Crm]Microsoft.Crm.ISqmSession <>c__DisplayClass58_1::session
0x880d  call     class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::NewCommand()
0x8812  stloc.1
0x8813  newobj   instance void <>c__DisplayClass58_0::.ctor()
0x8818  stloc.2
0x8819  ldloc.2
0x881a  ldloc.0
0x881b  stfld    class <>c__DisplayClass58_1 <>c__DisplayClass58_0::CS$<>8__locals1
0x8820  ldloc.2
0x8821  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x8826  stfld    valuetype [mscorlib]System.Guid <>c__DisplayClass58_0::previousProfileId
0x882b  ldloc.2
0x882c  ldc.i4.1
0x882d  stfld    bool <>c__DisplayClass58_0::started
0x8832  ldloc.2
0x8833  ldc.i4.0
0x8834  stfld    int32 <>c__DisplayClass58_0::userCount
0x8839  ldloc.2
0x883a  ldc.i4.0
0x883b  stfld    int32 <>c__DisplayClass58_0::queueCount
0x8840  ldloc.1
0x8841  ldstr    aSelectEmailser// "SELECT EmailServerProfile, RegardingObj"...
0x8846  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x884b  ldarg.0
0x884c  ldloc.1
0x884d  ldloc.2
0x884e  ldftn    instance void <>c__DisplayClass58_0::<CollectMailboxPerProfile>b__0(object[] values)
0x8854  newobj   instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase/RecordProcessor::.ctor(object, native int)
0x8859  call     instance int32 [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase::ExecuteSqlCommandAndProcessRecords(class [System.Data]System.Data.IDbCommand, class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase/RecordProcessor)
0x885e  pop
0x885f  ldloc.2
0x8860  ldfld    class <>c__DisplayClass58_1 <>c__DisplayClass58_0::CS$<>8__locals1
0x8865  ldfld    class [Microsoft.Crm]Microsoft.Crm.ISqmSession <>c__DisplayClass58_1::session
0x886a  ldc.i4   0x253
0x886f  ldc.i4.2
0x8870  newarr   [mscorlib]System.Int32
0x8875  dup
0x8876  ldc.i4.0
0x8877  ldloc.2
0x8878  ldfld    int32 <>c__DisplayClass58_0::userCount
0x887d  stelem.i4
0x887e  dup
0x887f  ldc.i4.1
0x8880  ldloc.2
0x8881  ldfld    int32 <>c__DisplayClass58_0::queueCount
0x8886  stelem.i4
0x8887  callvirt instance void [Microsoft.Crm]Microsoft.Crm.ISqmSession::AddToStream(valuetype [Microsoft.Crm]Microsoft.Crm.SqmDataPointId, int32[])
0x888c  leave.s  loc_8898
0x888e  ldloc.1
0x888f  brfalse.s loc_8897
0x8891  ldloc.1
0x8892  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x8897  endfinally
0x8898  ret
```
