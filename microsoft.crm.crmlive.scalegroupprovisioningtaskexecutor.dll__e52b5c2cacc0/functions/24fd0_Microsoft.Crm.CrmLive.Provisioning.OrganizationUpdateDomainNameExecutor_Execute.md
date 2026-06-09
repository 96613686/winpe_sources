# Microsoft.Crm.CrmLive.Provisioning.OrganizationUpdateDomainNameExecutor::Execute

- ea: `0x24fd0`
- end: `0x25097`
- name: `Microsoft.Crm.CrmLive.Provisioning.OrganizationUpdateDomainNameExecutor::Execute`
- size: `199`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x1c230`
- `0x1c3b0`
- `0x24fd0`

## string_xrefs

- `0x25018`: `task.QueueItem.OrganizationId`

## pseudocode

```c

```

## disassembly

```asm
0x24fd0  call     class [Microsoft.Crm.Core]Microsoft.Crm.ISiteSettingsProvider [Microsoft.Crm.Core]Microsoft.Crm.SiteSettingsProvider::get_Instance()
0x24fd5  ldstr    aRootdomain// "RootDomain"
0x24fda  ldc.i4.0
0x24fdb  callvirt T0x2B000011
0x24fe0  stloc.0
0x24fe1  ldarg.1
0x24fe2  callvirt instance class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.QueueItem [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Provisioning.QueueItemTask::get_QueueItem()
0x24fe7  callvirt instance string [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemBase::get_ItemData()
0x24fec  call     class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.OrganizationUpdateDomainNameData [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.OrganizationUpdateDomainNameData::Deserialize(string)
0x24ff1  stloc.1
0x24ff2  ldloc.1
0x24ff3  ldstr    aItemdata// "itemData"
0x24ff8  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x24ffd  ldloc.1
0x24ffe  callvirt instance string [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.OrganizationUpdateDomainNameData::get_NewDomainName()
0x25003  ldstr    aItemdataNewdom// "itemData.NewDomainName"
0x25008  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string, string)
0x2500d  ldarg.1
0x2500e  callvirt instance class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.QueueItem [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Provisioning.QueueItemTask::get_QueueItem()
0x25013  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemBase::get_OrganizationId()
0x25018  ldstr    aTaskQueueitemO// "task.QueueItem.OrganizationId"
0x2501d  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfGuidEmpty(valuetype [mscorlib]System.Guid, string)
0x25022  ldloc.1
0x25023  callvirt instance string [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.OrganizationUpdateDomainNameData::get_OldDomainName()
0x25028  ldloc.1
0x25029  callvirt instance string [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.OrganizationUpdateDomainNameData::get_NewDomainName()
0x2502e  ldc.i4.5
0x2502f  call     bool [mscorlib]System.String::Equals(string, string, valuetype [mscorlib]System.StringComparison)
0x25034  brfalse.s loc_25042
0x25036  ldc.i4.4
0x25037  ldstr    aNoActionTaken// "No action taken"
0x2503c  newobj   instance void [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Scheduling.TaskResult::.ctor(valuetype [Microsoft.Crm.Core]Microsoft.Crm.Config.Wrapper.TaskStatus, string)
0x25041  ret
0x25042  ldloc.1
0x25043  callvirt instance string [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.OrganizationUpdateDomainNameData::get_NewDomainName()
0x25048  ldstr    asc_3CF8E// "."
0x2504d  ldloc.0
0x2504e  call     string [mscorlib]System.String::Concat(string, string, string)
0x25053  stloc.2
0x25054  call     class Microsoft.Crm.CrmLive.Provisioning.IOrganizationDatabaseAccess Microsoft.Crm.CrmLive.Provisioning.OrganizationDatabaseAccess::NewService()
0x25059  ldarg.1
0x2505a  callvirt instance class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.QueueItem [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Provisioning.QueueItemTask::get_QueueItem()
0x2505f  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemBase::get_OrganizationId()
0x25064  ldloc.2
0x25065  callvirt instance bool Microsoft.Crm.CrmLive.Provisioning.IOrganizationDatabaseAccess::UpdateOrganizationUrlsInTemplates(valuetype [mscorlib]System.Guid organizationId, string newFullDomain)
0x2506a  pop
0x2506b  ldc.i4.4
0x2506c  ldstr    aSuccess_0// "Success"
0x25071  newobj   instance void [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Scheduling.TaskResult::.ctor(valuetype [Microsoft.Crm.Core]Microsoft.Crm.Config.Wrapper.TaskStatus, string)
0x25076  stloc.3
0x25077  leave.s  loc_25095
0x25079  stloc.s  4
0x2507b  ldstr    aFailedRetrying// "Failed, retrying"
0x25080  ldloc.s  4
0x25082  ldarg.1
0x25083  callvirt instance class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.QueueItem [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Provisioning.QueueItemTask::get_QueueItem()
0x25088  callvirt instance int32 [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemBase::get_RetryCount()
0x2508d  call     class [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Scheduling.TaskResult [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Scheduling.TaskResult::BuildRetry(string, class [mscorlib]System.Exception, int32)
0x25092  stloc.3
0x25093  leave.s  loc_25095
0x25095  ldloc.3
0x25096  ret
```
