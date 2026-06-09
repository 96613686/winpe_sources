# Microsoft.Crm.Application.Platform.Notifications.NotifiationGenerators.MailboxNotificationGenerator::AddNotificationsForTestConfiguration

- ea: `0x81480`
- end: `0x814ef`
- name: `Microsoft.Crm.Application.Platform.Notifications.NotifiationGenerators.MailboxNotificationGenerator::AddNotificationsForTestConfiguration`
- size: `111`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x811d0`

## callees

- `0x11760`
- `0x30260`
- `0x5be20`
- `0x81480`

## string_xrefs

- `0x81481`: `testemailconfigurationscheduled`
- `0x8148f`: `testemailconfigurationscheduled`
- `0x814be`: `Web.Email.Mailbox.Notification.TestAccessInProgress`
- `0x814da`: `Web.Email.Mailbox.Notification.TestAccessScheduled`

## pseudocode

```c

```

## disassembly

```asm
0x81480  ldarg.1
0x81481  ldstr    aTestemailconfi// "testemailconfigurationscheduled"
0x81486  callvirt instance object Microsoft.Crm.Application.Platform.EntityBase::get_Item(string name)
0x8148b  brtrue.s loc_8148E
0x8148d  ret
0x8148e  ldarg.1
0x8148f  ldstr    aTestemailconfi// "testemailconfigurationscheduled"
0x81494  callvirt instance object Microsoft.Crm.Application.Platform.EntityBase::get_Item(string name)
0x81499  unbox.any [mscorlib]System.Boolean
0x8149e  brfalse.s loc_814EE
0x814a0  ldarg.1
0x814a1  ldstr    aHostid// "hostid"
0x814a6  callvirt instance object Microsoft.Crm.Application.Platform.EntityBase::get_Item(string name)
0x814ab  castclass [mscorlib]System.String
0x814b0  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x814b5  brtrue.s loc_814D3
0x814b7  ldarg.2
0x814b8  ldc.i4.3
0x814b9  call     class Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x814be  ldstr    aWebEmailMailbo_2// "Web.Email.Mailbox.Notification.TestAcce"...
0x814c3  callvirt instance string Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string name)
0x814c8  call     class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.Platform.Notifications.Notification [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.Platform.Notifications.Notification::CreateNotification(int32, string)
0x814cd  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.Platform.Notifications.Notification>::Add(var<u1>)
0x814d2  ret
0x814d3  ldarg.2
0x814d4  ldc.i4.3
0x814d5  call     class Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x814da  ldstr    aWebEmailMailbo_3// "Web.Email.Mailbox.Notification.TestAcce"...
0x814df  callvirt instance string Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string name)
0x814e4  call     class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.Platform.Notifications.Notification [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.Platform.Notifications.Notification::CreateNotification(int32, string)
0x814e9  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.Platform.Notifications.Notification>::Add(var<u1>)
0x814ee  ret
```
