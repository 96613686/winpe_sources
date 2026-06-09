# Microsoft.Crm.Asynchronous.JobDataAccess::SelectJobs

- ea: `0x2210`
- end: `0x2295`
- name: `Microsoft.Crm.Asynchronous.JobDataAccess::SelectJobs`
- size: `133`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x2210`
- `0x2ae0`
- `0x3e10`
- `0x4a10`

## pseudocode

```c

```

## disassembly

```asm
0x2210  ldnull
0x2211  stloc.0
0x2212  ldarg.0
0x2213  ldfld    class Microsoft.Crm.Asynchronous.JobManager Microsoft.Crm.Asynchronous.JobDataAccess::_jobManager
0x2218  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.JobManager::get_ScaleGroupId()
0x221d  call     class [mscorlib]System.Collections.Generic.IList`1<valuetype [mscorlib]System.Guid> Microsoft.Crm.Asynchronous.JobDataAccessUtility::GetOrganizationsAvailableForMaintenance(valuetype [mscorlib]System.Guid scaleGroupId)
0x2222  stloc.1
0x2223  ldarg.0
0x2224  ldloc.1
0x2225  ldarg.1
0x2226  ldarg.2
0x2227  call     instance class Microsoft.Crm.Asynchronous.AsyncJob[] Microsoft.Crm.Asynchronous.JobDataAccess::GetNextJobInAppLock(class [mscorlib]System.Collections.Generic.IList`1<valuetype [mscorlib]System.Guid> orgsAvailableForMaintenance, valuetype [mscorlib]System.DateTime startCycleTime, int32 maxJobsToReturn)
0x222c  stloc.0
0x222d  leave.s  loc_2293
0x222f  stloc.2
0x2230  ldarg.0
0x2231  ldfld    class Microsoft.Crm.Asynchronous.JobManager Microsoft.Crm.Asynchronous.JobDataAccess::_jobManager
0x2236  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ICrmEventLog [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncManagerBase::get_EventLog()
0x223b  ldc.i4.1
0x223c  ldc.i4   0xC000440A
0x2241  conv.u8
0x2242  ldc.i4.2
0x2243  newarr   [mscorlib]System.Object
0x2248  dup
0x2249  ldc.i4.0
0x224a  ldarg.0
0x224b  ldfld    class Microsoft.Crm.Asynchronous.JobManager Microsoft.Crm.Asynchronous.JobDataAccess::_jobManager
0x2250  callvirt instance string [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncManagerBase::get_InstanceName()
0x2255  stelem.ref
0x2256  dup
0x2257  ldc.i4.1
0x2258  ldloc.2
0x2259  stelem.ref
0x225a  call     void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventLogHelper::LogEvent(class [Microsoft.Crm.Core]Microsoft.Crm.ICrmEventLog, valuetype [System]System.Diagnostics.EventLogEntryType, int64, object[])
0x225f  leave.s  loc_2293
0x2261  stloc.3
0x2262  ldarg.0
0x2263  ldfld    class Microsoft.Crm.Asynchronous.JobManager Microsoft.Crm.Asynchronous.JobDataAccess::_jobManager
0x2268  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ICrmEventLog [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncManagerBase::get_EventLog()
0x226d  ldc.i4.1
0x226e  ldc.i4   0xC000440A
0x2273  conv.u8
0x2274  ldc.i4.2
0x2275  newarr   [mscorlib]System.Object
0x227a  dup
0x227b  ldc.i4.0
0x227c  ldarg.0
0x227d  ldfld    class Microsoft.Crm.Asynchronous.JobManager Microsoft.Crm.Asynchronous.JobDataAccess::_jobManager
0x2282  callvirt instance string [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncManagerBase::get_InstanceName()
0x2287  stelem.ref
0x2288  dup
0x2289  ldc.i4.1
0x228a  ldloc.3
0x228b  stelem.ref
0x228c  call     void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventLogHelper::LogEvent(class [Microsoft.Crm.Core]Microsoft.Crm.ICrmEventLog, valuetype [System]System.Diagnostics.EventLogEntryType, int64, object[])
0x2291  leave.s  loc_2293
0x2293  ldloc.0
0x2294  ret
```
