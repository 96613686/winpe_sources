# Microsoft.Crm.Asynchronous.JobDataAccess::TryGetValidatedAsyncJob

- ea: `0x2f70`
- end: `0x305f`
- name: `Microsoft.Crm.Asynchronous.JobDataAccess::TryGetValidatedAsyncJob`
- size: `239`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x2dc0`

## callees

- `0x980`
- `0x2f70`
- `0x4320`
- `0x4340`

## string_xrefs

- `0x2f9f`: `d:\dbs\sh\dccm2\1101_190851\cmd\34\src\Core\ObjectModel\Async\AsyncService\JobDataAccess.cs`
- `0x2fc5`: `[DBUPDATES] Succesfully added DB Update job for org {0} on target server {1} to queue.`
- `0x2fea`: `[OrgDBUpdateThrottling] Incremented orgDBUpdatesRunning to {0} after adding org {1}.`

## pseudocode

```c

```

## disassembly

```asm
0x2f70  ldarg.1
0x2f71  ldarg.2
0x2f72  ldarg.3
0x2f73  ldarg.s  4
0x2f75  ldarg.s  5
0x2f77  ldarg.s  6
0x2f79  ldarg.s  7
0x2f7b  newobj   instance void Microsoft.Crm.Asynchronous.AsyncJob::.ctor(valuetype [mscorlib]System.Guid id, valuetype [mscorlib]System.Guid organizationId, string sqlServerName, int32 operationType, string recurrencePattern, valuetype [mscorlib]System.DateTime recurrenceStartTime, string jobParameters)
0x2f80  stloc.0
0x2f81  call     class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationSettingsProvider [Microsoft.Crm.Core]Microsoft.Crm.OrganizationSettingsProvider::get_Instance()
0x2f86  ldarg.2
0x2f87  ldc.i4.1
0x2f88  newarr   [mscorlib]System.String
0x2f8d  dup
0x2f8e  ldc.i4.0
0x2f8f  ldstr    aId// "Id"
0x2f94  stelem.ref
0x2f95  ldc.i4   0x301
0x2f9a  ldstr    aTrygetvalidate// "TryGetValidatedAsyncJob"
0x2f9f  ldstr    aDDbsShDccm2110// "d:\\dbs\\sh\\dccm2\\1101_190851\\cmd\\3"...
0x2fa4  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationSettingsProvider::GetOrganization(valuetype [mscorlib]System.Guid, string[], int32, string, string)
0x2fa9  brfalse  loc_303B
0x2fae  ldarg.s  4
0x2fb0  ldc.i4.s 0x2C
0x2fb2  bne.un.s loc_3017
0x2fb4  ldarg.0
0x2fb5  ldfld    class Microsoft.Crm.Asynchronous.JobManager Microsoft.Crm.Asynchronous.JobDataAccess::_jobManager
0x2fba  ldflda   int32 Microsoft.Crm.Asynchronous.JobManager::OrgDBUpdatesRunning
0x2fbf  call     int32 [mscorlib]System.Threading.Interlocked::Increment(int32&)
0x2fc4  pop
0x2fc5  ldstr    aDbupdatesSucce// "[DBUPDATES] Succesfully added DB Update"...
0x2fca  ldarg.2
0x2fcb  box      [mscorlib]System.Guid
0x2fd0  ldarg.3
0x2fd1  dup
0x2fd2  brtrue.s loc_2FDA
0x2fd4  pop
0x2fd5  ldstr    aUnknown// "UNKNOWN"
0x2fda  call     string [mscorlib]System.String::Format(string, object, object)
0x2fdf  ldc.i4.0
0x2fe0  newarr   [mscorlib]System.Object
0x2fe5  call     void Microsoft.Crm.Asynchronous.JobManager::LogDBUpdateScheduledTelemetry(string messageFormat, object[] args)
0x2fea  ldstr    aOrgdbupdatethr// "[OrgDBUpdateThrottling] Incremented org"...
0x2fef  ldarg.0
0x2ff0  ldfld    class Microsoft.Crm.Asynchronous.JobManager Microsoft.Crm.Asynchronous.JobDataAccess::_jobManager
0x2ff5  ldfld    int32 Microsoft.Crm.Asynchronous.JobManager::OrgDBUpdatesRunning
0x2ffa  box      [mscorlib]System.Int32
0x2fff  ldarg.2
0x3000  box      [mscorlib]System.Guid
0x3005  call     string [mscorlib]System.String::Format(string, object, object)
0x300a  ldc.i4.0
0x300b  newarr   [mscorlib]System.Object
0x3010  call     void Microsoft.Crm.Asynchronous.JobManager::LogDBUpdateThrottlingTelemetry(string messageFormat, object[] args)
0x3015  br.s     loc_3039
0x3017  ldstr    aJobprocessingP_3// "[JOBPROCESSING] Picked job {0} for org "...
0x301c  ldarg.s  4
0x301e  box      [mscorlib]System.Int32
0x3023  ldarg.2
0x3024  box      [mscorlib]System.Guid
0x3029  call     string [mscorlib]System.String::Format(string, object, object)
0x302e  ldc.i4.0
0x302f  newarr   [mscorlib]System.Object
0x3034  call     void Microsoft.Crm.Asynchronous.JobManager::LogDBUpdateScheduledTelemetry(string messageFormat, object[] args)
0x3039  ldloc.0
0x303a  ret
0x303b  ldstr    aJobprocessingF_1// "[JOBPROCESSING] Failed to process job {"...
0x3040  ldarg.s  4
0x3042  box      [mscorlib]System.Int32
0x3047  ldarg.2
0x3048  box      [mscorlib]System.Guid
0x304d  call     string [mscorlib]System.String::Format(string, object, object)
0x3052  ldc.i4.0
0x3053  newarr   [mscorlib]System.Object
0x3058  call     void Microsoft.Crm.Asynchronous.JobManager::LogDBUpdateScheduledTelemetry(string messageFormat, object[] args)
0x305d  ldnull
0x305e  ret
```
