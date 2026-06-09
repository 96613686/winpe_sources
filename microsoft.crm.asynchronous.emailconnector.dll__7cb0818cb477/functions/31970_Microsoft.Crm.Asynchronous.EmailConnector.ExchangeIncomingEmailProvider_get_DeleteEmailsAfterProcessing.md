# Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProvider::get_DeleteEmailsAfterProcessing

- ea: `0x31970`
- end: `0x3199a`
- name: `Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProvider::get_DeleteEmailsAfterProcessing`
- size: `42`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x31970`
- `0x32970`
- `0x35770`

## string_xrefs

- `0x31976`: `processanddeleteemails`
- `0x31988`: `processanddeleteemails`

## pseudocode

```c

```

## disassembly

```asm
0x31970  ldarg.0
0x31971  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailState Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailProviderBase::get_Mailbox()
0x31976  ldstr    aProcessanddele// "processanddeleteemails"
0x3197b  callvirt instance object Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailState::get_Item(string attributeName)
0x31980  brfalse.s loc_31998
0x31982  ldarg.0
0x31983  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailState Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailProviderBase::get_Mailbox()
0x31988  ldstr    aProcessanddele// "processanddeleteemails"
0x3198d  callvirt instance object Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailState::get_Item(string attributeName)
0x31992  unbox.any [mscorlib]System.Boolean
0x31997  ret
0x31998  ldc.i4.0
0x31999  ret
```
