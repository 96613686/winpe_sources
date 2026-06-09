# Microsoft.Crm.Common.Application.Platform.Email::PrePopulatePartyToCurrentUser

- ea: `0x32d0`
- end: `0x32f7`
- name: `Microsoft.Crm.Common.Application.Platform.Email::PrePopulatePartyToCurrentUser`
- size: `39`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x2780`

## pseudocode

```c

```

## disassembly

```asm
0x32d0  ldarg.0
0x32d1  ldarg.1
0x32d2  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::get_Current()
0x32d7  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser::get_SystemUserId()
0x32dc  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::GuidToString(valuetype [mscorlib]System.Guid)
0x32e1  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::get_Current()
0x32e6  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser::get_UserName()
0x32eb  ldc.i4.8
0x32ec  ldstr    aEmailAddress// "EMAIL_ADDRESS"
0x32f1  call     instance void Microsoft.Crm.Common.Application.Platform.ActivityBase::PrePopulateParty(string participationTypeName, string partyId, string partyIdName, int32 partyIdTypeCode, string addressUsed)
0x32f6  ret
```
