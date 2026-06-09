# TestExchangeIncomingEmailProvider::SetInitialState

- ea: `0x83990`
- end: `0x839f9`
- name: `TestExchangeIncomingEmailProvider::SetInitialState`
- size: `105`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callees

- `0x31f20`
- `0x32980`
- `0x35770`
- `0x71d00`
- `0x71e00`
- `0x71ea0`
- `0x71f30`
- `0x83990`

## string_xrefs

- `0x839c0`: `postponetestemailconfigurationuntil`
- `0x839de`: `postponetestemailconfigurationuntil`

## pseudocode

```c

```

## disassembly

```asm
0x83990  ldarg.0
0x83991  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailState Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailProviderBase::get_Mailbox()
0x83996  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.Mailbox Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailState::get_InternalMailbox()
0x8399b  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x839a0  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.Mailbox::set_LastSyncStartedOnForACT(valuetype [mscorlib]System.DateTime value)
0x839a5  ldarg.0
0x839a6  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailState Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailProviderBase::get_Mailbox()
0x839ab  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.Mailbox Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailState::get_InternalMailbox()
0x839b0  ldarg.0
0x839b1  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailState Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailProviderBase::get_Mailbox()
0x839b6  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.Mailbox Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailState::get_InternalMailbox()
0x839bb  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity Microsoft.Crm.Asynchronous.EmailConnector.Mailbox::get_InternalEntity()
0x839c0  ldstr    aPostponetestem// "postponetestemailconfigurationuntil"
0x839c5  callvirt instance bool [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::Contains(string)
0x839ca  brtrue.s loc_839D3
0x839cc  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x839d1  br.s     loc_839ED
0x839d3  ldarg.0
0x839d4  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailState Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailProviderBase::get_Mailbox()
0x839d9  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.Mailbox Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailState::get_InternalMailbox()
0x839de  ldstr    aPostponetestem// "postponetestemailconfigurationuntil"
0x839e3  callvirt instance object Microsoft.Crm.Asynchronous.EmailConnector.Mailbox::get_Item(string attributeName)
0x839e8  unbox.any [mscorlib]System.DateTime
0x839ed  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.Mailbox::set_MailboxProcessingScheduledOnForEC(valuetype [mscorlib]System.DateTime value)
0x839f2  ldarg.0
0x839f3  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProvider::SetInitialState()
0x839f8  ret
```
