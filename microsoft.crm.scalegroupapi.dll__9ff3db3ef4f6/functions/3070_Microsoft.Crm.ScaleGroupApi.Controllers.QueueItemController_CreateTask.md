# Microsoft.Crm.ScaleGroupApi.Controllers.QueueItemController::CreateTask

- ea: `0x3070`
- end: `0x30ba`
- name: `Microsoft.Crm.ScaleGroupApi.Controllers.QueueItemController::CreateTask`
- size: `74`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x2f10`

## callees

- `0x1630`
- `0x1640`
- `0x1660`

## pseudocode

```c

```

## disassembly

```asm
0x3070  newobj   instance void [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemBase::.ctor()
0x3075  stloc.0
0x3076  ldloc.0
0x3077  ldc.i4.2
0x3078  callvirt instance void [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemBase::set_ItemType(int32)
0x307d  ldloc.0
0x307e  call     class [Microsoft.Crm.Core]Microsoft.Crm.IScaleGroupInfoProvider [Microsoft.Crm.Core]Microsoft.Crm.ScaleGroupInfoProvider::get_Instance()
0x3083  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IScaleGroupInfoProvider::GetScaleGroupId()
0x3088  callvirt instance void [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemBase::set_ScaleGroupId(valuetype [mscorlib]System.Guid)
0x308d  ldloc.0
0x308e  ldarg.0
0x308f  callvirt instance string Microsoft.Crm.ScaleGroupApi.Models.SGQueueItem::get_ItemData()
0x3094  callvirt instance void [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemBase::set_ItemData(string)
0x3099  ldloc.0
0x309a  ldarg.0
0x309b  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.ScaleGroupApi.Models.SGQueueItem::get_OrganizationId()
0x30a0  callvirt instance void [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemBase::set_OrganizationId(valuetype [mscorlib]System.Guid)
0x30a5  call     class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemRequest [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemRequest::NewRequest()
0x30aa  stloc.1
0x30ab  ldarg.0
0x30ac  ldloc.1
0x30ad  ldloc.0
0x30ae  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemRequest::CreateReady(class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemBase)
0x30b3  callvirt instance void Microsoft.Crm.ScaleGroupApi.Models.SGQueueItem::set_QueueItemId(valuetype [mscorlib]System.Guid value)
0x30b8  ldarg.0
0x30b9  ret
```
