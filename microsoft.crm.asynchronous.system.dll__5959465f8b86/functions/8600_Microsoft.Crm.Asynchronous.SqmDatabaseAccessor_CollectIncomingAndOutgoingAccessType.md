# Microsoft.Crm.Asynchronous.SqmDatabaseAccessor::CollectIncomingAndOutgoingAccessType

- ea: `0x8600`
- end: `0x86b1`
- name: `Microsoft.Crm.Asynchronous.SqmDatabaseAccessor::CollectIncomingAndOutgoingAccessType`
- size: `177`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x83e0`

## callees

- `0x8600`
- `0xf2f0`

## string_xrefs

- `0x8622`: `SELECT COUNT(1) FROM EmailServerProfile (NOLOCK) WHERE StateCode = 0 AND ServerType = 0 AND IncomingUseImpersonation = 1`
- `0x8653`: `SELECT OutgoingUseImpersonation, OutgoingAutoGrantDelegateAccess, COUNT(1) FROM EmailServerProfile (NOLOCK) WHERE StateCode = 0 AND ServerType = 0 GROUP BY OutgoingUseImpersonation, OutgoingAutoGrantDelegateAccess`

## pseudocode

```c

```

## disassembly

```asm
0x8600  newobj   instance void <>c__DisplayClass55_0::.ctor()
0x8605  stloc.0
0x8606  ldloc.0
0x8607  ldc.i4.0
0x8608  stfld    int32 <>c__DisplayClass55_0::NumOfIncomingImpersonationTypeProfile
0x860d  ldloc.0
0x860e  ldc.i4.0
0x860f  stfld    int32 <>c__DisplayClass55_0::NumOfOutgoingAutoGrantDelegateAccessTypeProfile
0x8614  ldloc.0
0x8615  ldc.i4.0
0x8616  stfld    int32 <>c__DisplayClass55_0::NumOfOutgoingImpersonationTypeProfile
0x861b  call     class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::NewCommand()
0x8620  stloc.1
0x8621  ldloc.1
0x8622  ldstr    aSelectCount1Fr_2// "SELECT COUNT(1) FROM EmailServerProfile"...
0x8627  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x862c  ldarg.0
0x862d  ldloc.1
0x862e  ldloc.0
0x862f  ldftn    instance void <>c__DisplayClass55_0::<CollectIncomingAndOutgoingAccessType>b__0(object[] values)
0x8635  newobj   instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase/RecordProcessor::.ctor(object, native int)
0x863a  call     instance int32 [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase::ExecuteSqlCommandAndProcessRecords(class [System.Data]System.Data.IDbCommand, class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase/RecordProcessor)
0x863f  pop
0x8640  leave.s  loc_864C
0x8642  ldloc.1
0x8643  brfalse.s loc_864B
0x8645  ldloc.1
0x8646  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x864b  endfinally
0x864c  call     class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::NewCommand()
0x8651  stloc.2
0x8652  ldloc.2
0x8653  ldstr    aSelectOutgoing_0// "SELECT OutgoingUseImpersonation, Outgoi"...
0x8658  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x865d  ldarg.0
0x865e  ldloc.2
0x865f  ldloc.0
0x8660  ldftn    instance void <>c__DisplayClass55_0::<CollectIncomingAndOutgoingAccessType>b__1(object[] values)
0x8666  newobj   instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase/RecordProcessor::.ctor(object, native int)
0x866b  call     instance int32 [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase::ExecuteSqlCommandAndProcessRecords(class [System.Data]System.Data.IDbCommand, class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase/RecordProcessor)
0x8670  pop
0x8671  leave.s  loc_867D
0x8673  ldloc.2
0x8674  brfalse.s loc_867C
0x8676  ldloc.2
0x8677  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x867c  endfinally
0x867d  ldarg.1
0x867e  ldc.i4   0x24A
0x8683  ldloc.0
0x8684  ldfld    int32 <>c__DisplayClass55_0::NumOfIncomingImpersonationTypeProfile
0x8689  callvirt instance void [Microsoft.Crm]Microsoft.Crm.ISqmSession::set_Item(valuetype [Microsoft.Crm]Microsoft.Crm.SqmDataPointId, int32)
0x868e  ldarg.1
0x868f  ldc.i4   0x24C
0x8694  ldloc.0
0x8695  ldfld    int32 <>c__DisplayClass55_0::NumOfOutgoingAutoGrantDelegateAccessTypeProfile
0x869a  callvirt instance void [Microsoft.Crm]Microsoft.Crm.ISqmSession::set_Item(valuetype [Microsoft.Crm]Microsoft.Crm.SqmDataPointId, int32)
0x869f  ldarg.1
0x86a0  ldc.i4   0x248
0x86a5  ldloc.0
0x86a6  ldfld    int32 <>c__DisplayClass55_0::NumOfOutgoingImpersonationTypeProfile
0x86ab  callvirt instance void [Microsoft.Crm]Microsoft.Crm.ISqmSession::set_Item(valuetype [Microsoft.Crm]Microsoft.Crm.SqmDataPointId, int32)
0x86b0  ret
```
