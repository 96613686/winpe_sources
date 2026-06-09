# Microsoft.Crm.CrmLive.Provisioning.EndUserNotificationEmail::Execute

- ea: `0x71f0`
- end: `0x725b`
- name: `Microsoft.Crm.CrmLive.Provisioning.EndUserNotificationEmail::Execute`
- size: `107`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x71f0`
- `0x7260`
- `0x7380`

## string_xrefs

- `0x7223`: `Template with Organization Summary for MS Online StorageLimitReachedThreshold`
- `0x7235`: `Template with Organization Summary for MS Online StorageLimitExceeded`

## pseudocode

```c

```

## disassembly

```asm
0x71f0  ldarg.1
0x71f1  callvirt instance class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.QueueItem [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Provisioning.QueueItemTask::get_QueueItem()
0x71f6  callvirt instance string [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemBase::get_ItemData()
0x71fb  call     class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.EmailNotificationInfo [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.EmailNotificationInfo::Deserialize(string)
0x7200  stloc.0
0x7201  newobj   instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.EndUserNotification.LocalizedUserNotificationService::.ctor()
0x7206  ldloc.0
0x7207  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.EmailNotificationInfo::get_NotificationId()
0x720c  newobj   instance void valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::.ctor(var<u1>)
0x7211  ldnull
0x7212  call     instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.EndUserNotification.LocalizedUserNotification[] [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.EndUserNotification.LocalizedUserNotificationService::Retrieve(valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>, string)
0x7217  call     T0x2B000021
0x721c  stloc.1
0x721d  ldloc.1
0x721e  callvirt instance string [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.EndUserNotification.LocalizedUserNotification::get_TemplateName()
0x7223  ldstr    aTemplateWithOr// "Template with Organization Summary for "...
0x7228  call     bool [mscorlib]System.String::op_Equality(string, string)
0x722d  brtrue.s loc_7241
0x722f  ldloc.1
0x7230  callvirt instance string [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.EndUserNotification.LocalizedUserNotification::get_TemplateName()
0x7235  ldstr    aTemplateWithOr_0// "Template with Organization Summary for "...
0x723a  call     bool [mscorlib]System.String::op_Equality(string, string)
0x723f  brfalse.s loc_7249
0x7241  ldloc.0
0x7242  call     void Microsoft.Crm.CrmLive.Provisioning.EndUserNotificationEmail::SendEmailToTenantAdmins(class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.EmailNotificationInfo info)
0x7247  br.s     loc_724F
0x7249  ldloc.0
0x724a  call     void Microsoft.Crm.CrmLive.Provisioning.EndUserNotificationEmail::SendEmailToOrganizationAdmins(class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.EmailNotificationInfo info)
0x724f  ldc.i4.4
0x7250  ldstr    aSuccess// "success"
0x7255  newobj   instance void [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Scheduling.TaskResult::.ctor(valuetype [Microsoft.Crm.Core]Microsoft.Crm.Config.Wrapper.TaskStatus, string)
0x725a  ret
```
