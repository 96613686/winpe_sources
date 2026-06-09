# Microsoft.Crm.Asynchronous.SqmDatabaseAccessor::CollectPointsForFormMerge

- ea: `0x8a00`
- end: `0x8a50`
- name: `Microsoft.Crm.Asynchronous.SqmDatabaseAccessor::CollectPointsForFormMerge`
- size: `80`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x5410`

## callees

- `0x8a00`
- `0xf640`

## pseudocode

```c

```

## disassembly

```asm
0x8a00  newobj   instance void <>c__DisplayClass64_0::.ctor()
0x8a05  stloc.0
0x8a06  ldloc.0
0x8a07  ldc.i4.0
0x8a08  stfld    int32 <>c__DisplayClass64_0::NumOfMergedForms
0x8a0d  call     class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::NewCommand()
0x8a12  stloc.1
0x8a13  ldloc.1
0x8a14  ldstr    aSelectCount1Fr_4// "SELECT COUNT(1) FROM Systemform WHERE T"...
0x8a19  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x8a1e  ldarg.0
0x8a1f  ldloc.1
0x8a20  ldloc.0
0x8a21  ldftn    instance void <>c__DisplayClass64_0::<CollectPointsForFormMerge>b__0(object[] values)
0x8a27  newobj   instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase/RecordProcessor::.ctor(object, native int)
0x8a2c  call     instance int32 [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase::ExecuteSqlCommandAndProcessRecords(class [System.Data]System.Data.IDbCommand, class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase/RecordProcessor)
0x8a31  pop
0x8a32  leave.s  loc_8A3E
0x8a34  ldloc.1
0x8a35  brfalse.s loc_8A3D
0x8a37  ldloc.1
0x8a38  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x8a3d  endfinally
0x8a3e  ldarg.1
0x8a3f  ldc.i4   0x267
0x8a44  ldloc.0
0x8a45  ldfld    int32 <>c__DisplayClass64_0::NumOfMergedForms
0x8a4a  callvirt instance void [Microsoft.Crm]Microsoft.Crm.ISqmSession::set_Item(valuetype [Microsoft.Crm]Microsoft.Crm.SqmDataPointId, int32)
0x8a4f  ret
```
