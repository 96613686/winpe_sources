# Microsoft.Crm.CrmLive.Provisioning.Organization::TryCreateCleanupBackupQueueItem

- ea: `0x18eb0`
- end: `0x18f67`
- name: `Microsoft.Crm.CrmLive.Provisioning.Organization::TryCreateCleanupBackupQueueItem`
- size: `183`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x187c0`

## callees

- `0x18eb0`

## string_xrefs

- `0x18f1f`: `Call to TryCreateCleanupBackupQueueItem for Organization: {0}, failed with exception: {1}`
- `0x18f4f`: `Failed to create DeleteOrganizationBackup queueitem: `

## pseudocode

```c

```

## disassembly

```asm
0x18eb0  newobj   instance void [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmOrganizationBackupData::.ctor()
0x18eb5  stloc.0
0x18eb6  ldloc.0
0x18eb7  ldarg.2
0x18eb8  callvirt instance void [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmOrganizationBackupData::set_BackupPathOnShare(string)
0x18ebd  ldloc.0
0x18ebe  ldc.i4.1
0x18ebf  callvirt instance void [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmOrganizationBackupData::set_CleanupAllBackups(bool)
0x18ec4  newobj   instance void [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.QueueItem::.ctor()
0x18ec9  dup
0x18eca  ldc.i4   0x85
0x18ecf  callvirt instance void [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemBase::set_ItemType(int32)
0x18ed4  dup
0x18ed5  ldloc.0
0x18ed6  call     T0x2B00008B
0x18edb  callvirt instance void [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemBase::set_ItemData(string)
0x18ee0  dup
0x18ee1  ldarg.0
0x18ee2  callvirt instance void [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemBase::set_OrganizationId(valuetype [mscorlib]System.Guid)
0x18ee7  dup
0x18ee8  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x18eed  stloc.2
0x18eee  ldloca.s 2
0x18ef0  ldc.r8   90.0
0x18ef9  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::AddDays(float64)
0x18efe  callvirt instance void [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemBase::set_StartTime(valuetype [mscorlib]System.DateTime)
0x18f03  dup
0x18f04  ldarg.1
0x18f05  callvirt instance void [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemBase::set_ScaleGroupId(valuetype [mscorlib]System.Guid)
0x18f0a  stloc.1
0x18f0b  call     class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemRequest [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemRequest::NewRequest()
0x18f10  ldloc.1
0x18f11  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemRequest::CreateReady(class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemBase)
0x18f16  pop
0x18f17  leave.s  loc_18F66
0x18f19  stloc.3
0x18f1a  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x18f1f  ldstr    aCallToTrycreat// "Call to TryCreateCleanupBackupQueueItem"...
0x18f24  ldc.i4.2
0x18f25  newarr   [mscorlib]System.Object
0x18f2a  dup
0x18f2b  ldc.i4.0
0x18f2c  ldarg.0
0x18f2d  box      [mscorlib]System.Guid
0x18f32  stelem.ref
0x18f33  dup
0x18f34  ldc.i4.1
0x18f35  ldloc.3
0x18f36  stelem.ref
0x18f37  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x18f3c  stloc.s  4
0x18f3e  ldloc.3
0x18f3f  ldarg.0
0x18f40  ldc.i4.s 0xA
0x18f42  ldloc.s  4
0x18f44  ldc.i4.0
0x18f45  newarr   [mscorlib]System.Object
0x18f4a  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x18f4f  ldstr    aFailedToCreate_0// "Failed to create DeleteOrganizationBack"...
0x18f54  ldloc.3
0x18f55  callvirt instance string [mscorlib]System.Object::ToString()
0x18f5a  call     string [mscorlib]System.String::Concat(string, string)
0x18f5f  call     void [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Provisioning.ProvisioningTaskLogger::LogLine(string)
0x18f64  leave.s  loc_18F66
0x18f66  ret
```
