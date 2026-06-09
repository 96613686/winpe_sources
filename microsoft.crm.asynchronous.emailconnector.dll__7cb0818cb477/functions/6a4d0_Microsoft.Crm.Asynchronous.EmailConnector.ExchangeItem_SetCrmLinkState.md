# Microsoft.Crm.Asynchronous.EmailConnector.ExchangeItem::SetCrmLinkState

- ea: `0x6a4d0`
- end: `0x6a521`
- name: `Microsoft.Crm.Asynchronous.EmailConnector.ExchangeItem::SetCrmLinkState`
- size: `81`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x6a2a0`
- `0x6a840`

## callees

- `0x684f0`
- `0x69840`
- `0x69950`
- `0x6a4d0`
- `0x6ab00`
- `0x700e0`
- `0x702d0`

## string_xrefs

- `0x6a4de`: `CrmLinkState`
- `0x6a4fe`: `Set the crm link state to IsLinked for the item {0} on the exchange server for the mailbox : {1}.`

## pseudocode

```c

```

## disassembly

```asm
0x6a4d0  ldarg.0
0x6a4d1  call     instance valuetype Microsoft.Crm.Asynchronous.EmailConnector.LinkState Microsoft.Crm.Asynchronous.EmailConnector.ExchangeItem::get_CrmLinkstate()
0x6a4d6  ldarg.1
0x6a4d7  beq.s    loc_6A520
0x6a4d9  call     class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExtendedPropertyDefinition> Microsoft.Crm.Asynchronous.EmailConnector.ExchangeExtendedProperties::get_ExchangePropertiesCollection()
0x6a4de  ldstr    aCrmlinkstate_0// "CrmLinkState"
0x6a4e3  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExtendedPropertyDefinition>::get_Item(void)
0x6a4e8  stloc.0
0x6a4e9  ldarg.0
0x6a4ea  call     instance class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.Item Microsoft.Crm.Asynchronous.EmailConnector.ExchangeItem::get_Item()
0x6a4ef  ldloc.0
0x6a4f0  ldarg.1
0x6a4f1  conv.r8
0x6a4f2  box      [mscorlib]System.Double
0x6a4f7  callvirt instance void [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.Item::SetExtendedProperty(class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExtendedPropertyDefinition, object)
0x6a4fc  ldarg.0
0x6a4fd  ldc.i4.4
0x6a4fe  ldstr    aSetTheCrmLinkS// "Set the crm link state to IsLinked for "...
0x6a503  ldc.i4.2
0x6a504  newarr   [mscorlib]System.Object
0x6a509  dup
0x6a50a  ldc.i4.0
0x6a50b  ldarg.0
0x6a50c  callvirt instance string Microsoft.Crm.Asynchronous.EmailConnector.SyncItemBase::get_ToCrmId()
0x6a511  stelem.ref
0x6a512  dup
0x6a513  ldc.i4.1
0x6a514  ldarg.0
0x6a515  call     instance string Microsoft.Crm.Asynchronous.EmailConnector.SyncItemBase::get_MailboxId()
0x6a51a  stelem.ref
0x6a51b  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeItem::HandleTrace(valuetype [System]System.Diagnostics.TraceLevel traceLevel, string format, object[] args)
0x6a520  ret
```
