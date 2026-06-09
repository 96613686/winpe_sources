# Microsoft.Crm.Asynchronous.SqmDatabaseAccessor::CollectOutgoingConnectionType

- ea: `0x8510`
- end: `0x85a8`
- name: `Microsoft.Crm.Asynchronous.SqmDatabaseAccessor::CollectOutgoingConnectionType`
- size: `152`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x83e0`

## callees

- `0x8510`
- `0xf230`

## pseudocode

```c

```

## disassembly

```asm
0x8510  newobj   instance void <>c__DisplayClass53_0::.ctor()
0x8515  stloc.0
0x8516  ldloc.0
0x8517  ldc.i4.0
0x8518  stfld    int32 <>c__DisplayClass53_0::NumOfOutgoingUserSpecifiedEmailServerProfiles
0x851d  ldloc.0
0x851e  ldc.i4.0
0x851f  stfld    int32 <>c__DisplayClass53_0::NumOfOutgoingOtherEmailServerProfiles
0x8524  ldloc.0
0x8525  ldc.i4.0
0x8526  stfld    int32 <>c__DisplayClass53_0::NumOfOutgoingWinIntegratedEmailServerProfiles
0x852b  ldloc.0
0x852c  ldc.i4.0
0x852d  stfld    int32 <>c__DisplayClass53_0::NumOfOutgoingAnonEmailServerProfiles
0x8532  call     class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::NewCommand()
0x8537  stloc.1
0x8538  ldloc.1
0x8539  ldstr    aSelectOutgoing// "SELECT OutgoingCredentialRetrieval, COU"...
0x853e  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x8543  ldarg.0
0x8544  ldloc.1
0x8545  ldloc.0
0x8546  ldftn    instance void <>c__DisplayClass53_0::<CollectOutgoingConnectionType>b__0(object[] values)
0x854c  newobj   instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase/RecordProcessor::.ctor(object, native int)
0x8551  call     instance int32 [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase::ExecuteSqlCommandAndProcessRecords(class [System.Data]System.Data.IDbCommand, class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase/RecordProcessor)
0x8556  pop
0x8557  leave.s  loc_8563
0x8559  ldloc.1
0x855a  brfalse.s loc_8562
0x855c  ldloc.1
0x855d  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x8562  endfinally
0x8563  ldarg.1
0x8564  ldc.i4   0x247
0x8569  ldloc.0
0x856a  ldfld    int32 <>c__DisplayClass53_0::NumOfOutgoingUserSpecifiedEmailServerProfiles
0x856f  callvirt instance void [Microsoft.Crm]Microsoft.Crm.ISqmSession::set_Item(valuetype [Microsoft.Crm]Microsoft.Crm.SqmDataPointId, int32)
0x8574  ldarg.1
0x8575  ldc.i4   0x245
0x857a  ldloc.0
0x857b  ldfld    int32 <>c__DisplayClass53_0::NumOfOutgoingOtherEmailServerProfiles
0x8580  callvirt instance void [Microsoft.Crm]Microsoft.Crm.ISqmSession::set_Item(valuetype [Microsoft.Crm]Microsoft.Crm.SqmDataPointId, int32)
0x8585  ldarg.1
0x8586  ldc.i4   0x246
0x858b  ldloc.0
0x858c  ldfld    int32 <>c__DisplayClass53_0::NumOfOutgoingWinIntegratedEmailServerProfiles
0x8591  callvirt instance void [Microsoft.Crm]Microsoft.Crm.ISqmSession::set_Item(valuetype [Microsoft.Crm]Microsoft.Crm.SqmDataPointId, int32)
0x8596  ldarg.1
0x8597  ldc.i4   0x244
0x859c  ldloc.0
0x859d  ldfld    int32 <>c__DisplayClass53_0::NumOfOutgoingAnonEmailServerProfiles
0x85a2  callvirt instance void [Microsoft.Crm]Microsoft.Crm.ISqmSession::set_Item(valuetype [Microsoft.Crm]Microsoft.Crm.SqmDataPointId, int32)
0x85a7  ret
```
