# Microsoft.Crm.CrmLive.Provisioning.JitUserProcessing::TryCreateUser

- ea: `0xd8a0`
- end: `0xda85`
- name: `Microsoft.Crm.CrmLive.Provisioning.JitUserProcessing::TryCreateUser`
- size: `485`
- prototype: ``
- caller_count: `0`
- callee_count: `12`
- tags: `service_task, broker_com_uri`

## callees

- `0xd8a0`
- `0xdac0`
- `0xdb00`
- `0xdb80`
- `0x2bb70`
- `0x2bb90`
- `0x2bbb0`
- `0x2e7c0`
- `0x2e7d0`
- `0x2e810`
- `0x2e850`
- `0x2e890`

## string_xrefs

- `0xd8ac`: `directoryObjectId`
- `0xd9b0`: `TaskStatus: {0}, Details: {1}, Exception: {2}, TaskLog: {3}`
- `0xda74`: `ProvisioningCache`

## pseudocode

```c

```

## disassembly

```asm
0xd8a0  ldarg.1
0xd8a1  ldstr    aOrganizationid// "organizationId"
0xd8a6  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfGuidEmpty(valuetype [mscorlib]System.Guid, string)
0xd8ab  ldarg.2
0xd8ac  ldstr    aDirectoryobjec_1// "directoryObjectId"
0xd8b1  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfGuidEmpty(valuetype [mscorlib]System.Guid, string)
0xd8b6  ldarg.3
0xd8b7  ldstr    aPuid// "puid"
0xd8bc  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string, string)
0xd8c1  ldarg.0
0xd8c2  ldarg.1
0xd8c3  ldarg.2
0xd8c4  call     instance int32 Microsoft.Crm.CrmLive.Provisioning.JitUserProcessing::GetJitRequestCounterForUser(valuetype [mscorlib]System.Guid organizationId, valuetype [mscorlib]System.Guid objectId)
0xd8c9  stloc.0
0xd8ca  ldloc.0
0xd8cb  ldarg.0
0xd8cc  ldfld    int32 Microsoft.Crm.CrmLive.Provisioning.JitUserProcessing::_maximumNumberOfJitRequestAllowedPerHour
0xd8d1  bgt      loc_DA6D
0xd8d6  ldarg.2
0xd8d7  ldc.i4.0
0xd8d8  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0xd8dd  ldnull
0xd8de  ldsfld   string [mscorlib]System.String::Empty
0xd8e3  ldarg.3
0xd8e4  newobj   instance void [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.DirectoryObjectUser::.ctor(valuetype [mscorlib]System.Guid, bool, valuetype [mscorlib]System.Guid, string, string, string)
0xd8e9  stloc.1
0xd8ea  newobj   instance void [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.UserProvisioningBatchInfo::.ctor()
0xd8ef  stloc.2
0xd8f0  ldloc.2
0xd8f1  ldc.i4.1
0xd8f2  newarr   [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.DirectoryObjectUser
0xd8f7  dup
0xd8f8  ldc.i4.0
0xd8f9  ldloc.1
0xd8fa  stelem.ref
0xd8fb  callvirt instance void [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.UserProvisioningBatchInfo::set_Users(class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.DirectoryObjectUser[])
0xd900  ldloc.2
0xd901  ldc.i4.0
0xd902  callvirt instance void [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.UserProvisioningBatchInfo::set_IgnoreLicenseChecks(bool)
0xd907  newobj   instance void [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.QueueItem::.ctor()
0xd90c  dup
0xd90d  call     valuetype [mscorlib]System.Guid [mscorlib]System.Guid::NewGuid()
0xd912  callvirt instance void [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemBase::set_QueueItemId(valuetype [mscorlib]System.Guid)
0xd917  dup
0xd918  ldc.i4.s 0x40
0xd91a  callvirt instance void [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemBase::set_ItemType(int32)
0xd91f  dup
0xd920  ldarg.1
0xd921  callvirt instance void [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemBase::set_OrganizationId(valuetype [mscorlib]System.Guid)
0xd926  dup
0xd927  ldloc.2
0xd928  call     T0x2B00004E
0xd92d  callvirt instance void [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemBase::set_ItemData(string)
0xd932  stloc.3
0xd933  call     class [System]System.Diagnostics.Stopwatch [System]System.Diagnostics.Stopwatch::StartNew()
0xd938  stloc.s  4
0xd93a  ldarg.0
0xd93b  ldloc.3
0xd93c  call     instance class Microsoft.Crm.CrmLive.Provisioning.JitUserExecutionResult Microsoft.Crm.CrmLive.Provisioning.JitUserProcessing::CreateUser(class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.QueueItem queueItem)
0xd941  stloc.s  5
0xd943  ldloc.s  4
0xd945  callvirt instance void [System]System.Diagnostics.Stopwatch::Stop()
0xd94a  ldloc.s  5
0xd94c  callvirt instance valuetype Microsoft.Crm.CrmLive.Provisioning.SyncUserOutcome Microsoft.Crm.CrmLive.Provisioning.JitUserExecutionResult::get_IsUserCreated()
0xd951  ldc.i4.2
0xd952  bne.un.s loc_D97D
0xd954  call     class Microsoft.Crm.CrmLive.Provisioning.JitUserProcessingEventSource Microsoft.Crm.CrmLive.Provisioning.JitUserProcessingEventSource::get_Instance()
0xd959  ldarg.1
0xd95a  ldarg.2
0xd95b  ldloc.s  4
0xd95d  callvirt instance int64 [System]System.Diagnostics.Stopwatch::get_ElapsedMilliseconds()
0xd962  conv.r8
0xd963  callvirt instance void Microsoft.Crm.CrmLive.Provisioning.JitUserProcessingEventSource::JitUserProvisioningSkipped(valuetype [mscorlib]System.Guid orgId, valuetype [mscorlib]System.Guid directoryObjectId, float64 timeTaken)
0xd968  ldarg.0
0xd969  ldarg.1
0xd96a  ldarg.2
0xd96b  ldloc.0
0xd96c  ldc.i4.1
0xd96d  add
0xd96e  dup
0xd96f  stloc.0
0xd970  call     instance void Microsoft.Crm.CrmLive.Provisioning.JitUserProcessing::SetJitRequestCounterForUser(valuetype [mscorlib]System.Guid organizationId, valuetype [mscorlib]System.Guid objectId, int32 numberOfJitRequests)
0xd975  ldc.i4.0
0xd976  stloc.s  7
0xd978  leave    loc_DA82
0xd97d  ldloc.s  5
0xd97f  callvirt instance class [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Scheduling.TaskResult Microsoft.Crm.CrmLive.Provisioning.JitUserExecutionResult::get_Result()
0xd984  stloc.s  6
0xd986  ldloc.s  6
0xd988  brfalse  loc_DA35
0xd98d  ldloc.s  6
0xd98f  callvirt instance class [mscorlib]System.Exception [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Scheduling.TaskResult::get_Exception()
0xd994  brtrue.s loc_D99D
0xd996  ldsfld   string [mscorlib]System.String::Empty
0xd99b  br.s     loc_D9A9
0xd99d  ldloc.s  6
0xd99f  callvirt instance class [mscorlib]System.Exception [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Scheduling.TaskResult::get_Exception()
0xd9a4  callvirt instance string [mscorlib]System.Object::ToString()
0xd9a9  stloc.s  8
0xd9ab  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xd9b0  ldstr    aTaskstatus0Det// "TaskStatus: {0}, Details: {1}, Exceptio"...
0xd9b5  ldc.i4.4
0xd9b6  newarr   [mscorlib]System.Object
0xd9bb  dup
0xd9bc  ldc.i4.0
0xd9bd  ldloc.s  6
0xd9bf  callvirt instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.Config.Wrapper.TaskStatus [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Scheduling.TaskResult::get_Status()
0xd9c4  box      [Microsoft.Crm.Core]Microsoft.Crm.Config.Wrapper.TaskStatus
0xd9c9  stelem.ref
0xd9ca  dup
0xd9cb  ldc.i4.1
0xd9cc  ldloc.s  6
0xd9ce  callvirt instance string [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Scheduling.TaskResult::get_Details()
0xd9d3  stelem.ref
0xd9d4  dup
0xd9d5  ldc.i4.2
0xd9d6  ldloc.s  8
0xd9d8  stelem.ref
0xd9d9  dup
0xd9da  ldc.i4.3
0xd9db  ldloc.s  5
0xd9dd  callvirt instance string Microsoft.Crm.CrmLive.Provisioning.JitUserExecutionResult::get_TaskLog()
0xd9e2  stelem.ref
0xd9e3  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xd9e8  stloc.s  9
0xd9ea  ldloc.s  6
0xd9ec  callvirt instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.Config.Wrapper.TaskStatus [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Scheduling.TaskResult::get_Status()
0xd9f1  ldc.i4.4
0xd9f2  beq.s    loc_DA1C
0xd9f4  call     class Microsoft.Crm.CrmLive.Provisioning.JitUserProcessingEventSource Microsoft.Crm.CrmLive.Provisioning.JitUserProcessingEventSource::get_Instance()
0xd9f9  ldarg.1
0xd9fa  ldarg.2
0xd9fb  ldloc.s  9
0xd9fd  ldloc.s  4
0xd9ff  callvirt instance int64 [System]System.Diagnostics.Stopwatch::get_ElapsedMilliseconds()
0xda04  conv.r8
0xda05  callvirt instance void Microsoft.Crm.CrmLive.Provisioning.JitUserProcessingEventSource::JitUserProvisioningFailed(valuetype [mscorlib]System.Guid orgId, valuetype [mscorlib]System.Guid directoryObjectId, string exception, float64 timeTaken)
0xda0a  ldarg.0
0xda0b  ldarg.1
0xda0c  ldarg.2
0xda0d  ldloc.0
0xda0e  ldc.i4.1
0xda0f  add
0xda10  dup
0xda11  stloc.0
0xda12  call     instance void Microsoft.Crm.CrmLive.Provisioning.JitUserProcessing::SetJitRequestCounterForUser(valuetype [mscorlib]System.Guid organizationId, valuetype [mscorlib]System.Guid objectId, int32 numberOfJitRequests)
0xda17  ldc.i4.0
0xda18  stloc.s  7
0xda1a  leave.s  loc_DA82
0xda1c  call     class Microsoft.Crm.CrmLive.Provisioning.JitUserProcessingEventSource Microsoft.Crm.CrmLive.Provisioning.JitUserProcessingEventSource::get_Instance()
0xda21  ldarg.1
0xda22  ldarg.2
0xda23  ldloc.s  4
0xda25  callvirt instance int64 [System]System.Diagnostics.Stopwatch::get_ElapsedMilliseconds()
0xda2a  conv.r8
0xda2b  callvirt instance void Microsoft.Crm.CrmLive.Provisioning.JitUserProcessingEventSource::JitUserProvisioningCompleted(valuetype [mscorlib]System.Guid orgId, valuetype [mscorlib]System.Guid directoryObjectId, float64 timeTaken)
0xda30  ldc.i4.1
0xda31  stloc.s  7
0xda33  leave.s  loc_DA82
0xda35  leave.s  loc_DA80
0xda37  stloc.s  0xA
0xda39  ldloc.s  4
0xda3b  callvirt instance void [System]System.Diagnostics.Stopwatch::Stop()
0xda40  call     class Microsoft.Crm.CrmLive.Provisioning.JitUserProcessingEventSource Microsoft.Crm.CrmLive.Provisioning.JitUserProcessingEventSource::get_Instance()
0xda45  ldarg.1
0xda46  ldarg.2
0xda47  ldloc.s  0xA
0xda49  callvirt instance string [mscorlib]System.Object::ToString()
0xda4e  ldloc.s  4
0xda50  callvirt instance int64 [System]System.Diagnostics.Stopwatch::get_ElapsedMilliseconds()
0xda55  conv.r8
0xda56  callvirt instance void Microsoft.Crm.CrmLive.Provisioning.JitUserProcessingEventSource::JitUserProvisioningFailed(valuetype [mscorlib]System.Guid orgId, valuetype [mscorlib]System.Guid directoryObjectId, string exception, float64 timeTaken)
0xda5b  ldarg.0
0xda5c  ldarg.1
0xda5d  ldarg.2
0xda5e  ldloc.0
0xda5f  ldc.i4.1
0xda60  add
0xda61  dup
0xda62  stloc.0
0xda63  call     instance void Microsoft.Crm.CrmLive.Provisioning.JitUserProcessing::SetJitRequestCounterForUser(valuetype [mscorlib]System.Guid organizationId, valuetype [mscorlib]System.Guid objectId, int32 numberOfJitRequests)
0xda68  ldc.i4.0
0xda69  stloc.s  7
0xda6b  leave.s  loc_DA82
0xda6d  call     class Microsoft.Crm.CrmLive.Provisioning.JitUserProcessingEventSource Microsoft.Crm.CrmLive.Provisioning.JitUserProcessingEventSource::get_Instance()
0xda72  ldarg.1
0xda73  ldarg.2
0xda74  ldstr    aProvisioningca// "ProvisioningCache"
0xda79  callvirt instance void Microsoft.Crm.CrmLive.Provisioning.JitUserProcessingEventSource::JitUserExceededRequestLimit(valuetype [mscorlib]System.Guid orgId, valuetype [mscorlib]System.Guid directoryObjectId, string counterSource)
0xda7e  ldc.i4.0
0xda7f  ret
0xda80  ldc.i4.0
0xda81  ret
0xda82  ldloc.s  7
0xda84  ret
```
