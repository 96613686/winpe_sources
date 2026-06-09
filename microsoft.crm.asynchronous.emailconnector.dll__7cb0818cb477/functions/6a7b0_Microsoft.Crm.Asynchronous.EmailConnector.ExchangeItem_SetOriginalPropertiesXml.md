# Microsoft.Crm.Asynchronous.EmailConnector.ExchangeItem::SetOriginalPropertiesXml

- ea: `0x6a7b0`
- end: `0x6a7ec`
- name: `Microsoft.Crm.Asynchronous.EmailConnector.ExchangeItem::SetOriginalPropertiesXml`
- size: `60`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x6a2a0`

## callees

- `0x69950`
- `0x6e920`
- `0x700e0`
- `0x702d0`
- `0x70390`
- `0x704a0`

## string_xrefs

- `0x6a7b1`: `crmxml`
- `0x6a7c9`: `Set the original properties xml for the item {0} on the exchange server for the mailbox : {1}.`

## pseudocode

```c

```

## disassembly

```asm
0x6a7b0  ldarg.0
0x6a7b1  ldstr    aCrmxml// "crmxml"
0x6a7b6  ldarg.0
0x6a7b7  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.OriginalProperties Microsoft.Crm.Asynchronous.EmailConnector.SyncItemBase::get_OriginalProperties()
0x6a7bc  callvirt instance string Microsoft.Crm.Asynchronous.EmailConnector.OriginalProperties::get_Xml()
0x6a7c1  call     instance bool Microsoft.Crm.Asynchronous.EmailConnector.SyncItemBase::SetProperty(string propertyName, string propertyValue)
0x6a7c6  pop
0x6a7c7  ldarg.0
0x6a7c8  ldc.i4.4
0x6a7c9  ldstr    aSetTheOriginal// "Set the original properties xml for the"...
0x6a7ce  ldc.i4.2
0x6a7cf  newarr   [mscorlib]System.Object
0x6a7d4  dup
0x6a7d5  ldc.i4.0
0x6a7d6  ldarg.0
0x6a7d7  callvirt instance string Microsoft.Crm.Asynchronous.EmailConnector.SyncItemBase::get_ToCrmId()
0x6a7dc  stelem.ref
0x6a7dd  dup
0x6a7de  ldc.i4.1
0x6a7df  ldarg.0
0x6a7e0  call     instance string Microsoft.Crm.Asynchronous.EmailConnector.SyncItemBase::get_MailboxId()
0x6a7e5  stelem.ref
0x6a7e6  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeItem::HandleTrace(valuetype [System]System.Diagnostics.TraceLevel traceLevel, string format, object[] args)
0x6a7eb  ret
```
