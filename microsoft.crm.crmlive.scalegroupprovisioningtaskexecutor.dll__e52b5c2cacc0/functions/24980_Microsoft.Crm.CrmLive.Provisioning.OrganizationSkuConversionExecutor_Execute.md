# Microsoft.Crm.CrmLive.Provisioning.OrganizationSkuConversionExecutor::Execute

- ea: `0x24980`
- end: `0x24a7f`
- name: `Microsoft.Crm.CrmLive.Provisioning.OrganizationSkuConversionExecutor::Execute`
- size: `255`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callees

- `0x3370`
- `0x33b0`
- `0x89c0`
- `0x8a00`
- `0x24980`
- `0x24a80`

## string_xrefs

- `0x24991`: `task.QueueItem`
- `0x249bf`: `Parameter 'task' of unexpected type`
- `0x249a6`: `task.QueueItem.ItemData`

## pseudocode

```c

```

## disassembly

```asm
0x24980  ldarg.1
0x24981  ldstr    aTask// "task"
0x24986  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x2498b  ldarg.1
0x2498c  callvirt instance class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.QueueItem [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Provisioning.QueueItemTask::get_QueueItem()
0x24991  ldstr    aTaskQueueitem// "task.QueueItem"
0x24996  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x2499b  ldarg.1
0x2499c  callvirt instance class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.QueueItem [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Provisioning.QueueItemTask::get_QueueItem()
0x249a1  callvirt instance string [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemBase::get_ItemData()
0x249a6  ldstr    aTaskQueueitemI// "task.QueueItem.ItemData"
0x249ab  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string, string)
0x249b0  ldarg.1
0x249b1  callvirt instance class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.QueueItem [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Provisioning.QueueItemTask::get_QueueItem()
0x249b6  callvirt instance int32 [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemBase::get_ItemType()
0x249bb  ldc.i4.s 0xA
0x249bd  ceq
0x249bf  ldstr    aParameterTaskO// "Parameter 'task' of unexpected type"
0x249c4  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x249c9  ldarg.1
0x249ca  callvirt instance class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.QueueItem [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Provisioning.QueueItemTask::get_QueueItem()
0x249cf  callvirt instance string [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemBase::get_ItemData()
0x249d4  call     class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.OrganizationSkuConversionInfo [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.OrganizationSkuConversionInfo::Deserialize(string)
0x249d9  stloc.0
0x249da  ldloc.0
0x249db  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.OrganizationSkuConversionInfo::get_OrganizationId()
0x249e0  stloc.1
0x249e1  ldloc.0
0x249e2  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.OrganizationSkuConversionInfo::get_OldServiceComponentId()
0x249e7  stloc.2
0x249e8  ldloca.s 2
0x249ea  constrained. [mscorlib]System.Guid
0x249f0  callvirt instance string [mscorlib]System.Object::ToString()
0x249f5  callvirt instance string [mscorlib]System.String::ToUpperInvariant()
0x249fa  call     bool Microsoft.Crm.CrmLive.Provisioning.OrganizationSkuConversionExecutor::IsR3Sku(string sku)
0x249ff  brtrue.s loc_24A0D
0x24a01  ldnull
0x24a02  newobj   instance void Microsoft.Crm.CrmLive.Provisioning.OrganizationDatabaseHardLimitAction::.ctor(class Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties organizationProperties)
0x24a07  ldloc.1
0x24a08  callvirt instance void Microsoft.Crm.CrmLive.Provisioning.OrganizationDatabaseHardLimitAction::Do(valuetype [mscorlib]System.Guid orgId)
0x24a0d  ldnull
0x24a0e  newobj   instance void Microsoft.Crm.CrmLive.Provisioning.ConfigureOrganizationFeaturesAction::.ctor(class Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties organizationProperties)
0x24a13  ldloc.1
0x24a14  callvirt instance void Microsoft.Crm.CrmLive.Provisioning.ConfigureOrganizationFeaturesAction::Do(valuetype [mscorlib]System.Guid orgId)
0x24a19  leave.s  loc_24A75
0x24a1b  stloc.3
0x24a1c  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x24a21  ldstr    aOrganizationsk// "OrganizationSkuConversionExecutor.Execu"...
0x24a26  ldc.i4.3
0x24a27  newarr   [mscorlib]System.Object
0x24a2c  dup
0x24a2d  ldc.i4.0
0x24a2e  ldloc.1
0x24a2f  box      [mscorlib]System.Guid
0x24a34  stelem.ref
0x24a35  dup
0x24a36  ldc.i4.1
0x24a37  ldarg.1
0x24a38  callvirt instance class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.QueueItem [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Provisioning.QueueItemTask::get_QueueItem()
0x24a3d  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemBase::get_ScaleGroupId()
0x24a42  box      [mscorlib]System.Guid
0x24a47  stelem.ref
0x24a48  dup
0x24a49  ldc.i4.2
0x24a4a  ldarg.1
0x24a4b  callvirt instance class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.QueueItem [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Provisioning.QueueItemTask::get_QueueItem()
0x24a50  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemBase::get_QueueItemId()
0x24a55  box      [mscorlib]System.Guid
0x24a5a  stelem.ref
0x24a5b  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x24a60  ldloc.3
0x24a61  ldarg.1
0x24a62  callvirt instance class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.QueueItem [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Provisioning.QueueItemTask::get_QueueItem()
0x24a67  callvirt instance int32 [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemBase::get_RetryCount()
0x24a6c  call     class [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Scheduling.TaskResult [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Scheduling.TaskResult::BuildRetry(string, class [mscorlib]System.Exception, int32)
0x24a71  stloc.s  4
0x24a73  leave.s  loc_24A7C
0x24a75  ldc.i4.4
0x24a76  newobj   instance void [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Scheduling.TaskResult::.ctor(valuetype [Microsoft.Crm.Core]Microsoft.Crm.Config.Wrapper.TaskStatus)
0x24a7b  ret
0x24a7c  ldloc.s  4
0x24a7e  ret
```
