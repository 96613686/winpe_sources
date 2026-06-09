# Microsoft.Crm.Asynchronous.SqmDatabaseAccessor::CollectUseAsWindowsCredentials

- ea: `0x85b0`
- end: `0x8600`
- name: `Microsoft.Crm.Asynchronous.SqmDatabaseAccessor::CollectUseAsWindowsCredentials`
- size: `80`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x83e0`

## callees

- `0x85b0`
- `0xf2c0`

## string_xrefs

- `0x85c4`: `SELECT COUNT(1) FROM EmailServerProfile (NOLOCK) WHERE StateCode = 0 And IncomingAuthenticationProtocol = 2`

## pseudocode

```c

```

## disassembly

```asm
0x85b0  newobj   instance void <>c__DisplayClass54_0::.ctor()
0x85b5  stloc.0
0x85b6  ldloc.0
0x85b7  ldc.i4.0
0x85b8  stfld    int32 <>c__DisplayClass54_0::NumOfIncomingWinCredentialsEmailServerProfiles
0x85bd  call     class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::NewCommand()
0x85c2  stloc.1
0x85c3  ldloc.1
0x85c4  ldstr    aSelectCount1Fr_1// "SELECT COUNT(1) FROM EmailServerProfile"...
0x85c9  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x85ce  ldarg.0
0x85cf  ldloc.1
0x85d0  ldloc.0
0x85d1  ldftn    instance void <>c__DisplayClass54_0::<CollectUseAsWindowsCredentials>b__0(object[] values)
0x85d7  newobj   instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase/RecordProcessor::.ctor(object, native int)
0x85dc  call     instance int32 [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase::ExecuteSqlCommandAndProcessRecords(class [System.Data]System.Data.IDbCommand, class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase/RecordProcessor)
0x85e1  pop
0x85e2  leave.s  loc_85EE
0x85e4  ldloc.1
0x85e5  brfalse.s loc_85ED
0x85e7  ldloc.1
0x85e8  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x85ed  endfinally
0x85ee  ldarg.1
0x85ef  ldc.i4   0x248
0x85f4  ldloc.0
0x85f5  ldfld    int32 <>c__DisplayClass54_0::NumOfIncomingWinCredentialsEmailServerProfiles
0x85fa  callvirt instance void [Microsoft.Crm]Microsoft.Crm.ISqmSession::set_Item(valuetype [Microsoft.Crm]Microsoft.Crm.SqmDataPointId, int32)
0x85ff  ret
```
