# Microsoft.Crm.CrmLive.Provisioning.OrganizationDisableYammerExecutor::Execute

- ea: `0x15080`
- end: `0x151c9`
- name: `Microsoft.Crm.CrmLive.Provisioning.OrganizationDisableYammerExecutor::Execute`
- size: `329`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0x15080`
- `0x1c2a0`
- `0x1c3b0`
- `0x2f0f0`

## string_xrefs

- `0x15185`: `CrmScaleGroupProvisioningService`
- `0x15091`: `task.QueueItem`
- `0x150aa`: `Parameter 'task' of unexpected type`
- `0x1511c`: `Finished OrganizationService to Disable Yammer for org {0}`
- `0x15144`: `Error Occurred OrganizationService to Disable Yammer for org {0}`

## pseudocode

```c

```

## disassembly

```asm
0x15080  ldarg.1
0x15081  ldstr    aTask// "task"
0x15086  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x1508b  ldarg.1
0x1508c  callvirt instance class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.QueueItem [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Provisioning.QueueItemTask::get_QueueItem()
0x15091  ldstr    aTaskQueueitem// "task.QueueItem"
0x15096  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x1509b  ldarg.1
0x1509c  callvirt instance class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.QueueItem [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Provisioning.QueueItemTask::get_QueueItem()
0x150a1  callvirt instance int32 [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemBase::get_ItemType()
0x150a6  ldc.i4.s 0x5A
0x150a8  ceq
0x150aa  ldstr    aParameterTaskO// "Parameter 'task' of unexpected type"
0x150af  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x150b4  ldarg.1
0x150b5  callvirt instance class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.QueueItem [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Provisioning.QueueItemTask::get_QueueItem()
0x150ba  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemBase::get_OrganizationId()
0x150bf  stloc.0
0x150c0  ldloc.0
0x150c1  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x150c6  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x150cb  ldstr    aCannotDisableY// "Cannot disable yammer for an organizati"...
0x150d0  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x150d5  ldloc.0
0x150d6  call     void Microsoft.Crm.CrmLive.Provisioning.TracingListener::SetOrganizationId(valuetype [mscorlib]System.Guid organizationId)
0x150db  ldloc.0
0x150dc  ldstr    aOrganization// "Organization"
0x150e1  ldstr    aDisableYammer// "Disable Yammer"
0x150e6  call     void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.PerformanceAuditHistoryService::CreateStartEntry(valuetype [mscorlib]System.Guid, string, string)
0x150eb  ldsfld   string [mscorlib]System.String::Empty
0x150f0  stloc.1
0x150f1  call     class Microsoft.Crm.CrmLive.Provisioning.IOrganizationDatabaseAccess Microsoft.Crm.CrmLive.Provisioning.OrganizationDatabaseAccess::NewService()
0x150f6  ldloc.0
0x150f7  callvirt instance void Microsoft.Crm.CrmLive.Provisioning.IOrganizationDatabaseAccess::DisableYammer(valuetype [mscorlib]System.Guid organizationId)
0x150fc  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x15101  ldstr    aDisabledYammer// "Disabled Yammer for Organizaion ={0}"
0x15106  ldc.i4.1
0x15107  newarr   [mscorlib]System.Object
0x1510c  dup
0x1510d  ldc.i4.0
0x1510e  ldloc.0
0x1510f  box      [mscorlib]System.Guid
0x15114  stelem.ref
0x15115  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x1511a  stloc.1
0x1511b  ldarg.0
0x1511c  ldstr    aFinishedOrgani// "Finished OrganizationService to Disable"...
0x15121  ldc.i4.1
0x15122  newarr   [mscorlib]System.Object
0x15127  dup
0x15128  ldc.i4.0
0x15129  ldloc.0
0x1512a  box      [mscorlib]System.Guid
0x1512f  stelem.ref
0x15130  call     instance void [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Provisioning.TaskExecutorBase::TraceInfo(string, object[])
0x15135  ldc.i4.4
0x15136  ldloc.1
0x15137  newobj   instance void [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Scheduling.TaskResult::.ctor(valuetype [Microsoft.Crm.Core]Microsoft.Crm.Config.Wrapper.TaskStatus, string)
0x1513c  stloc.2
0x1513d  leave    loc_151C7
0x15142  stloc.3
0x15143  ldarg.0
0x15144  ldstr    aErrorOccurredO// "Error Occurred OrganizationService to D"...
0x15149  ldc.i4.1
0x1514a  newarr   [mscorlib]System.Object
0x1514f  dup
0x15150  ldc.i4.0
0x15151  ldloc.0
0x15152  box      [mscorlib]System.Guid
0x15157  stelem.ref
0x15158  call     instance void [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Provisioning.TaskExecutorBase::TraceInfo(string, object[])
0x1515d  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x15162  ldstr    aFailedToDisabl// "Failed to disable Yammer for Organizaio"...
0x15167  ldc.i4.1
0x15168  newarr   [mscorlib]System.Object
0x1516d  dup
0x1516e  ldc.i4.0
0x1516f  ldloc.0
0x15170  box      [mscorlib]System.Guid
0x15175  stelem.ref
0x15176  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x1517b  stloc.1
0x1517c  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmEventLog::.ctor()
0x15181  stloc.s  4
0x15183  ldloc.s  4
0x15185  ldstr    aCrmscalegroupp// "CrmScaleGroupProvisioningService"
0x1518a  ldc.i4.1
0x1518b  ldc.i4   0xC0006005
0x15190  conv.u8
0x15191  ldc.i4.3
0x15192  newarr   [mscorlib]System.Object
0x15197  dup
0x15198  ldc.i4.0
0x15199  ldloc.0
0x1519a  box      [mscorlib]System.Guid
0x1519f  stelem.ref
0x151a0  dup
0x151a1  ldc.i4.1
0x151a2  ldloc.1
0x151a3  stelem.ref
0x151a4  dup
0x151a5  ldc.i4.2
0x151a6  ldloc.3
0x151a7  stelem.ref
0x151a8  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmEventLog::WriteEntry(string, valuetype [System]System.Diagnostics.EventLogEntryType, int64, object[])
0x151ad  leave.s  loc_151BB
0x151af  ldloc.s  4
0x151b1  brfalse.s loc_151BA
0x151b3  ldloc.s  4
0x151b5  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x151ba  endfinally
0x151bb  ldc.i4.s 0xB
0x151bd  ldloc.1
0x151be  ldloc.3
0x151bf  newobj   instance void [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Scheduling.TaskResult::.ctor(valuetype [Microsoft.Crm.Core]Microsoft.Crm.Config.Wrapper.TaskStatus, string, class [mscorlib]System.Exception)
0x151c4  stloc.2
0x151c5  leave.s  loc_151C7
0x151c7  ldloc.2
0x151c8  ret
```
