# Microsoft.Crm.Asynchronous.SqmDatabaseAccessor::CollectEmailServerTypeAndActiveProfile

- ea: `0x8410`
- end: `0x8490`
- name: `Microsoft.Crm.Asynchronous.SqmDatabaseAccessor::CollectEmailServerTypeAndActiveProfile`
- size: `128`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x83e0`

## callees

- `0x8410`
- `0xf150`

## pseudocode

```c

```

## disassembly

```asm
0x8410  newobj   instance void <>c__DisplayClass51_0::.ctor()
0x8415  stloc.0
0x8416  ldloc.0
0x8417  ldc.i4.0
0x8418  stfld    int32 <>c__DisplayClass51_0::totalRecordsProcessed
0x841d  ldloc.0
0x841e  ldc.i4.0
0x841f  stfld    int32 <>c__DisplayClass51_0::NumOfExchangeEmailServerProfiles
0x8424  ldloc.0
0x8425  ldc.i4.0
0x8426  stfld    int32 <>c__DisplayClass51_0::NumOfOtherEmailServerProfiles
0x842b  call     class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::NewCommand()
0x8430  stloc.1
0x8431  ldloc.1
0x8432  ldstr    aSelectServerty// "SELECT ServerType, COUNT(1) FROM EmailS"...
0x8437  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x843c  ldarg.0
0x843d  ldloc.1
0x843e  ldloc.0
0x843f  ldftn    instance void <>c__DisplayClass51_0::<CollectEmailServerTypeAndActiveProfile>b__0(object[] values)
0x8445  newobj   instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase/RecordProcessor::.ctor(object, native int)
0x844a  call     instance int32 [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase::ExecuteSqlCommandAndProcessRecords(class [System.Data]System.Data.IDbCommand, class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase/RecordProcessor)
0x844f  pop
0x8450  leave.s  loc_845C
0x8452  ldloc.1
0x8453  brfalse.s loc_845B
0x8455  ldloc.1
0x8456  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x845b  endfinally
0x845c  ldarg.1
0x845d  ldc.i4   0x240
0x8462  ldloc.0
0x8463  ldfld    int32 <>c__DisplayClass51_0::totalRecordsProcessed
0x8468  callvirt instance void [Microsoft.Crm]Microsoft.Crm.ISqmSession::set_Item(valuetype [Microsoft.Crm]Microsoft.Crm.SqmDataPointId, int32)
0x846d  ldarg.1
0x846e  ldc.i4   0x23E
0x8473  ldloc.0
0x8474  ldfld    int32 <>c__DisplayClass51_0::NumOfExchangeEmailServerProfiles
0x8479  callvirt instance void [Microsoft.Crm]Microsoft.Crm.ISqmSession::set_Item(valuetype [Microsoft.Crm]Microsoft.Crm.SqmDataPointId, int32)
0x847e  ldarg.1
0x847f  ldc.i4   0x23F
0x8484  ldloc.0
0x8485  ldfld    int32 <>c__DisplayClass51_0::NumOfOtherEmailServerProfiles
0x848a  callvirt instance void [Microsoft.Crm]Microsoft.Crm.ISqmSession::set_Item(valuetype [Microsoft.Crm]Microsoft.Crm.SqmDataPointId, int32)
0x848f  ret
```
