# Microsoft.Crm.Common.Application.Platform.Email::SetParentActivityIdAndClearCorrelationFields

- ea: `0x34b0`
- end: `0x3522`
- name: `Microsoft.Crm.Common.Application.Platform.Email::SetParentActivityIdAndClearCorrelationFields`
- size: `114`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x3790`
- `0x3810`
- `0x3890`

## callees

- `0x34b0`

## pseudocode

```c

```

## disassembly

```asm
0x34b0  ldarg.0
0x34b1  ldstr    aParentactivity// "parentactivityid"
0x34b6  ldarg.1
0x34b7  box      [mscorlib]System.Guid
0x34bc  call     instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Item(string, object)
0x34c1  ldarg.0
0x34c2  ldstr    aMessageid// "messageid"
0x34c7  call     instance bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::HasAttribute(string)
0x34cc  brfalse.s loc_34D9
0x34ce  ldarg.0
0x34cf  ldstr    aMessageid// "messageid"
0x34d4  call     instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::ClearAttribute(string)
0x34d9  ldarg.0
0x34da  ldstr    aInreplyto// "inreplyto"
0x34df  call     instance bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::HasAttribute(string)
0x34e4  brfalse.s loc_34F1
0x34e6  ldarg.0
0x34e7  ldstr    aInreplyto// "inreplyto"
0x34ec  call     instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::ClearAttribute(string)
0x34f1  ldarg.0
0x34f2  ldstr    aConversationin// "conversationindex"
0x34f7  call     instance bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::HasAttribute(string)
0x34fc  brfalse.s loc_3509
0x34fe  ldarg.0
0x34ff  ldstr    aConversationin// "conversationindex"
0x3504  call     instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::ClearAttribute(string)
0x3509  ldarg.0
0x350a  ldstr    aBaseconversati// "baseconversationindexhash"
0x350f  call     instance bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::HasAttribute(string)
0x3514  brfalse.s loc_3521
0x3516  ldarg.0
0x3517  ldstr    aBaseconversati// "baseconversationindexhash"
0x351c  call     instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::ClearAttribute(string)
0x3521  ret
```
