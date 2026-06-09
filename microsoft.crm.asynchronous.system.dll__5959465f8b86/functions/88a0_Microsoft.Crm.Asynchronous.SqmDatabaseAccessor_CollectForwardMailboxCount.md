# Microsoft.Crm.Asynchronous.SqmDatabaseAccessor::CollectForwardMailboxCount

- ea: `0x88a0`
- end: `0x88f0`
- name: `Microsoft.Crm.Asynchronous.SqmDatabaseAccessor::CollectForwardMailboxCount`
- size: `80`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x86c0`

## callees

- `0x88a0`
- `0xf560`

## pseudocode

```c

```

## disassembly

```asm
0x88a0  newobj   instance void <>c__DisplayClass59_0::.ctor()
0x88a5  stloc.0
0x88a6  ldloc.0
0x88a7  ldc.i4.0
0x88a8  stfld    int32 <>c__DisplayClass59_0::NumOfActiveForwardMailboxes
0x88ad  call     class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::NewCommand()
0x88b2  stloc.1
0x88b3  ldloc.1
0x88b4  ldstr    aSelectCount1Fr_3// "SELECT COUNT(1) FROM Mailbox WHERE IsFo"...
0x88b9  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x88be  ldarg.0
0x88bf  ldloc.1
0x88c0  ldloc.0
0x88c1  ldftn    instance void <>c__DisplayClass59_0::<CollectForwardMailboxCount>b__0(object[] values)
0x88c7  newobj   instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase/RecordProcessor::.ctor(object, native int)
0x88cc  call     instance int32 [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase::ExecuteSqlCommandAndProcessRecords(class [System.Data]System.Data.IDbCommand, class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase/RecordProcessor)
0x88d1  pop
0x88d2  leave.s  loc_88DE
0x88d4  ldloc.1
0x88d5  brfalse.s loc_88DD
0x88d7  ldloc.1
0x88d8  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x88dd  endfinally
0x88de  ldarg.1
0x88df  ldc.i4   0x254
0x88e4  ldloc.0
0x88e5  ldfld    int32 <>c__DisplayClass59_0::NumOfActiveForwardMailboxes
0x88ea  callvirt instance void [Microsoft.Crm]Microsoft.Crm.ISqmSession::set_Item(valuetype [Microsoft.Crm]Microsoft.Crm.SqmDataPointId, int32)
0x88ef  ret
```
