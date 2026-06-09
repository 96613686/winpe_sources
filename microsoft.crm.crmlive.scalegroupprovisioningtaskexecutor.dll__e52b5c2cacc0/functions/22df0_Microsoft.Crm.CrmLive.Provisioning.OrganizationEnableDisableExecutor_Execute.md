# Microsoft.Crm.CrmLive.Provisioning.OrganizationEnableDisableExecutor::Execute

- ea: `0x22df0`
- end: `0x22ebf`
- name: `Microsoft.Crm.CrmLive.Provisioning.OrganizationEnableDisableExecutor::Execute`
- size: `207`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0x1aea0`
- `0x1af50`
- `0x1bb50`
- `0x22df0`

## string_xrefs

- `0x22e3d`: `CrmScaleGroupProvisioningService`
- `0x22e72`: `CrmScaleGroupProvisioningService`

## pseudocode

```c

```

## disassembly

```asm
0x22df0  ldnull
0x22df1  stloc.0
0x22df2  ldarg.1
0x22df3  callvirt instance class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.QueueItem [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Provisioning.QueueItemTask::get_QueueItem()
0x22df8  stloc.1
0x22df9  ldloc.1
0x22dfa  callvirt instance string [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemBase::get_ItemData()
0x22dff  call     class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.OrganizationEnableDisableInfo [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.OrganizationEnableDisableInfo::Deserialize(string)
0x22e04  stloc.0
0x22e05  newobj   instance void Microsoft.Crm.CrmLive.Provisioning.Organization::.ctor()
0x22e0a  stloc.2
0x22e0b  ldloc.0
0x22e0c  callvirt instance bool [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.OrganizationEnableDisableInfo::get_EnableOrganization()
0x22e11  brfalse.s loc_22E21
0x22e13  ldloc.2
0x22e14  ldloc.0
0x22e15  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.OrganizationEnableDisableInfo::get_OrganizationId()
0x22e1a  callvirt instance void Microsoft.Crm.CrmLive.Provisioning.Organization::EnableOrganization(valuetype [mscorlib]System.Guid organizationId)
0x22e1f  br.s     loc_22E2D
0x22e21  ldloc.2
0x22e22  ldloc.0
0x22e23  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.OrganizationEnableDisableInfo::get_OrganizationId()
0x22e28  callvirt instance void Microsoft.Crm.CrmLive.Provisioning.Organization::DisableOrganization(valuetype [mscorlib]System.Guid organizationId)
0x22e2d  leave    loc_22EB3
0x22e32  pop
0x22e33  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmEventLog::.ctor()
0x22e38  stloc.3
0x22e39  ldloc.0
0x22e3a  brtrue.s loc_22E71
0x22e3c  ldloc.3
0x22e3d  ldstr    aCrmscalegroupp// "CrmScaleGroupProvisioningService"
0x22e42  ldc.i4.1
0x22e43  ldc.i4   0xC0004628
0x22e48  conv.u8
0x22e49  ldc.i4.2
0x22e4a  newarr   [mscorlib]System.Object
0x22e4f  dup
0x22e50  ldc.i4.0
0x22e51  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x22e56  box      [mscorlib]System.Guid
0x22e5b  stelem.ref
0x22e5c  dup
0x22e5d  ldc.i4.1
0x22e5e  ldloc.1
0x22e5f  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemBase::get_QueueItemId()
0x22e64  box      [mscorlib]System.Guid
0x22e69  stelem.ref
0x22e6a  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmEventLog::WriteEntry(string, valuetype [System]System.Diagnostics.EventLogEntryType, int64, object[])
0x22e6f  br.s     loc_22EA5
0x22e71  ldloc.3
0x22e72  ldstr    aCrmscalegroupp// "CrmScaleGroupProvisioningService"
0x22e77  ldc.i4.1
0x22e78  ldc.i4   0xC0004628
0x22e7d  conv.u8
0x22e7e  ldc.i4.2
0x22e7f  newarr   [mscorlib]System.Object
0x22e84  dup
0x22e85  ldc.i4.0
0x22e86  ldloc.0
0x22e87  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.OrganizationEnableDisableInfo::get_OrganizationId()
0x22e8c  box      [mscorlib]System.Guid
0x22e91  stelem.ref
0x22e92  dup
0x22e93  ldc.i4.1
0x22e94  ldloc.1
0x22e95  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemBase::get_QueueItemId()
0x22e9a  box      [mscorlib]System.Guid
0x22e9f  stelem.ref
0x22ea0  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmEventLog::WriteEntry(string, valuetype [System]System.Diagnostics.EventLogEntryType, int64, object[])
0x22ea5  leave.s  loc_22EB1
0x22ea7  ldloc.3
0x22ea8  brfalse.s loc_22EB0
0x22eaa  ldloc.3
0x22eab  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x22eb0  endfinally
0x22eb1  rethrow
0x22eb3  ldc.i4.4
0x22eb4  ldstr    aSuccess// "success"
0x22eb9  newobj   instance void [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Scheduling.TaskResult::.ctor(valuetype [Microsoft.Crm.Core]Microsoft.Crm.Config.Wrapper.TaskStatus, string)
0x22ebe  ret
```
