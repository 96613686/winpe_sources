# Microsoft.Crm.Application.Platform.Notifications.NotifiationGenerators.ServerSideSyncFcbNotificationGenerator::AddNotificationForFcbCheck

- ea: `0x82270`
- end: `0x822e2`
- name: `Microsoft.Crm.Application.Platform.Notifications.NotifiationGenerators.ServerSideSyncFcbNotificationGenerator::AddNotificationForFcbCheck`
- size: `114`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x80b80`
- `0x818e0`
- `0x82260`

## callees

- `0x11760`
- `0x30260`
- `0x81d90`
- `0x82270`

## string_xrefs

- `0x822ae`: `Web.Email.ServerSideSync.Notification.ActivityQueueAndMailboxQueueFcbTurnedOff`
- `0x822cd`: `Web.Email.ServerSideSync.Notification.ActivityQueueFcbTurnedOff`

## pseudocode

```c

```

## disassembly

```asm
0x82270  call     class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl [Microsoft.Crm.Core]Microsoft.Crm.FeatureControl::get_Current()
0x82275  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl::get_Features()
0x8227a  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer::get_ActivityQueue()
0x8227f  ldarg.0
0x82280  call     instance class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext Microsoft.Crm.Application.Platform.Notifications.NotifiationGenerators.NotificationGenerator::get_Context()
0x82285  call     bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.FeatureEnabledHelper::IsNonOrgFeatureEnabled(class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x8228a  stloc.0
0x8228b  call     class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl [Microsoft.Crm.Core]Microsoft.Crm.FeatureControl::get_Current()
0x82290  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl::get_Features()
0x82295  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer::get_MailboxQueue()
0x8229a  ldarg.0
0x8229b  call     instance class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext Microsoft.Crm.Application.Platform.Notifications.NotifiationGenerators.NotificationGenerator::get_Context()
0x822a0  call     bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.FeatureEnabledHelper::IsNonOrgFeatureEnabled(class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x822a5  brtrue.s loc_822C3
0x822a7  ldarg.1
0x822a8  ldc.i4.2
0x822a9  call     class Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x822ae  ldstr    aWebEmailServer// "Web.Email.ServerSideSync.Notification.A"...
0x822b3  callvirt instance string Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string name)
0x822b8  call     class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.Platform.Notifications.Notification [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.Platform.Notifications.Notification::CreateNotification(int32, string)
0x822bd  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.Platform.Notifications.Notification>::Add(var<u1>)
0x822c2  ret
0x822c3  ldloc.0
0x822c4  brtrue.s loc_822E1
0x822c6  ldarg.1
0x822c7  ldc.i4.2
0x822c8  call     class Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x822cd  ldstr    aWebEmailServer_0// "Web.Email.ServerSideSync.Notification.A"...
0x822d2  callvirt instance string Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string name)
0x822d7  call     class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.Platform.Notifications.Notification [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.Platform.Notifications.Notification::CreateNotification(int32, string)
0x822dc  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.Platform.Notifications.Notification>::Add(var<u1>)
0x822e1  ret
```
