# Microsoft.Crm.Common.Application.Platform.Email::VerifyPartiesForSend

- ea: `0x3ea0`
- end: `0x3f0c`
- name: `Microsoft.Crm.Common.Application.Platform.Email::VerifyPartiesForSend`
- size: `108`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x3e30`

## callees

- `0x2a20`
- `0x3300`
- `0x3ea0`

## pseudocode

```c

```

## disassembly

```asm
0x3ea0  ldarg.0
0x3ea1  call     instance valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.PartyStatusType Microsoft.Crm.Common.Application.Platform.Email::get_SenderStatus()
0x3ea6  stloc.0
0x3ea7  ldloc.0
0x3ea8  ldc.i4.2
0x3ea9  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.General::CheckBit(unsigned int32, unsigned int32)
0x3eae  brtrue.s loc_3EB9
0x3eb0  ldloc.0
0x3eb1  ldc.i4.1
0x3eb2  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.General::CheckBit(unsigned int32, unsigned int32)
0x3eb7  brfalse.s loc_3EBB
0x3eb9  ldc.i4.0
0x3eba  ret
0x3ebb  ldarg.0
0x3ebc  callvirt instance valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.PartyStatusType Microsoft.Crm.Common.Application.Platform.ActivityBase::GetRecipientsStatuses()
0x3ec1  stloc.0
0x3ec2  ldarg.0
0x3ec3  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_EntityType()
0x3ec8  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::get_Context()
0x3ecd  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.Organization::GetSettings(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x3ed2  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings::get_IsUnresolvedPartiesOnEmailSendAllowed()
0x3ed7  brfalse.s loc_3EED
0x3ed9  ldloc.0
0x3eda  ldc.i4.1
0x3edb  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.General::CheckBit(unsigned int32, unsigned int32)
0x3ee0  brtrue.s loc_3EEB
0x3ee2  ldloc.0
0x3ee3  ldc.i4.4
0x3ee4  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.General::CheckBit(unsigned int32, unsigned int32)
0x3ee9  brfalse.s loc_3F0A
0x3eeb  ldc.i4.0
0x3eec  ret
0x3eed  ldloc.0
0x3eee  ldc.i4.2
0x3eef  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.General::CheckBit(unsigned int32, unsigned int32)
0x3ef4  brtrue.s loc_3F08
0x3ef6  ldloc.0
0x3ef7  ldc.i4.1
0x3ef8  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.General::CheckBit(unsigned int32, unsigned int32)
0x3efd  brtrue.s loc_3F08
0x3eff  ldloc.0
0x3f00  ldc.i4.4
0x3f01  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.General::CheckBit(unsigned int32, unsigned int32)
0x3f06  brfalse.s loc_3F0A
0x3f08  ldc.i4.0
0x3f09  ret
0x3f0a  ldc.i4.1
0x3f0b  ret
```
