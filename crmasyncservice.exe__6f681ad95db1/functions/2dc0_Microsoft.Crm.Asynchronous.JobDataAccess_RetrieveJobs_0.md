# Microsoft.Crm.Asynchronous.JobDataAccess::RetrieveJobs_0

- ea: `0x2dc0`
- end: `0x2f69`
- name: `Microsoft.Crm.Asynchronous.JobDataAccess::RetrieveJobs_0`
- size: `425`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x2d10`

## callees

- `0x23b0`
- `0x2dc0`
- `0x2f70`
- `0x33a0`
- `0x4340`
- `0x4a50`
- `0x4ae0`
- `0x4b30`

## pseudocode

```c

```

## disassembly

```asm
0x2dc0  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.AsyncJob>::.ctor()
0x2dc5  stloc.0
0x2dc6  ldnull
0x2dc7  stloc.1
0x2dc8  ldarg.2
0x2dc9  brfalse.s loc_2DE2
0x2dcb  ldarg.3
0x2dcc  ldarg.0
0x2dcd  ldfld    class Microsoft.Crm.Asynchronous.JobManager Microsoft.Crm.Asynchronous.JobDataAccess::_jobManager
0x2dd2  callvirt instance class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IJobConfiguration Microsoft.Crm.Asynchronous.JobManager::get_Configuration()
0x2dd7  callvirt instance int32 [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IJobConfiguration::get_OrgMaintenanceServerMaximumConcurrentJobs()
0x2ddc  newobj   instance void Microsoft.Crm.Asynchronous.MaintenanceJobTableState::.ctor(class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> currentJobsRunningOnServer, int32 maxItemsOnTargetServer)
0x2de1  stloc.1
0x2de2  ldc.i4.0
0x2de3  stloc.2
0x2de4  ldarg.1
0x2de5  callvirt instance class [System.Data]System.Data.IDataReader [System.Data]System.Data.IDbCommand::ExecuteReader()
0x2dea  stloc.3
0x2deb  br       loc_2F50
0x2df0  ldloc.2
0x2df1  ldc.i4.1
0x2df2  add
0x2df3  stloc.2
0x2df4  ldloc.3
0x2df5  ldstr    aOptype// "OpType"
0x2dfa  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x2dff  unbox.any [mscorlib]System.Int32
0x2e04  stloc.s  4
0x2e06  ldloc.3
0x2e07  ldstr    aOrganizationid// "OrganizationId"
0x2e0c  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x2e11  unbox.any [mscorlib]System.Guid
0x2e16  stloc.s  5
0x2e18  ldarg.0
0x2e19  ldloc.s  4
0x2e1b  ldloc.s  5
0x2e1d  call     instance bool Microsoft.Crm.Asynchronous.JobDataAccess::ShouldSkipProcessingJob(int32 operationType, valuetype [mscorlib]System.Guid orgId)
0x2e22  brtrue   loc_2F50
0x2e27  ldloc.3
0x2e28  ldstr    aId// "Id"
0x2e2d  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x2e32  unbox.any [mscorlib]System.Guid
0x2e37  stloc.s  6
0x2e39  ldloc.3
0x2e3a  ldstr    aRecurrencepatt_1// "RecurrencePattern"
0x2e3f  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x2e44  castclass [mscorlib]System.String
0x2e49  stloc.s  7
0x2e4b  ldloc.3
0x2e4c  ldstr    aRecurrencestar_1// "RecurrenceStartTime"
0x2e51  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x2e56  unbox.any [mscorlib]System.DateTime
0x2e5b  stloc.s  8
0x2e5d  ldloc.3
0x2e5e  ldstr    aTargetserver// "TargetServer"
0x2e63  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x2e68  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x2e6d  beq.s    loc_2E81
0x2e6f  ldloc.3
0x2e70  ldstr    aTargetserver// "TargetServer"
0x2e75  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x2e7a  castclass [mscorlib]System.String
0x2e7f  br.s     loc_2E82
0x2e81  ldnull
0x2e82  stloc.s  9
0x2e84  ldnull
0x2e85  stloc.s  0xA
0x2e87  ldarg.0
0x2e88  call     instance bool Microsoft.Crm.Asynchronous.JobDataAccess::ReadJobParameters()
0x2e8d  brfalse.s loc_2EB6
0x2e8f  ldloc.3
0x2e90  ldstr    aJobparameters// "JobParameters"
0x2e95  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x2e9a  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x2e9f  beq.s    loc_2EB3
0x2ea1  ldloc.3
0x2ea2  ldstr    aJobparameters// "JobParameters"
0x2ea7  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x2eac  castclass [mscorlib]System.String
0x2eb1  br.s     loc_2EB4
0x2eb3  ldnull
0x2eb4  stloc.s  0xA
0x2eb6  ldarg.2
0x2eb7  brfalse.s loc_2F22
0x2eb9  ldloc.3
0x2eba  ldstr    aCapacitytype// "CapacityType"
0x2ebf  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x2ec4  unbox.any Microsoft.Crm.Asynchronous.CapacityType
0x2ec9  stloc.s  0xB
0x2ecb  ldloc.1
0x2ecc  ldloc.s  5
0x2ece  ldloc.s  0xB
0x2ed0  ldloc.s  9
0x2ed2  callvirt instance bool Microsoft.Crm.Asynchronous.MaintenanceJobTableState::TryAdd(valuetype [mscorlib]System.Guid orgId, valuetype Microsoft.Crm.Asynchronous.CapacityType capacityType, string targetServer)
0x2ed7  brfalse.s loc_2EFD
0x2ed9  ldarg.0
0x2eda  ldloc.s  6
0x2edc  ldloc.s  5
0x2ede  ldloc.s  9
0x2ee0  ldloc.s  4
0x2ee2  ldloc.s  7
0x2ee4  ldloc.s  8
0x2ee6  ldloc.s  0xA
0x2ee8  call     instance class Microsoft.Crm.Asynchronous.AsyncJob Microsoft.Crm.Asynchronous.JobDataAccess::TryGetValidatedAsyncJob(valuetype [mscorlib]System.Guid jobId, valuetype [mscorlib]System.Guid orgId, string targetServer, int32 operationType, string recurrencePattern, valuetype [mscorlib]System.DateTime recurrenceStartTime, string jobParameters)
0x2eed  stloc.s  0xC
0x2eef  ldloc.s  0xC
0x2ef1  brfalse.s loc_2F44
0x2ef3  ldloc.0
0x2ef4  ldloc.s  0xC
0x2ef6  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.AsyncJob>::Add(var<u1>)
0x2efb  br.s     loc_2F44
0x2efd  ldstr    aJobprocessingF_0// "[JOBPROCESSING] Failed to process job {"...
0x2f02  ldloc.s  4
0x2f04  box      [mscorlib]System.Int32
0x2f09  ldloc.s  5
0x2f0b  box      [mscorlib]System.Guid
0x2f10  call     string [mscorlib]System.String::Format(string, object, object)
0x2f15  ldc.i4.0
0x2f16  newarr   [mscorlib]System.Object
0x2f1b  call     void Microsoft.Crm.Asynchronous.JobManager::LogDBUpdateScheduledTelemetry(string messageFormat, object[] args)
0x2f20  br.s     loc_2F44
0x2f22  ldarg.0
0x2f23  ldloc.s  6
0x2f25  ldloc.s  5
0x2f27  ldloc.s  9
0x2f29  ldloc.s  4
0x2f2b  ldloc.s  7
0x2f2d  ldloc.s  8
0x2f2f  ldloc.s  0xA
0x2f31  call     instance class Microsoft.Crm.Asynchronous.AsyncJob Microsoft.Crm.Asynchronous.JobDataAccess::TryGetValidatedAsyncJob(valuetype [mscorlib]System.Guid jobId, valuetype [mscorlib]System.Guid orgId, string targetServer, int32 operationType, string recurrencePattern, valuetype [mscorlib]System.DateTime recurrenceStartTime, string jobParameters)
0x2f36  stloc.s  0xD
0x2f38  ldloc.s  0xD
0x2f3a  brfalse.s loc_2F44
0x2f3c  ldloc.0
0x2f3d  ldloc.s  0xD
0x2f3f  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.AsyncJob>::Add(var<u1>)
0x2f44  ldloc.0
0x2f45  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.AsyncJob>::get_Count()
0x2f4a  ldarg.s  4
0x2f4c  bne.un.s loc_2F50
0x2f4e  leave.s  loc_2F67
0x2f50  ldloc.3
0x2f51  callvirt instance bool [System.Data]System.Data.IDataReader::Read()
0x2f56  brtrue   loc_2DF0
0x2f5b  leave.s  loc_2F67
0x2f5d  ldloc.3
0x2f5e  brfalse.s loc_2F66
0x2f60  ldloc.3
0x2f61  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2f66  endfinally
0x2f67  ldloc.0
0x2f68  ret
```
