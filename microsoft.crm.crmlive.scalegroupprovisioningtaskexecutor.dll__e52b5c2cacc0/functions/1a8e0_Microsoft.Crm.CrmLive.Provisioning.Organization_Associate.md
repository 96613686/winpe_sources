# Microsoft.Crm.CrmLive.Provisioning.Organization::Associate

- ea: `0x1a8e0`
- end: `0x1a918`
- name: `Microsoft.Crm.CrmLive.Provisioning.Organization::Associate`
- size: `56`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x24370`

## callees

- `0x1a920`
- `0x1b240`

## string_xrefs

- `0x1a8e1`: `createInfo`
- `0x1a8ec`: `taskInfo`

## pseudocode

```c

```

## disassembly

```asm
0x1a8e0  ldarg.1
0x1a8e1  ldstr    aCreateinfo// "createInfo"
0x1a8e6  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x1a8eb  ldarg.2
0x1a8ec  ldstr    aTaskinfo// "taskInfo"
0x1a8f1  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x1a8f6  ldarg.0
0x1a8f7  ldarg.2
0x1a8f8  stfld    class [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Provisioning.QueueItemTask Microsoft.Crm.CrmLive.Provisioning.Organization::task
0x1a8fd  ldarg.0
0x1a8fe  ldarg.1
0x1a8ff  ldarg.2
0x1a900  callvirt instance class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.QueueItem [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Provisioning.QueueItemTask::get_QueueItem()
0x1a905  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemBase::get_QueueItemId()
0x1a90a  call     instance class Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties Microsoft.Crm.CrmLive.Provisioning.Organization::GenerateOrganizationProperties(class Microsoft.Crm.CrmLive.Provisioning.OrganizationCreateInfoLocal createInfo, valuetype [mscorlib]System.Guid queueItemId)
0x1a90f  stloc.0
0x1a910  ldarg.0
0x1a911  ldloc.0
0x1a912  call     instance void Microsoft.Crm.CrmLive.Provisioning.Organization::Associate(class Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties orgProperties)
0x1a917  ret
```
