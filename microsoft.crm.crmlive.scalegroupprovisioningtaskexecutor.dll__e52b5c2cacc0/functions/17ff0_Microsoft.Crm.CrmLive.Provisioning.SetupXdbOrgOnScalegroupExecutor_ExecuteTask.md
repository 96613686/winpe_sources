# Microsoft.Crm.CrmLive.Provisioning.SetupXdbOrgOnScalegroupExecutor::ExecuteTask

- ea: `0x17ff0`
- end: `0x181ac`
- name: `Microsoft.Crm.CrmLive.Provisioning.SetupXdbOrgOnScalegroupExecutor::ExecuteTask`
- size: `444`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x17fb0`

## callees

- `0x17f20`
- `0x17ff0`
- `0x181b0`
- `0x181d0`
- `0x18310`
- `0x1c080`
- `0x1c3b0`

## string_xrefs

- `0x18001`: `task.QueueItem`

## pseudocode

```c

```

## disassembly

```asm
0x17ff0  ldarg.1
0x17ff1  ldstr    aTask// "task"
0x17ff6  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x17ffb  ldarg.1
0x17ffc  callvirt instance class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.QueueItem [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Provisioning.QueueItemTask::get_QueueItem()
0x18001  ldstr    aTaskQueueitem// "task.QueueItem"
0x18006  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x1800b  ldarg.1
0x1800c  callvirt instance class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.QueueItem [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Provisioning.QueueItemTask::get_QueueItem()
0x18011  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemBase::get_OrganizationId()
0x18016  stloc.0
0x18017  ldarg.1
0x18018  callvirt instance class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.QueueItem [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Provisioning.QueueItemTask::get_QueueItem()
0x1801d  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemBase::get_ScaleGroupId()
0x18022  stloc.1
0x18023  ldarg.1
0x18024  callvirt instance class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.QueueItem [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Provisioning.QueueItemTask::get_QueueItem()
0x18029  callvirt instance string [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemBase::get_ItemRuntimeData()
0x1802e  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x18033  brfalse.s loc_1803C
0x18035  newobj   instance void [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.QueueItemRuntimeData::.ctor()
0x1803a  br.s     loc_1804C
0x1803c  ldarg.1
0x1803d  callvirt instance class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.QueueItem [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Provisioning.QueueItemTask::get_QueueItem()
0x18042  callvirt instance string [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemBase::get_ItemRuntimeData()
0x18047  call     class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.QueueItemRuntimeData [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.QueueItemRuntimeData::Deserialize(string)
0x1804c  stloc.2
0x1804d  call     class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.QueueManager [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.QueueManager::NewManager()
0x18052  stloc.3
0x18053  call     class Microsoft.Crm.CrmLive.Provisioning.IOrganizationDatabaseAccess Microsoft.Crm.CrmLive.Provisioning.OrganizationDatabaseAccess::NewService()
0x18058  stloc.s  4
0x1805a  newobj   instance void class [Microsoft.Crm.Core]Microsoft.Crm.EnumEnumerable`1<valuetype Microsoft.Crm.CrmLive.Provisioning.SetupXdbOrgOnScalegroupStage>::.ctor()
0x1805f  ldloc.2
0x18060  callvirt instance int32 [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.QueueItemRuntimeData::get_Stage()
0x18065  call     instance class [mscorlib]System.Collections.Generic.IEnumerable`1<var<u1>> class [Microsoft.Crm.Core]Microsoft.Crm.EnumEnumerable`1<valuetype Microsoft.Crm.CrmLive.Provisioning.SetupXdbOrgOnScalegroupStage>::Enumerate(!!T0)
0x1806a  ldc.i4.1
0x1806b  call     T0x2B000088
0x18070  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<valuetype Microsoft.Crm.CrmLive.Provisioning.SetupXdbOrgOnScalegroupStage>::GetEnumerator()
0x18075  stloc.s  5
0x18077  br       loc_18186
0x1807c  ldloc.s  5
0x1807e  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<valuetype Microsoft.Crm.CrmLive.Provisioning.SetupXdbOrgOnScalegroupStage>::get_Current()
0x18083  stloc.s  6
0x18085  ldloc.2
0x18086  ldloc.s  6
0x18088  callvirt instance void [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.QueueItemRuntimeData::set_Stage(int32)
0x1808d  ldloc.s  6
0x1808f  ldc.i4.s 0x14
0x18091  bgt.s    loc_180A4
0x18093  ldloc.s  6
0x18095  ldc.i4.s 0xA
0x18097  beq.s    loc_180BB
0x18099  ldloc.s  6
0x1809b  ldc.i4.s 0x14
0x1809d  beq.s    loc_180E7
0x1809f  br       loc_18158
0x180a4  ldloc.s  6
0x180a6  ldc.i4.s 0x1E
0x180a8  beq.s    loc_180F1
0x180aa  ldloc.s  6
0x180ac  ldc.i4.s 0x28
0x180ae  beq.s    loc_180FD
0x180b0  ldloc.s  6
0x180b2  ldc.i4.s 0x32
0x180b4  beq.s    loc_18135
0x180b6  br       loc_18158
0x180bb  ldarg.0
0x180bc  ldfld    class Microsoft.Crm.CrmLive.Provisioning.SetupXdbOrgOnScalegroupItemData Microsoft.Crm.CrmLive.Provisioning.SetupXdbOrgOnScalegroupExecutor::ItemData
0x180c1  callvirt instance bool Microsoft.Crm.CrmLive.Provisioning.SetupXdbOrgOnScalegroupItemData::get_MakeUnique()
0x180c6  brfalse  loc_1816F
0x180cb  call     class [Microsoft.Crm.Core]Microsoft.Crm.LocatorService [Microsoft.Crm.Core]Microsoft.Crm.LocatorService::get_Instance()
0x180d0  ldloc.0
0x180d1  callvirt instance string [Microsoft.Crm.Core]Microsoft.Crm.LocatorService::GetOrganizationFriendlyName(valuetype [mscorlib]System.Guid)
0x180d6  stloc.s  7
0x180d8  ldloc.s  4
0x180da  ldloc.0
0x180db  ldloc.s  7
0x180dd  callvirt instance void Microsoft.Crm.CrmLive.Provisioning.IOrganizationDatabaseAccess::MakeRestoredOrganizationUnique(valuetype [mscorlib]System.Guid organizationId, string organizationFriendlyName)
0x180e2  br       loc_1816F
0x180e7  ldarg.0
0x180e8  ldloc.0
0x180e9  ldloc.1
0x180ea  call     instance void Microsoft.Crm.CrmLive.Provisioning.SetupXdbOrgOnScalegroupExecutor::RecreateMaintenanceJobs(valuetype [mscorlib]System.Guid orgId, valuetype [mscorlib]System.Guid scaleGroupId)
0x180ef  br.s     loc_1816F
0x180f1  ldarg.0
0x180f2  ldloc.0
0x180f3  ldloc.1
0x180f4  ldloc.s  4
0x180f6  call     instance void Microsoft.Crm.CrmLive.Provisioning.SetupXdbOrgOnScalegroupExecutor::RestoreReports(valuetype [mscorlib]System.Guid orgId, valuetype [mscorlib]System.Guid scaleGroupId, class Microsoft.Crm.CrmLive.Provisioning.IOrganizationDatabaseAccess orgDbAccess)
0x180fb  br.s     loc_1816F
0x180fd  ldstr    aAdminApiPublis// "Admin.Api.PublishRestoreEvent(organizat"...
0x18102  ldc.i4.1
0x18103  newarr   [mscorlib]System.Object
0x18108  dup
0x18109  ldc.i4.0
0x1810a  ldloc.0
0x1810b  box      [mscorlib]System.Guid
0x18110  stelem.ref
0x18111  newobj   instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.AdminApiTrace::.ctor(string, object[])
0x18116  stloc.s  8
0x18118  call     T0x2B000081
0x1811d  ldloc.0
0x1811e  ldloc.s  4
0x18120  ldloc.s  8
0x18122  callvirt instance void Microsoft.Crm.CrmLive.Provisioning.IOrganization::PublishRestoreEvent(valuetype [mscorlib]System.Guid organizationId, class Microsoft.Crm.CrmLive.Provisioning.IOrganizationDatabaseAccess orgAccess, class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.AdminApiTrace trace)
0x18127  leave.s  loc_1816F
0x18129  ldloc.s  8
0x1812b  brfalse.s loc_18134
0x1812d  ldloc.s  8
0x1812f  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x18134  endfinally
0x18135  newobj   instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.AdminContext::.ctor()
0x1813a  stloc.s  9
0x1813c  ldloc.s  9
0x1813e  newobj   instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.OrganizationService::.ctor(class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.AdminContext)
0x18143  ldloc.0
0x18144  ldc.i4.0
0x18145  callvirt instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.OrganizationService::SetLastTaskStatus(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.OrganizationTaskStatus)
0x1814a  leave.s  loc_1816F
0x1814c  ldloc.s  9
0x1814e  brfalse.s loc_18157
0x18150  ldloc.s  9
0x18152  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x18157  endfinally
0x18158  ldstr    aSetupxdborgons// "SetupXdbOrgOnScalegroup stage not mappe"...
0x1815d  ldloc.s  6
0x1815f  box      Microsoft.Crm.CrmLive.Provisioning.SetupXdbOrgOnScalegroupStage
0x18164  call     string [mscorlib]System.String::Concat(object, object)
0x18169  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmArgumentOutOfRangeException::.ctor(string)
0x1816e  throw
0x1816f  ldloc.3
0x18170  ldarg.1
0x18171  callvirt instance class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.QueueItem [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Provisioning.QueueItemTask::get_QueueItem()
0x18176  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemBase::get_QueueItemId()
0x1817b  ldloc.2
0x1817c  call     string [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.QueueItemRuntimeData::Serialize(class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.QueueItemRuntimeData)
0x18181  callvirt instance void [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.QueueManager::UpdateQueueItemRuntimeData(valuetype [mscorlib]System.Guid, string)
0x18186  ldloc.s  5
0x18188  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x1818d  brtrue   loc_1807C
0x18192  leave.s  loc_181A0
0x18194  ldloc.s  5
0x18196  brfalse.s loc_1819F
0x18198  ldloc.s  5
0x1819a  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1819f  endfinally
0x181a0  ldc.i4.4
0x181a1  ldstr    aSuccess_0// "Success"
0x181a6  newobj   instance void [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Scheduling.TaskResult::.ctor(valuetype [Microsoft.Crm.Core]Microsoft.Crm.Config.Wrapper.TaskStatus, string)
0x181ab  ret
```
