# Microsoft.Crm.Common.Application.Platform.ActivityBase::PrePopulatePartyToCurrentUser

- ea: `0x2850`
- end: `0x287c`
- name: `Microsoft.Crm.Common.Application.Platform.ActivityBase::PrePopulatePartyToCurrentUser`
- size: `44`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x31b0`
- `0x3fe0`
- `0x4170`
- `0x4aa0`

## callees

- `0x2780`

## pseudocode

```c

```

## disassembly

```asm
0x2850  ldarg.0
0x2851  ldarg.1
0x2852  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::get_Current()
0x2857  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser::get_SystemUserId()
0x285c  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::GuidToString(valuetype [mscorlib]System.Guid)
0x2861  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::get_Current()
0x2866  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser::get_UserName()
0x286b  ldc.i4.8
0x286c  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::get_Current()
0x2871  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser::get_EmailAddress()
0x2876  call     instance void Microsoft.Crm.Common.Application.Platform.ActivityBase::PrePopulateParty(string participationTypeName, string partyId, string partyIdName, int32 partyIdTypeCode, string addressUsed)
0x287b  ret
```
