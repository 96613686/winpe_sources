# Microsoft.Crm.Asynchronous.SqmDatabaseAccessor::CollectIncomingConnectionType

- ea: `0x8490`
- end: `0x8510`
- name: `Microsoft.Crm.Asynchronous.SqmDatabaseAccessor::CollectIncomingConnectionType`
- size: `128`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x83e0`

## callees

- `0x8490`
- `0xf1c0`

## string_xrefs

- `0x84b2`: `SELECT IncomingCredentialRetrieval, COUNT(1) FROM EmailServerProfile (NOLOCK) WHERE StateCode = 0 GROUP BY IncomingCredentialRetrieval`

## pseudocode

```c

```

## disassembly

```asm
0x8490  newobj   instance void <>c__DisplayClass52_0::.ctor()
0x8495  stloc.0
0x8496  ldloc.0
0x8497  ldc.i4.0
0x8498  stfld    int32 <>c__DisplayClass52_0::NumOfIncomingUserSpecifiedEmailServerProfiles
0x849d  ldloc.0
0x849e  ldc.i4.0
0x849f  stfld    int32 <>c__DisplayClass52_0::NumOfIncomingOtherEmailServerProfiles
0x84a4  ldloc.0
0x84a5  ldc.i4.0
0x84a6  stfld    int32 <>c__DisplayClass52_0::NumOfIncomingWinIntegratedEmailServerProfiles
0x84ab  call     class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::NewCommand()
0x84b0  stloc.1
0x84b1  ldloc.1
0x84b2  ldstr    aSelectIncoming// "SELECT IncomingCredentialRetrieval, COU"...
0x84b7  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x84bc  ldarg.0
0x84bd  ldloc.1
0x84be  ldloc.0
0x84bf  ldftn    instance void <>c__DisplayClass52_0::<CollectIncomingConnectionType>b__0(object[] values)
0x84c5  newobj   instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase/RecordProcessor::.ctor(object, native int)
0x84ca  call     instance int32 [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase::ExecuteSqlCommandAndProcessRecords(class [System.Data]System.Data.IDbCommand, class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase/RecordProcessor)
0x84cf  pop
0x84d0  leave.s  loc_84DC
0x84d2  ldloc.1
0x84d3  brfalse.s loc_84DB
0x84d5  ldloc.1
0x84d6  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x84db  endfinally
0x84dc  ldarg.1
0x84dd  ldc.i4   0x243
0x84e2  ldloc.0
0x84e3  ldfld    int32 <>c__DisplayClass52_0::NumOfIncomingUserSpecifiedEmailServerProfiles
0x84e8  callvirt instance void [Microsoft.Crm]Microsoft.Crm.ISqmSession::set_Item(valuetype [Microsoft.Crm]Microsoft.Crm.SqmDataPointId, int32)
0x84ed  ldarg.1
0x84ee  ldc.i4   0x241
0x84f3  ldloc.0
0x84f4  ldfld    int32 <>c__DisplayClass52_0::NumOfIncomingOtherEmailServerProfiles
0x84f9  callvirt instance void [Microsoft.Crm]Microsoft.Crm.ISqmSession::set_Item(valuetype [Microsoft.Crm]Microsoft.Crm.SqmDataPointId, int32)
0x84fe  ldarg.1
0x84ff  ldc.i4   0x242
0x8504  ldloc.0
0x8505  ldfld    int32 <>c__DisplayClass52_0::NumOfIncomingWinIntegratedEmailServerProfiles
0x850a  callvirt instance void [Microsoft.Crm]Microsoft.Crm.ISqmSession::set_Item(valuetype [Microsoft.Crm]Microsoft.Crm.SqmDataPointId, int32)
0x850f  ret
```
