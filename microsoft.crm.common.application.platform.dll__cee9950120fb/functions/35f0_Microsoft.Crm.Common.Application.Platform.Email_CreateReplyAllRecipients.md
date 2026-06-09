# Microsoft.Crm.Common.Application.Platform.Email::CreateReplyAllRecipients

- ea: `0x35f0`
- end: `0x366c`
- name: `Microsoft.Crm.Common.Application.Platform.Email::CreateReplyAllRecipients`
- size: `124`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x3810`

## callees

- `0x3670`
- `0x36f0`

## pseudocode

```c

```

## disassembly

```asm
0x35f0  newobj   instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ApplicationEntityCollection::.ctor()
0x35f5  stloc.0
0x35f6  ldarg.0
0x35f7  ldstr    aFrom// "from"
0x35fc  call     instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x3601  isinst   [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ApplicationEntityCollection
0x3606  ldloc.0
0x3607  ldc.i4.0
0x3608  call     void Microsoft.Crm.Common.Application.Platform.Email::AppendParties(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ApplicationEntityCollection oldParty, class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ApplicationEntityCollection newParty, bool ignoreCurrentUser)
0x360d  ldarg.0
0x360e  ldstr    aTo// "to"
0x3613  call     instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x3618  isinst   [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ApplicationEntityCollection
0x361d  ldloc.0
0x361e  ldc.i4.1
0x361f  call     void Microsoft.Crm.Common.Application.Platform.Email::AppendParties(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ApplicationEntityCollection oldParty, class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ApplicationEntityCollection newParty, bool ignoreCurrentUser)
0x3624  newobj   instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ApplicationEntityCollection::.ctor()
0x3629  stloc.1
0x362a  ldarg.0
0x362b  ldstr    aCc// "cc"
0x3630  call     instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x3635  isinst   [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ApplicationEntityCollection
0x363a  ldloc.1
0x363b  ldc.i4.1
0x363c  call     void Microsoft.Crm.Common.Application.Platform.Email::AppendParties(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ApplicationEntityCollection oldParty, class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ApplicationEntityCollection newParty, bool ignoreCurrentUser)
0x3641  ldarg.0
0x3642  ldstr    aTo// "to"
0x3647  ldloc.0
0x3648  call     instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Item(string, object)
0x364d  ldarg.0
0x364e  ldstr    aCc// "cc"
0x3653  ldloc.1
0x3654  call     instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Item(string, object)
0x3659  ldarg.0
0x365a  ldstr    aBcc// "bcc"
0x365f  ldnull
0x3660  call     instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Item(string, object)
0x3665  ldarg.0
0x3666  call     instance void Microsoft.Crm.Common.Application.Platform.Email::SetCurrentUserAsSender()
0x366b  ret
```
