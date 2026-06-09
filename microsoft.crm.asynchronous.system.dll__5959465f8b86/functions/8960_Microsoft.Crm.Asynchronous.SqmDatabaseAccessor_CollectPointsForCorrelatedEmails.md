# Microsoft.Crm.Asynchronous.SqmDatabaseAccessor::CollectPointsForCorrelatedEmails

- ea: `0x8960`
- end: `0x89f8`
- name: `Microsoft.Crm.Asynchronous.SqmDatabaseAccessor::CollectPointsForCorrelatedEmails`
- size: `152`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x88f0`

## callees

- `0x8960`
- `0xf5a0`

## string_xrefs

- `0x8989`: `SELECT COUNT(1), CorrelationMethod FROM Email (NOLOCK) WHERE DirectionCode = 0 AND StateCode = 1 AND StatusCode = 4 AND  CreatedOn >= DATEADD(DAY, -1, GETUTCDATE()) GROUP BY CorrelationMethod`

## pseudocode

```c

```

## disassembly

```asm
0x8960  newobj   instance void <>c__DisplayClass63_0::.ctor()
0x8965  stloc.0
0x8966  ldloc.0
0x8967  ldc.i4.0
0x8968  stfld    int32 <>c__DisplayClass63_0::CorrelationMethodIRTCount
0x896d  ldloc.0
0x896e  ldc.i4.0
0x896f  stfld    int32 <>c__DisplayClass63_0::CorrelationMethodCICount
0x8974  ldloc.0
0x8975  ldc.i4.0
0x8976  stfld    int32 <>c__DisplayClass63_0::CorrelationMethodTTCount
0x897b  ldloc.0
0x897c  ldc.i4.0
0x897d  stfld    int32 <>c__DisplayClass63_0::CorrelationMethodSMCount
0x8982  call     class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::NewCommand()
0x8987  stloc.1
0x8988  ldloc.1
0x8989  ldstr    aSelectCount1Co// "SELECT COUNT(1), CorrelationMethod FROM"...
0x898e  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x8993  ldarg.0
0x8994  ldloc.1
0x8995  ldloc.0
0x8996  ldftn    instance void <>c__DisplayClass63_0::<CollectPointsForCorrelatedEmails>b__0(object[] values)
0x899c  newobj   instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase/RecordProcessor::.ctor(object, native int)
0x89a1  call     instance int32 [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase::ExecuteSqlCommandAndProcessRecords(class [System.Data]System.Data.IDbCommand, class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase/RecordProcessor)
0x89a6  pop
0x89a7  leave.s  loc_89B3
0x89a9  ldloc.1
0x89aa  brfalse.s loc_89B2
0x89ac  ldloc.1
0x89ad  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x89b2  endfinally
0x89b3  ldarg.1
0x89b4  ldc.i4   0x256
0x89b9  ldloc.0
0x89ba  ldfld    int32 <>c__DisplayClass63_0::CorrelationMethodIRTCount
0x89bf  callvirt instance void [Microsoft.Crm]Microsoft.Crm.ISqmSession::set_Item(valuetype [Microsoft.Crm]Microsoft.Crm.SqmDataPointId, int32)
0x89c4  ldarg.1
0x89c5  ldc.i4   0x257
0x89ca  ldloc.0
0x89cb  ldfld    int32 <>c__DisplayClass63_0::CorrelationMethodCICount
0x89d0  callvirt instance void [Microsoft.Crm]Microsoft.Crm.ISqmSession::set_Item(valuetype [Microsoft.Crm]Microsoft.Crm.SqmDataPointId, int32)
0x89d5  ldarg.1
0x89d6  ldc.i4   0x258
0x89db  ldloc.0
0x89dc  ldfld    int32 <>c__DisplayClass63_0::CorrelationMethodTTCount
0x89e1  callvirt instance void [Microsoft.Crm]Microsoft.Crm.ISqmSession::set_Item(valuetype [Microsoft.Crm]Microsoft.Crm.SqmDataPointId, int32)
0x89e6  ldarg.1
0x89e7  ldc.i4   0x259
0x89ec  ldloc.0
0x89ed  ldfld    int32 <>c__DisplayClass63_0::CorrelationMethodSMCount
0x89f2  callvirt instance void [Microsoft.Crm]Microsoft.Crm.ISqmSession::set_Item(valuetype [Microsoft.Crm]Microsoft.Crm.SqmDataPointId, int32)
0x89f7  ret
```
