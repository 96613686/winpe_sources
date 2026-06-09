# Microsoft.Crm.CrmLive.Provisioning.OrganizationProvisionExecutor::RetryOnFailure

- ea: `0x24710`
- end: `0x2485a`
- name: `Microsoft.Crm.CrmLive.Provisioning.OrganizationProvisionExecutor::RetryOnFailure`
- size: `330`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x24370`

## callees

- `0x8a60`
- `0x21390`
- `0x23e50`
- `0x23e90`
- `0x23ed0`
- `0x24190`
- `0x24690`
- `0x246f0`
- `0x24710`

## string_xrefs

- `0x24751`: `Skipping deprovision because template debug mode is on`
- `0x247a2`: `Org provision has reached the max retry count:{0} so the org will now be deleted. Exception : {1}`
- `0x247e4`: `complete`

## pseudocode

```c

```

## disassembly

```asm
0x24710  call     bool Microsoft.Crm.CrmLive.Provisioning.MtpOrganizationProvisioner::TemplateDebuggingModeEnabled()
0x24715  stloc.0
0x24716  ldarg.2
0x24717  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.CrmLive.Provisioning.OrganizationCreateInfoLocal::get_OrganizationId()
0x2471c  ldarg.1
0x2471d  callvirt instance class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.QueueItem [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Provisioning.QueueItemTask::get_QueueItem()
0x24722  callvirt instance int32 [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemBase::get_RetryCount()
0x24727  call     void Microsoft.Crm.CrmLive.Provisioning.ScaleGroupProvisioningPerformanceCounters::UpdateProvisioningFailureCounters(valuetype [mscorlib]System.Guid organizationId, int32 retryCount)
0x2472c  ldarg.2
0x2472d  callvirt instance bool Microsoft.Crm.CrmLive.Provisioning.OrganizationCreateInfoLocal::get_PerformSingleAttemptOnly()
0x24732  brfalse.s loc_2473D
0x24734  ldc.i4.s 0xB
0x24736  ldarg.3
0x24737  newobj   instance void [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Scheduling.TaskResult::.ctor(valuetype [Microsoft.Crm.Core]Microsoft.Crm.Config.Wrapper.TaskStatus, class [mscorlib]System.Exception)
0x2473c  ret
0x2473d  ldarg.2
0x2473e  callvirt instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.OrganizationType Microsoft.Crm.CrmLive.Provisioning.OrganizationCreateInfoLocal::get_OrgType()
0x24743  ldc.i4.8
0x24744  beq.s    loc_2474E
0x24746  ldarg.2
0x24747  callvirt instance bool Microsoft.Crm.CrmLive.Provisioning.OrganizationCreateInfoLocal::get_CreateTemplate()
0x2474c  brfalse.s loc_24768
0x2474e  ldloc.0
0x2474f  brfalse.s loc_2475D
0x24751  ldstr    aSkippingDeprov// "Skipping deprovision because template d"...
0x24756  call     void [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Provisioning.ProvisioningTaskLogger::LogLine(string)
0x2475b  br.s     loc_24768
0x2475d  ldarg.2
0x2475e  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.CrmLive.Provisioning.OrganizationCreateInfoLocal::get_OrganizationId()
0x24763  call     void Microsoft.Crm.CrmLive.Provisioning.OrganizationProvisionExecutor::MarkOrganizationForDeprovision(valuetype [mscorlib]System.Guid organizationId)
0x24768  ldarg.2
0x24769  callvirt instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.OrganizationType Microsoft.Crm.CrmLive.Provisioning.OrganizationCreateInfoLocal::get_OrgType()
0x2476e  ldc.i4.8
0x2476f  beq.s    loc_24782
0x24771  ldarg.2
0x24772  callvirt instance bool Microsoft.Crm.CrmLive.Provisioning.OrganizationCreateInfoLocal::get_CreateTemplate()
0x24777  brtrue.s loc_24782
0x24779  ldarg.2
0x2477a  callvirt instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.OrganizationType Microsoft.Crm.CrmLive.Provisioning.OrganizationCreateInfoLocal::get_OrgType()
0x2477f  ldc.i4.3
0x24780  bne.un.s loc_2478B
0x24782  ldc.i4.s 0xB
0x24784  ldarg.3
0x24785  newobj   instance void [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Scheduling.TaskResult::.ctor(valuetype [Microsoft.Crm.Core]Microsoft.Crm.Config.Wrapper.TaskStatus, class [mscorlib]System.Exception)
0x2478a  ret
0x2478b  ldarg.1
0x2478c  callvirt instance class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.QueueItem [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Provisioning.QueueItemTask::get_QueueItem()
0x24791  callvirt instance int32 [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemBase::get_RetryCount()
0x24796  call     bool Microsoft.Crm.CrmLive.Provisioning.OrganizationProvisionExecutor::HasReachedTheMaxRetryCount(int32 currentRetryCount)
0x2479b  brfalse.s loc_2480A
0x2479d  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x247a2  ldstr    aOrgProvisionHa// "Org provision has reached the max retry"...
0x247a7  ldc.i4.2
0x247a8  newarr   [mscorlib]System.Object
0x247ad  dup
0x247ae  ldc.i4.0
0x247af  ldarg.1
0x247b0  callvirt instance class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.QueueItem [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Provisioning.QueueItemTask::get_QueueItem()
0x247b5  callvirt instance int32 [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemBase::get_RetryCount()
0x247ba  box      [mscorlib]System.Int32
0x247bf  stelem.ref
0x247c0  dup
0x247c1  ldc.i4.1
0x247c2  ldarg.3
0x247c3  callvirt instance string [mscorlib]System.Object::ToString()
0x247c8  stelem.ref
0x247c9  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x247ce  stloc.1
0x247cf  call     class [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.IAuditHistory [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.AuditHistory::NewService()
0x247d4  ldarg.1
0x247d5  callvirt instance class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.QueueItem [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Provisioning.QueueItemTask::get_QueueItem()
0x247da  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemBase::get_QueueItemId()
0x247df  ldstr    aQueueitem// "QueueItem"
0x247e4  ldstr    aComplete// "complete"
0x247e9  ldloc.1
0x247ea  ldc.i4.0
0x247eb  ldarg.2
0x247ec  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.CrmLive.Provisioning.OrganizationCreateInfoLocal::get_OrganizationId()
0x247f1  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.IAuditHistory::CreateCompletedEntry(valuetype [mscorlib]System.Guid, string, string, string, bool, valuetype [mscorlib]System.Guid)
0x247f6  ldarg.2
0x247f7  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.CrmLive.Provisioning.OrganizationCreateInfoLocal::get_OrganizationId()
0x247fc  call     void Microsoft.Crm.CrmLive.Provisioning.OrganizationProvisionExecutor::MarkOrganizationForDeprovision(valuetype [mscorlib]System.Guid organizationId)
0x24801  ldc.i4.s 0xB
0x24803  ldloc.1
0x24804  newobj   instance void [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Scheduling.TaskResult::.ctor(valuetype [Microsoft.Crm.Core]Microsoft.Crm.Config.Wrapper.TaskStatus, string)
0x24809  ret
0x2480a  ldarg.1
0x2480b  callvirt instance class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.QueueItem [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Provisioning.QueueItemTask::get_QueueItem()
0x24810  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemBase::get_DependentQueueItemId()
0x24815  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x2481a  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x2481f  brfalse.s loc_24842
0x24821  newobj   instance void [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.QueueManager::.ctor()
0x24826  ldarg.1
0x24827  callvirt instance class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.QueueItem [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Provisioning.QueueItemTask::get_QueueItem()
0x2482c  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemBase::get_QueueItemId()
0x24831  ldnull
0x24832  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x24837  box      [mscorlib]System.Guid
0x2483c  ldnull
0x2483d  callvirt instance void [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.QueueManager::UpdateQueueItem(valuetype [mscorlib]System.Guid, string, object, string)
0x24842  ldarg.3
0x24843  callvirt instance string [mscorlib]System.Exception::get_Message()
0x24848  ldarg.3
0x24849  ldarg.1
0x2484a  callvirt instance class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.QueueItem [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Provisioning.QueueItemTask::get_QueueItem()
0x2484f  callvirt instance int32 [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemBase::get_RetryCount()
0x24854  call     class [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Scheduling.TaskResult [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Scheduling.TaskResult::BuildRetry(string, class [mscorlib]System.Exception, int32)
0x24859  ret
```
