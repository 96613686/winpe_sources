# Microsoft.Crm.Asynchronous.EmailConnector.UpdateExchangeItemsStep::ProcessResponse

- ea: `0x40bc0`
- end: `0x40c95`
- name: `Microsoft.Crm.Asynchronous.EmailConnector.UpdateExchangeItemsStep::ProcessResponse`
- size: `213`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `installer_update, broker_com_uri`

## callees

- `0x14090`
- `0x25060`
- `0x25110`
- `0x32980`
- `0x3ab40`
- `0x40bc0`
- `0x41be0`
- `0x41dc0`
- `0x42060`
- `0x71e60`
- `0x71e70`

## string_xrefs

- `0x40c4c`: `{0} failures found while updating crmLinkStateTracker in CrmEmailMessagesPendingLinking search folder.`

## pseudocode

```c

```

## disassembly

```asm
0x40bc0  ldarg.0
0x40bc1  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IExchangeIncomingEmailProvider Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::provider
0x40bc6  ldc.i4.s 0xA
0x40bc8  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.IExchangeIncomingEmailProvider::set_ExecutionStatus(valuetype Microsoft.Crm.Asynchronous.EmailConnector.ExecutionStatus value)
0x40bcd  ldarg.0
0x40bce  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.UpdateItemResponseType Microsoft.Crm.Asynchronous.EmailConnector.UpdateExchangeItemsStep::response
0x40bd3  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.ArrayOfResponseMessagesType Microsoft.Crm.Asynchronous.EmailConnector.BaseResponseMessageType::get_ResponseMessages()
0x40bd8  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.ResponseMessageType[] Microsoft.Crm.Asynchronous.EmailConnector.ArrayOfResponseMessagesType::get_Items()
0x40bdd  stloc.0
0x40bde  ldc.i4.0
0x40bdf  stloc.1
0x40be0  br.s     loc_40C2C
0x40be2  ldloc.0
0x40be3  ldloc.1
0x40be4  ldelem.ref
0x40be5  stloc.2
0x40be6  ldloc.2
0x40be7  callvirt instance valuetype Microsoft.Crm.Asynchronous.EmailConnector.ResponseClassType Microsoft.Crm.Asynchronous.EmailConnector.ResponseMessageType::get_ResponseClass()
0x40bec  brfalse.s loc_40C28
0x40bee  ldarg.0
0x40bef  ldc.i4.1
0x40bf0  ldstr    aFailureInMovin_0// "Failure in moving the email to Search f"...
0x40bf5  ldc.i4.1
0x40bf6  newarr   [mscorlib]System.Object
0x40bfb  dup
0x40bfc  ldc.i4.0
0x40bfd  ldloc.2
0x40bfe  call     T0x2B000070
0x40c03  stelem.ref
0x40c04  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::HandleTrace(valuetype [System]System.Diagnostics.TraceLevel traceLevel, string format, object[] args)
0x40c09  ldarg.0
0x40c0a  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IExchangeIncomingEmailProvider Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::provider
0x40c0f  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailState Microsoft.Crm.Asynchronous.EmailConnector.IIncomingEmailProvider::get_Mailbox()
0x40c14  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.Mailbox Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailState::get_InternalMailbox()
0x40c19  dup
0x40c1a  callvirt instance int32 Microsoft.Crm.Asynchronous.EmailConnector.Mailbox::get_TotalFailures()
0x40c1f  ldc.i4.1
0x40c20  add
0x40c21  stloc.3
0x40c22  ldloc.3
0x40c23  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.Mailbox::set_TotalFailures(int32 value)
0x40c28  ldloc.1
0x40c29  ldc.i4.1
0x40c2a  add
0x40c2b  stloc.1
0x40c2c  ldloc.1
0x40c2d  ldloc.0
0x40c2e  ldlen
0x40c2f  conv.i4
0x40c30  blt.s    loc_40BE2
0x40c32  ldarg.0
0x40c33  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IExchangeIncomingEmailProvider Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::provider
0x40c38  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailState Microsoft.Crm.Asynchronous.EmailConnector.IIncomingEmailProvider::get_Mailbox()
0x40c3d  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.Mailbox Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailState::get_InternalMailbox()
0x40c42  callvirt instance int32 Microsoft.Crm.Asynchronous.EmailConnector.Mailbox::get_TotalFailures()
0x40c47  ldc.i4.0
0x40c48  ble.s    loc_40C7B
0x40c4a  ldarg.0
0x40c4b  ldc.i4.4
0x40c4c  ldstr    a0FailuresFound_3// "{0} failures found while updating crmLi"...
0x40c51  ldc.i4.1
0x40c52  newarr   [mscorlib]System.Object
0x40c57  dup
0x40c58  ldc.i4.0
0x40c59  ldarg.0
0x40c5a  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IExchangeIncomingEmailProvider Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::provider
0x40c5f  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailState Microsoft.Crm.Asynchronous.EmailConnector.IIncomingEmailProvider::get_Mailbox()
0x40c64  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.Mailbox Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailState::get_InternalMailbox()
0x40c69  callvirt instance int32 Microsoft.Crm.Asynchronous.EmailConnector.Mailbox::get_TotalFailures()
0x40c6e  box      [mscorlib]System.Int32
0x40c73  stelem.ref
0x40c74  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::HandleTrace(valuetype [System]System.Diagnostics.TraceLevel traceLevel, string format, object[] args)
0x40c79  br.s     loc_40C86
0x40c7b  ldarg.0
0x40c7c  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IExchangeIncomingEmailProvider Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::provider
0x40c81  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.IExchangeIncomingEmailProvider::UpdateMailboxFoldersStatus()
0x40c86  ldarg.0
0x40c87  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IExchangeIncomingEmailProvider Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::provider
0x40c8c  ldc.i4.s 0xA
0x40c8e  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.IExchangeIncomingEmailProvider::set_ExecutionStatus(valuetype Microsoft.Crm.Asynchronous.EmailConnector.ExecutionStatus value)
0x40c93  ldc.i4.1
0x40c94  ret
```
