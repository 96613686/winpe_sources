# Microsoft.Crm.Asynchronous.JobDataAccess::GetNextJobInAppLock

- ea: `0x2ae0`
- end: `0x2b2e`
- name: `Microsoft.Crm.Asynchronous.JobDataAccess::GetNextJobInAppLock`
- size: `78`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x2210`

## callees

- `0x2950`
- `0x2ae0`
- `0x2b30`

## pseudocode

```c

```

## disassembly

```asm
0x2ae0  ldarg.0
0x2ae1  ldc.i4.1
0x2ae2  call     instance class [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection Microsoft.Crm.Asynchronous.JobDataAccess::CreateConnection(valuetype [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.ConfigScope configScope)
0x2ae7  stloc.0
0x2ae8  ldloc.0
0x2ae9  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::Open()
0x2aee  ldloc.0
0x2aef  callvirt instance class [System.Data]System.Data.IDbTransaction [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::BeginTransaction()
0x2af4  stloc.1
0x2af5  ldstr    aAsyncGetnextjo// "Async_GetNextJob"
0x2afa  ldloc.0
0x2afb  ldloc.1
0x2afc  call     class [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.IConfigDBLock [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.ConfigDBLock::NewLock(string, class [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection, class [System.Data]System.Data.IDbTransaction)
0x2b01  stloc.2
0x2b02  ldarg.0
0x2b03  ldarg.1
0x2b04  ldarg.2
0x2b05  ldarg.3
0x2b06  call     instance class Microsoft.Crm.Asynchronous.AsyncJob[] Microsoft.Crm.Asynchronous.JobDataAccess::GetNextJob(class [mscorlib]System.Collections.Generic.IList`1<valuetype [mscorlib]System.Guid> orgsAvailableForMaintenance, valuetype [mscorlib]System.DateTime startCycleTime, int32 maxJobsToReturn)
0x2b0b  stloc.3
0x2b0c  leave.s  loc_2B2C
0x2b0e  ldloc.2
0x2b0f  brfalse.s loc_2B17
0x2b11  ldloc.2
0x2b12  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2b17  endfinally
0x2b18  ldloc.1
0x2b19  brfalse.s loc_2B21
0x2b1b  ldloc.1
0x2b1c  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2b21  endfinally
0x2b22  ldloc.0
0x2b23  brfalse.s loc_2B2B
0x2b25  ldloc.0
0x2b26  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2b2b  endfinally
0x2b2c  ldloc.3
0x2b2d  ret
```
