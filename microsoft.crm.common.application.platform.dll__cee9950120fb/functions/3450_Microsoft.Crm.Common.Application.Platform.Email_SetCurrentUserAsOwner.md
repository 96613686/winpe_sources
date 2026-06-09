# Microsoft.Crm.Common.Application.Platform.Email::SetCurrentUserAsOwner

- ea: `0x3450`
- end: `0x34a2`
- name: `Microsoft.Crm.Common.Application.Platform.Email::SetCurrentUserAsOwner`
- size: `82`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x3320`

## pseudocode

```c

```

## disassembly

```asm
0x3450  ldarg.0
0x3451  ldstr    aOwnerid// "ownerid"
0x3456  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::get_Current()
0x345b  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser::get_SystemUserId()
0x3460  box      [mscorlib]System.Guid
0x3465  call     instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Item(string, object)
0x346a  ldarg.0
0x346b  ldstr    aOwneridname// "owneridname"
0x3470  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::get_Current()
0x3475  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser::get_UserName()
0x347a  call     instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Item(string, object)
0x347f  ldarg.0
0x3480  ldstr    aOwneriddsc// "owneriddsc"
0x3485  ldc.i4.0
0x3486  box      [mscorlib]System.Int32
0x348b  call     instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Item(string, object)
0x3490  ldarg.0
0x3491  ldstr    aOwneridtype// "owneridtype"
0x3496  ldc.i4.8
0x3497  box      [mscorlib]System.Int32
0x349c  call     instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Item(string, object)
0x34a1  ret
```
