# Microsoft.Crm.Common.Application.Platform.Notifications.NotifiationGenerators.FaxRecipientNotificationGenerator::AddNotificationIfNecessary

- ea: `0x6ca0`
- end: `0x6d70`
- name: `Microsoft.Crm.Common.Application.Platform.Notifications.NotifiationGenerators.FaxRecipientNotificationGenerator::AddNotificationIfNecessary`
- size: `208`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x2a20`
- `0x4130`
- `0x6ca0`

## pseudocode

```c

```

## disassembly

```asm
0x6ca0  call     bool [Microsoft.Crm]Microsoft.Crm.CoverPages::GetFaxSupported()
0x6ca5  brtrue.s loc_6CA8
0x6ca7  ret
0x6ca8  ldarg.1
0x6ca9  callvirt instance bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_IsNew()
0x6cae  brfalse.s loc_6CB1
0x6cb0  ret
0x6cb1  ldarg.1
0x6cb2  ldstr    aStatecode// "statecode"
0x6cb7  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x6cbc  isinst   [mscorlib]System.String
0x6cc1  ldc.i4.0
0x6cc2  stloc.1
0x6cc3  ldloca.s 1
0x6cc5  constrained. [Microsoft.Crm.Sdk.Reserved]Microsoft.Crm.Sdk.Types.FaxState
0x6ccb  callvirt instance string [mscorlib]System.Object::ToString()
0x6cd0  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x6cd5  brfalse.s loc_6CD8
0x6cd7  ret
0x6cd8  ldarg.1
0x6cd9  ldstr    aDirectioncode// "directioncode"
0x6cde  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x6ce3  brfalse.s loc_6CF8
0x6ce5  ldarg.1
0x6ce6  ldstr    aDirectioncode// "directioncode"
0x6ceb  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x6cf0  unbox.any [mscorlib]System.Boolean
0x6cf5  brtrue.s loc_6CF8
0x6cf7  ret
0x6cf8  ldarg.1
0x6cf9  isinst   Microsoft.Crm.Common.Application.Platform.ActivityBase
0x6cfe  stloc.0
0x6cff  ldloc.0
0x6d00  brtrue.s loc_6D03
0x6d02  ret
0x6d03  ldloc.0
0x6d04  callvirt instance valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.PartyStatusType Microsoft.Crm.Common.Application.Platform.ActivityBase::GetRecipientsStatuses()
0x6d09  ldc.i4.4
0x6d0a  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.General::CheckBit(unsigned int32, unsigned int32)
0x6d0f  brfalse.s loc_6D2E
0x6d11  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x6d16  ldstr    aFaxErrorFaxsen// "Fax_Error_FaxSendBlocked"
0x6d1b  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x6d20  stloc.2
0x6d21  ldarg.2
0x6d22  ldc.i4.1
0x6d23  ldloc.2
0x6d24  newobj   instance void [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.Platform.Notifications.Notification::.ctor(int32, string)
0x6d29  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.Platform.Notifications.Notification>::Add(var<u1>)
0x6d2e  ldarg.1
0x6d2f  castclass Microsoft.Crm.Common.Application.Platform.Fax
0x6d34  callvirt instance bool Microsoft.Crm.Common.Application.Platform.Fax::HasRecipients()
0x6d39  brfalse.s loc_6D6F
0x6d3b  ldarg.1
0x6d3c  ldstr    aFaxnumber// "faxnumber"
0x6d41  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x6d46  castclass [mscorlib]System.String
0x6d4b  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x6d50  brfalse.s loc_6D6F
0x6d52  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x6d57  ldstr    aFaxErrorNodial// "Fax_Error_NoDialNumber"
0x6d5c  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x6d61  stloc.3
0x6d62  ldarg.2
0x6d63  ldc.i4.1
0x6d64  ldloc.3
0x6d65  newobj   instance void [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.Platform.Notifications.Notification::.ctor(int32, string)
0x6d6a  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.Platform.Notifications.Notification>::Add(var<u1>)
0x6d6f  ret
```
