# Microsoft.Crm.Common.Application.Platform.Notifications.NotifiationGenerators.LetterSendBlockedNotificationGenerator::AddNotificationIfNecessary

- ea: `0x6da0`
- end: `0x6dcc`
- name: `Microsoft.Crm.Common.Application.Platform.Notifications.NotifiationGenerators.LetterSendBlockedNotificationGenerator::AddNotificationIfNecessary`
- size: `44`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x2a30`
- `0x6da0`

## pseudocode

```c

```

## disassembly

```asm
0x6da0  ldarg.1
0x6da1  call     valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.PartyStatusType Microsoft.Crm.Common.Application.Platform.ActivityBase::GetRecipientsStatusType(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity entity)
0x6da6  ldc.i4.4
0x6da7  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.General::CheckBit(unsigned int32, unsigned int32)
0x6dac  brfalse.s loc_6DCB
0x6dae  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x6db3  ldstr    aLetterErrorLet// "Letter_Error_LetterSendBlocked"
0x6db8  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x6dbd  stloc.0
0x6dbe  ldarg.2
0x6dbf  ldc.i4.1
0x6dc0  ldloc.0
0x6dc1  newobj   instance void [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.Platform.Notifications.Notification::.ctor(int32, string)
0x6dc6  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.Platform.Notifications.Notification>::Add(var<u1>)
0x6dcb  ret
```
