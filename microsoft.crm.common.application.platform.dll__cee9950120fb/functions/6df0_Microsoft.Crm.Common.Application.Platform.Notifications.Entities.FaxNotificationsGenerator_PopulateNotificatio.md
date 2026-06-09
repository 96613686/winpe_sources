# Microsoft.Crm.Common.Application.Platform.Notifications.Entities.FaxNotificationsGenerator::PopulateNotificationGenerators

- ea: `0x6df0`
- end: `0x6e01`
- name: `Microsoft.Crm.Common.Application.Platform.Notifications.Entities.FaxNotificationsGenerator::PopulateNotificationGenerators`
- size: `17`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x6d70`

## pseudocode

```c

```

## disassembly

```asm
0x6df0  ldarg.0
0x6df1  call     instance class [mscorlib]System.Collections.Generic.IList`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Notifications.NotifiationGenerators.NotificationGenerator> [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Notifications.Entities.EntityNotificationsGenerator::get_NotificationGenerators()
0x6df6  newobj   instance void Microsoft.Crm.Common.Application.Platform.Notifications.NotifiationGenerators.FaxRecipientNotificationGenerator::.ctor()
0x6dfb  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Notifications.NotifiationGenerators.NotificationGenerator>::Add(var<u1>)
0x6e00  ret
```
