# Microsoft.Crm.Common.Application.Platform.Email::CreateForwardRecipients

- ea: `0x39f0`
- end: `0x3a27`
- name: `Microsoft.Crm.Common.Application.Platform.Email::CreateForwardRecipients`
- size: `55`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x39c0`

## callees

- `0x36f0`

## pseudocode

```c

```

## disassembly

```asm
0x39f0  ldarg.0
0x39f1  ldstr    aFrom// "from"
0x39f6  ldnull
0x39f7  call     instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Item(string, object)
0x39fc  ldarg.0
0x39fd  ldstr    aTo// "to"
0x3a02  ldnull
0x3a03  call     instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Item(string, object)
0x3a08  ldarg.0
0x3a09  ldstr    aCc// "cc"
0x3a0e  ldnull
0x3a0f  call     instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Item(string, object)
0x3a14  ldarg.0
0x3a15  ldstr    aBcc// "bcc"
0x3a1a  ldnull
0x3a1b  call     instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Item(string, object)
0x3a20  ldarg.0
0x3a21  call     instance void Microsoft.Crm.Common.Application.Platform.Email::SetCurrentUserAsSender()
0x3a26  ret
```
