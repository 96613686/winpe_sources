# Microsoft.Crm.Common.Application.Platform.Notifications.Entities.LetterNotificationsGenerator::PopulateNotificationGenerators

- ea: `0x6e30`
- end: `0x6e41`
- name: `Microsoft.Crm.Common.Application.Platform.Notifications.Entities.LetterNotificationsGenerator::PopulateNotificationGenerators`
- size: `17`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x6dd0`

## pseudocode

```c

```

## disassembly

```asm
0x6e30  ldarg.0
0x6e31  call     instance class [mscorlib]System.Collections.Generic.IList`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Notifications.NotifiationGenerators.NotificationGenerator> [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Notifications.Entities.EntityNotificationsGenerator::get_NotificationGenerators()
0x6e36  newobj   instance void Microsoft.Crm.Common.Application.Platform.Notifications.NotifiationGenerators.LetterSendBlockedNotificationGenerator::.ctor()
0x6e3b  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Notifications.NotifiationGenerators.NotificationGenerator>::Add(var<u1>)
0x6e40  ret
```
