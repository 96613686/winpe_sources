# Microsoft.Crm.Asynchronous.SqmDatabaseAccessor::CollectSyncInfo

- ea: `0x6970`
- end: `0x6a67`
- name: `Microsoft.Crm.Asynchronous.SqmDatabaseAccessor::CollectSyncInfo`
- size: `247`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x4c40`

## callees

- `0x6970`
- `0xe760`
- `0xe800`

## pseudocode

```c

```

## disassembly

```asm
0x6970  newobj   instance void <>c__DisplayClass18_1::.ctor()
0x6975  stloc.0
0x6976  ldloc.0
0x6977  ldarg.0
0x6978  stfld    class Microsoft.Crm.Asynchronous.SqmDatabaseAccessor <>c__DisplayClass18_1::<>4__this
0x697d  ldloc.0
0x697e  ldarg.2
0x697f  stfld    class [Microsoft.Crm]Microsoft.Crm.ISqmSession <>c__DisplayClass18_1::session
0x6984  call     class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::NewCommand()
0x6989  stloc.1
0x698a  newobj   instance void <>c__DisplayClass18_0::.ctor()
0x698f  stloc.2
0x6990  ldloc.2
0x6991  ldloc.0
0x6992  stfld    class <>c__DisplayClass18_1 <>c__DisplayClass18_0::CS$<>8__locals1
0x6997  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x699c  stloc.3
0x699d  ldloc.3
0x699e  ldstr    aSelectInsertob// "SELECT InsertObjectCount, EndTime FROM "...
0x69a3  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x69a8  pop
0x69a9  ldloc.3
0x69aa  ldstr    aUnion// " UNION"
0x69af  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x69b4  pop
0x69b5  ldloc.3
0x69b6  ldstr    aSelectTop1Inse// " SELECT TOP 1 InsertObjectCount, EndTim"...
0x69bb  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x69c0  pop
0x69c1  ldloc.1
0x69c2  ldloc.3
0x69c3  callvirt instance string [mscorlib]System.Object::ToString()
0x69c8  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x69cd  ldloc.1
0x69ce  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0x69d3  castclass [System.Data]System.Data.SqlClient.SqlParameterCollection
0x69d8  ldstr    aSubscriptionid// "@SubscriptionId"
0x69dd  ldarg.1
0x69de  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x69e3  pop
0x69e4  ldloc.2
0x69e5  ldsfld   valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::MaxValue
0x69ea  stfld    valuetype [mscorlib]System.DateTime <>c__DisplayClass18_0::previousEndTime
0x69ef  ldloc.2
0x69f0  ldc.i4.0
0x69f1  stfld    int32 <>c__DisplayClass18_0::previousInsertObjectCount
0x69f6  ldarg.0
0x69f7  ldloc.1
0x69f8  ldloc.2
0x69f9  ldftn    instance void <>c__DisplayClass18_0::<CollectSyncInfo>b__0(object[] values)
0x69ff  newobj   instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase/RecordProcessor::.ctor(object, native int)
0x6a04  call     instance int32 [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase::ExecuteSqlCommandAndProcessRecords(class [System.Data]System.Data.IDbCommand, class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase/RecordProcessor)
0x6a09  pop
0x6a0a  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x6a0f  stloc.s  4
0x6a11  ldloc.2
0x6a12  ldfld    valuetype [mscorlib]System.DateTime <>c__DisplayClass18_0::previousEndTime
0x6a17  ldloca.s 4
0x6a19  ldc.r8   -1.0
0x6a22  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::AddDays(float64)
0x6a27  call     bool [mscorlib]System.DateTime::op_GreaterThan(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x6a2c  brfalse.s loc_6A5A
0x6a2e  ldloc.2
0x6a2f  ldfld    class <>c__DisplayClass18_1 <>c__DisplayClass18_0::CS$<>8__locals1
0x6a34  ldfld    class [Microsoft.Crm]Microsoft.Crm.ISqmSession <>c__DisplayClass18_1::session
0x6a39  ldc.i4   0x8D
0x6a3e  ldc.i4.2
0x6a3f  newarr   [mscorlib]System.Int32
0x6a44  dup
0x6a45  ldc.i4.0
0x6a46  ldloc.2
0x6a47  ldfld    int32 <>c__DisplayClass18_0::previousInsertObjectCount
0x6a4c  stelem.i4
0x6a4d  dup
0x6a4e  ldc.i4.1
0x6a4f  ldc.i4   0x2710
0x6a54  stelem.i4
0x6a55  callvirt instance void [Microsoft.Crm]Microsoft.Crm.ISqmSession::AddToStream(valuetype [Microsoft.Crm]Microsoft.Crm.SqmDataPointId, int32[])
0x6a5a  leave.s  loc_6A66
0x6a5c  ldloc.1
0x6a5d  brfalse.s loc_6A65
0x6a5f  ldloc.1
0x6a60  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x6a65  endfinally
0x6a66  ret
```
