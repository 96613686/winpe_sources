# Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.ActionCard::SetTokenIformation

- ea: `0x129c0`
- end: `0x129d2`
- name: `Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.ActionCard::SetTokenIformation`
- size: `18`
- prototype: ``
- caller_count: `3`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x10f30`
- `0x12000`
- `0x12310`

## string_xrefs

- `0x129c6`: `referencetokens`

## pseudocode

```c

```

## disassembly

```asm
0x129c0  ldarg.0
0x129c1  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.ActionCard::_actionCard
0x129c6  ldstr    aReferencetoken// "referencetokens"
0x129cb  ldarg.1
0x129cc  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_Item(string, object)
0x129d1  ret
```
