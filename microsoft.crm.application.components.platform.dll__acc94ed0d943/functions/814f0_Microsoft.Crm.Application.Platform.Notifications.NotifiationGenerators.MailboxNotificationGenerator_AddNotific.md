# Microsoft.Crm.Application.Platform.Notifications.NotifiationGenerators.MailboxNotificationGenerator::AddNotificationsForProcessingState

- ea: `0x814f0`
- end: `0x815fe`
- name: `Microsoft.Crm.Application.Platform.Notifications.NotifiationGenerators.MailboxNotificationGenerator::AddNotificationsForProcessingState`
- size: `270`
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
- `0x814f0`

## string_xrefs

- `0x8152c`: `incomingemaildeliverymethod`
- `0x81539`: `incomingemaildeliverymethod`
- `0x8150c`: `testemailconfigurationscheduled`
- `0x81519`: `testemailconfigurationscheduled`
- `0x814f1`: `enabledforincomingemail`
- `0x81574`: `enabledforincomingemail`
- `0x815ca`: `Web.Email.Mailbox.Notification.MailboxIsDisabledForIncoming`

## pseudocode

```c

```

## disassembly

```asm
0x814f0  ldarg.1
0x814f1  ldstr    aEnabledforinco// "enabledforincomingemail"
0x814f6  callvirt instance object Microsoft.Crm.Application.Platform.EntityBase::get_Item(string name)
0x814fb  brfalse.s loc_8150A
0x814fd  ldarg.1
0x814fe  ldstr    aEnabledforoutg// "enabledforoutgoingemail"
0x81503  callvirt instance object Microsoft.Crm.Application.Platform.EntityBase::get_Item(string name)
0x81508  brtrue.s loc_8150B
0x8150a  ret
0x8150b  ldarg.1
0x8150c  ldstr    aTestemailconfi// "testemailconfigurationscheduled"
0x81511  callvirt instance object Microsoft.Crm.Application.Platform.EntityBase::get_Item(string name)
0x81516  brfalse.s loc_8152B
0x81518  ldarg.1
0x81519  ldstr    aTestemailconfi// "testemailconfigurationscheduled"
0x8151e  callvirt instance object Microsoft.Crm.Application.Platform.EntityBase::get_Item(string name)
0x81523  unbox.any [mscorlib]System.Boolean
0x81528  brfalse.s loc_8152B
0x8152a  ret
0x8152b  ldarg.1
0x8152c  ldstr    aIncomingemaild// "incomingemaildeliverymethod"
0x81531  callvirt instance object Microsoft.Crm.Application.Platform.EntityBase::get_Item(string name)
0x81536  brfalse.s loc_8154D
0x81538  ldarg.1
0x81539  ldstr    aIncomingemaild// "incomingemaildeliverymethod"
0x8153e  callvirt instance object Microsoft.Crm.Application.Platform.EntityBase::get_Item(string name)
0x81543  unbox.any [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.EmailDeliveryMethod
0x81548  ldc.i4.2
0x81549  ceq
0x8154b  br.s     loc_8154E
0x8154d  ldc.i4.0
0x8154e  stloc.0
0x8154f  ldarg.1
0x81550  ldstr    aOutgoingemaild// "outgoingemaildeliverymethod"
0x81555  callvirt instance object Microsoft.Crm.Application.Platform.EntityBase::get_Item(string name)
0x8155a  brfalse.s loc_81571
0x8155c  ldarg.1
0x8155d  ldstr    aOutgoingemaild// "outgoingemaildeliverymethod"
0x81562  callvirt instance object Microsoft.Crm.Application.Platform.EntityBase::get_Item(string name)
0x81567  unbox.any [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.EmailDeliveryMethod
0x8156c  ldc.i4.2
0x8156d  ceq
0x8156f  br.s     loc_81572
0x81571  ldc.i4.0
0x81572  stloc.1
0x81573  ldarg.1
0x81574  ldstr    aEnabledforinco// "enabledforincomingemail"
0x81579  callvirt instance object Microsoft.Crm.Application.Platform.EntityBase::get_Item(string name)
0x8157e  unbox.any [mscorlib]System.Boolean
0x81583  ldc.i4.0
0x81584  ceq
0x81586  ldloc.0
0x81587  and
0x81588  stloc.2
0x81589  ldarg.1
0x8158a  ldstr    aEnabledforoutg// "enabledforoutgoingemail"
0x8158f  callvirt instance object Microsoft.Crm.Application.Platform.EntityBase::get_Item(string name)
0x81594  unbox.any [mscorlib]System.Boolean
0x81599  ldc.i4.0
0x8159a  ceq
0x8159c  ldloc.1
0x8159d  and
0x8159e  stloc.3
0x8159f  ldloc.2
0x815a0  ldloc.3
0x815a1  and
0x815a2  brfalse.s loc_815C0
0x815a4  ldarg.2
0x815a5  ldc.i4.2
0x815a6  call     class Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x815ab  ldstr    aWebEmailMailbo_4// "Web.Email.Mailbox.Notification.MailboxI"...
0x815b0  callvirt instance string Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string name)
0x815b5  call     class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.Platform.Notifications.Notification [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.Platform.Notifications.Notification::CreateNotification(int32, string)
0x815ba  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.Platform.Notifications.Notification>::Add(var<u1>)
0x815bf  ret
0x815c0  ldloc.2
0x815c1  brfalse.s loc_815DF
0x815c3  ldarg.2
0x815c4  ldc.i4.2
0x815c5  call     class Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x815ca  ldstr    aWebEmailMailbo_5// "Web.Email.Mailbox.Notification.MailboxI"...
0x815cf  callvirt instance string Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string name)
0x815d4  call     class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.Platform.Notifications.Notification [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.Platform.Notifications.Notification::CreateNotification(int32, string)
0x815d9  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.Platform.Notifications.Notification>::Add(var<u1>)
0x815de  ret
0x815df  ldloc.3
0x815e0  brfalse.s loc_815FD
0x815e2  ldarg.2
0x815e3  ldc.i4.2
0x815e4  call     class Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x815e9  ldstr    aWebEmailMailbo_6// "Web.Email.Mailbox.Notification.MailboxI"...
0x815ee  callvirt instance string Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string name)
0x815f3  call     class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.Platform.Notifications.Notification [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.Platform.Notifications.Notification::CreateNotification(int32, string)
0x815f8  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.Platform.Notifications.Notification>::Add(var<u1>)
0x815fd  ret
```
