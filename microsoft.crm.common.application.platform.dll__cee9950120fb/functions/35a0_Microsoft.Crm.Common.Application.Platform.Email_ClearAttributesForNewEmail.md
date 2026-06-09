# Microsoft.Crm.Common.Application.Platform.Email::ClearAttributesForNewEmail

- ea: `0x35a0`
- end: `0x35ec`
- name: `Microsoft.Crm.Common.Application.Platform.Email::ClearAttributesForNewEmail`
- size: `76`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x3530`
- `0x3670`

## callees

- `0x35a0`

## string_xrefs

- `0x35c2`: `ispartydeleted`
- `0x35cf`: `ispartydeleted`

## pseudocode

```c

```

## disassembly

```asm
0x35a0  ldarg.0
0x35a1  ldstr    aActivityid// "activityid"
0x35a6  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::ClearAttribute(string)
0x35ab  ldarg.0
0x35ac  ldstr    aActivitypartyi// "activitypartyid"
0x35b1  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::ClearAttribute(string)
0x35b6  ldarg.0
0x35b7  ldstr    aExchangeentryi// "exchangeentryid"
0x35bc  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::ClearAttribute(string)
0x35c1  ldarg.0
0x35c2  ldstr    aIspartydeleted// "ispartydeleted"
0x35c7  callvirt instance bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::HasAttribute(string)
0x35cc  brfalse.s loc_35EB
0x35ce  ldarg.0
0x35cf  ldstr    aIspartydeleted// "ispartydeleted"
0x35d4  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x35d9  unbox.any [mscorlib]System.Boolean
0x35de  brfalse.s loc_35EB
0x35e0  ldarg.0
0x35e1  ldstr    aPartyid// "partyid"
0x35e6  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::ClearAttribute(string)
0x35eb  ret
```
