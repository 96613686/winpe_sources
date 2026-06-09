# Microsoft.Crm.CrmLive.Provisioning.ConfigureReportServerExecutor::Execute

- ea: `0x21550`
- end: `0x216c1`
- name: `Microsoft.Crm.CrmLive.Provisioning.ConfigureReportServerExecutor::Execute`
- size: `369`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x21550`
- `0x216d0`
- `0x217e0`

## string_xrefs

- `0x21669`: `CrmScaleGroupProvisioningService`
- `0x215a8`: `Organization not specified for ConfigureReports`
- `0x215cb`: `configuring report server for {0}`
- `0x2163c`: `Error Configuring Report Server: error message {0}, stack trace {1} `

## pseudocode

```c

```

## disassembly

```asm
0x21550  ldarg.1
0x21551  callvirt instance class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.QueueItem [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Provisioning.QueueItemTask::get_QueueItem()
0x21556  stloc.0
0x21557  ldloc.0
0x21558  callvirt instance string [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemBase::get_ItemData()
0x2155d  call     class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.ConfigureReportServerInfo [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.ConfigureReportServerInfo::Deserialize(string)
0x21562  stloc.1
0x21563  ldnull
0x21564  stloc.2
0x21565  ldloc.1
0x21566  callvirt instance string [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.ConfigureReportServerInfo::get_AvailabilityGroupName()
0x2156b  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x21570  brtrue.s loc_21580
0x21572  ldloc.1
0x21573  callvirt instance string [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.ConfigureReportServerInfo::get_AvailabilityGroupName()
0x21578  call     class [mscorlib]System.Collections.Generic.IEnumerable`1<valuetype [mscorlib]System.Guid> Microsoft.Crm.CrmLive.Provisioning.ConfigureReportServerExecutor::GetOrganizationsToBeConfigured(string availabilityGroupName)
0x2157d  stloc.2
0x2157e  br.s     loc_215B3
0x21580  ldloc.0
0x21581  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemBase::get_OrganizationId()
0x21586  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x2158b  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x21590  brfalse.s loc_215A8
0x21592  ldc.i4.1
0x21593  newarr   [mscorlib]System.Guid
0x21598  dup
0x21599  ldc.i4.0
0x2159a  ldloc.0
0x2159b  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemBase::get_OrganizationId()
0x215a0  stelem   [mscorlib]System.Guid
0x215a5  stloc.2
0x215a6  br.s     loc_215B3
0x215a8  ldstr    aOrganizationNo// "Organization not specified for Configur"...
0x215ad  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0x215b2  throw
0x215b3  ldloc.2
0x215b4  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<valuetype [mscorlib]System.Guid>::GetEnumerator()
0x215b9  stloc.3
0x215ba  br.s     loc_21618
0x215bc  ldloc.3
0x215bd  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<valuetype [mscorlib]System.Guid>::get_Current()
0x215c2  stloc.s  4
0x215c4  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x215c9  ldc.i4.s 0xA
0x215cb  ldstr    aConfiguringRep_0// "configuring report server for {0}"
0x215d0  ldc.i4.1
0x215d1  newarr   [mscorlib]System.Object
0x215d6  dup
0x215d7  ldc.i4.0
0x215d8  ldloc.s  4
0x215da  box      [mscorlib]System.Guid
0x215df  stelem.ref
0x215e0  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x215e5  ldloc.s  4
0x215e7  ldloc.0
0x215e8  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemBase::get_QueueItemId()
0x215ed  call     bool Microsoft.Crm.CrmLive.Provisioning.ConfigureReportServerExecutor::TryConfigureReportServer(valuetype [mscorlib]System.Guid organizationId, valuetype [mscorlib]System.Guid queueItemId)
0x215f2  brfalse.s loc_21618
0x215f4  newobj   instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::.ctor()
0x215f9  stloc.s  5
0x215fb  ldloc.s  5
0x215fd  ldloc.s  4
0x215ff  callvirt instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::set_Id(valuetype [mscorlib]System.Guid)
0x21604  ldloc.s  5
0x21606  ldc.i4.1
0x21607  callvirt instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::set_IsRemoteReportServerConfigured(bool)
0x2160c  newobj   instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.CrmOrganizationService::.ctor()
0x21611  ldloc.s  5
0x21613  call     instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.CrmOrganizationService::UpdateWithoutCheckStatus(class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData)
0x21618  ldloc.3
0x21619  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x2161e  brtrue.s loc_215BC
0x21620  leave.s  loc_2162C
0x21622  ldloc.3
0x21623  brfalse.s loc_2162B
0x21625  ldloc.3
0x21626  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2162b  endfinally
0x2162c  leave    loc_216B5
0x21631  stloc.s  6
0x21633  ldloc.s  6
0x21635  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x2163a  ldc.i4.s 0xA
0x2163c  ldstr    aErrorConfiguri// "Error Configuring Report Server: error "...
0x21641  ldc.i4.2
0x21642  newarr   [mscorlib]System.Object
0x21647  dup
0x21648  ldc.i4.0
0x21649  ldloc.s  6
0x2164b  callvirt instance string [mscorlib]System.Exception::get_Message()
0x21650  stelem.ref
0x21651  dup
0x21652  ldc.i4.1
0x21653  ldloc.s  6
0x21655  callvirt instance string [mscorlib]System.Exception::get_StackTrace()
0x2165a  stelem.ref
0x2165b  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x21660  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmEventLog::.ctor()
0x21665  stloc.s  7
0x21667  ldloc.s  7
0x21669  ldstr    aCrmscalegroupp// "CrmScaleGroupProvisioningService"
0x2166e  ldc.i4.1
0x2166f  ldc.i4   0xC0004687
0x21674  conv.u8
0x21675  ldc.i4.3
0x21676  newarr   [mscorlib]System.Object
0x2167b  dup
0x2167c  ldc.i4.0
0x2167d  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x21682  box      [mscorlib]System.Guid
0x21687  stelem.ref
0x21688  dup
0x21689  ldc.i4.1
0x2168a  ldloc.0
0x2168b  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemBase::get_QueueItemId()
0x21690  box      [mscorlib]System.Guid
0x21695  stelem.ref
0x21696  dup
0x21697  ldc.i4.2
0x21698  ldloc.s  6
0x2169a  callvirt instance string [mscorlib]System.Exception::get_Message()
0x2169f  stelem.ref
0x216a0  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmEventLog::WriteEntry(string, valuetype [System]System.Diagnostics.EventLogEntryType, int64, object[])
0x216a5  leave.s  loc_216B3
0x216a7  ldloc.s  7
0x216a9  brfalse.s loc_216B2
0x216ab  ldloc.s  7
0x216ad  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x216b2  endfinally
0x216b3  rethrow
0x216b5  ldc.i4.4
0x216b6  ldstr    aSuccess// "success"
0x216bb  newobj   instance void [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Scheduling.TaskResult::.ctor(valuetype [Microsoft.Crm.Core]Microsoft.Crm.Config.Wrapper.TaskStatus, string)
0x216c0  ret
```
