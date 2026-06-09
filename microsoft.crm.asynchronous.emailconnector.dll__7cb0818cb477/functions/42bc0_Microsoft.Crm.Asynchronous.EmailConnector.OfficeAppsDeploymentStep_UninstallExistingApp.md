# Microsoft.Crm.Asynchronous.EmailConnector.OfficeAppsDeploymentStep::UninstallExistingApp

- ea: `0x42bc0`
- end: `0x42d29`
- name: `Microsoft.Crm.Asynchronous.EmailConnector.OfficeAppsDeploymentStep::UninstallExistingApp`
- size: `361`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `installer_update, broker_com_uri`

## callers

- `0x42b50`

## callees

- `0x13750`
- `0x13fd0`
- `0x14090`
- `0x28140`
- `0x28150`
- `0x32970`
- `0x3ab40`
- `0x417a0`
- `0x41bc0`
- `0x42060`
- `0x42bc0`
- `0x4da80`

## string_xrefs

- `0x42c10`: `Failed to uninstall the MailApp for mailbox {0}, organization {1}, async event id {2} : exception: {3}`
- `0x42cba`: `Failed to uninstall the MailApp for mailbox {0}, organization {1}, async event id {2} : exception: {3}`
- `0x42c75`: `Uninstalling the MailApp was successful for mailbox {0}, organization {1}`

## pseudocode

```c

```

## disassembly

```asm
0x42bc0  newobj   instance void Microsoft.Crm.Asynchronous.EmailConnector.UninstallAppType::.ctor()
0x42bc5  stloc.0
0x42bc6  ldloc.0
0x42bc7  castclass Microsoft.Crm.Asynchronous.EmailConnector.UninstallAppType
0x42bcc  ldarg.0
0x42bcd  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IEmailProviderContext Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::Context
0x42bd2  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext::get_OrganizationId()
0x42bd7  stloc.1
0x42bd8  ldloca.s 1
0x42bda  ldstr    aB// "B"
0x42bdf  call     instance string [mscorlib]System.Guid::ToString(string)
0x42be4  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.UninstallAppType::set_ID(string value)
0x42be9  ldarg.0
0x42bea  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IExchangeIncomingEmailProvider Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::provider
0x42bef  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeServiceBinding Microsoft.Crm.Asynchronous.EmailConnector.IExchangeIncomingEmailProvider::get_ExchangeServiceBinding()
0x42bf4  ldloc.0
0x42bf5  castclass Microsoft.Crm.Asynchronous.EmailConnector.UninstallAppType
0x42bfa  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.UninstallAppResponseType Microsoft.Crm.Asynchronous.EmailConnector.ExchangeServiceBinding::UninstallApp(class Microsoft.Crm.Asynchronous.EmailConnector.UninstallAppType)
0x42bff  stloc.2
0x42c00  ldloc.2
0x42c01  brfalse.s loc_42C0E
0x42c03  ldloc.2
0x42c04  brfalse.s loc_42C73
0x42c06  ldloc.2
0x42c07  callvirt instance valuetype Microsoft.Crm.Asynchronous.EmailConnector.ResponseClassType Microsoft.Crm.Asynchronous.EmailConnector.ResponseMessageType::get_ResponseClass()
0x42c0c  brfalse.s loc_42C73
0x42c0e  ldarg.0
0x42c0f  ldc.i4.1
0x42c10  ldstr    aFailedToUninst// "Failed to uninstall the MailApp for mai"...
0x42c15  ldc.i4.4
0x42c16  newarr   [mscorlib]System.Object
0x42c1b  dup
0x42c1c  ldc.i4.0
0x42c1d  ldarg.0
0x42c1e  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IExchangeIncomingEmailProvider Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::provider
0x42c23  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailState Microsoft.Crm.Asynchronous.EmailConnector.IIncomingEmailProvider::get_Mailbox()
0x42c28  ldstr    aMailboxid// "mailboxid"
0x42c2d  callvirt instance object Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailState::get_Item(string attributeName)
0x42c32  stelem.ref
0x42c33  dup
0x42c34  ldc.i4.1
0x42c35  ldarg.0
0x42c36  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IEmailProviderContext Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::Context
0x42c3b  callvirt instance class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IAsyncEvent Microsoft.Crm.Asynchronous.EmailConnector.IActivityProviderContext::get_AsyncEvent()
0x42c40  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IAsyncEvent::get_OrganizationId()
0x42c45  box      [mscorlib]System.Guid
0x42c4a  stelem.ref
0x42c4b  dup
0x42c4c  ldc.i4.2
0x42c4d  ldarg.0
0x42c4e  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IEmailProviderContext Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::Context
0x42c53  callvirt instance class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IAsyncEvent Microsoft.Crm.Asynchronous.EmailConnector.IActivityProviderContext::get_AsyncEvent()
0x42c58  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IAsyncEvent::get_EventId()
0x42c5d  box      [mscorlib]System.Guid
0x42c62  stelem.ref
0x42c63  dup
0x42c64  ldc.i4.3
0x42c65  ldloc.2
0x42c66  callvirt instance string Microsoft.Crm.Asynchronous.EmailConnector.ResponseMessageType::get_MessageText()
0x42c6b  stelem.ref
0x42c6c  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::HandleTrace(valuetype [System]System.Diagnostics.TraceLevel traceLevel, string format, object[] args)
0x42c71  br.s     loc_42CB5
0x42c73  ldarg.0
0x42c74  ldc.i4.4
0x42c75  ldstr    aUninstallingTh// "Uninstalling the MailApp was successful"...
0x42c7a  ldc.i4.2
0x42c7b  newarr   [mscorlib]System.Object
0x42c80  dup
0x42c81  ldc.i4.0
0x42c82  ldarg.0
0x42c83  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IExchangeIncomingEmailProvider Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::provider
0x42c88  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailState Microsoft.Crm.Asynchronous.EmailConnector.IIncomingEmailProvider::get_Mailbox()
0x42c8d  ldstr    aMailboxid// "mailboxid"
0x42c92  callvirt instance object Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailState::get_Item(string attributeName)
0x42c97  stelem.ref
0x42c98  dup
0x42c99  ldc.i4.1
0x42c9a  ldarg.0
0x42c9b  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IEmailProviderContext Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::Context
0x42ca0  callvirt instance class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IAsyncEvent Microsoft.Crm.Asynchronous.EmailConnector.IActivityProviderContext::get_AsyncEvent()
0x42ca5  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IAsyncEvent::get_OrganizationId()
0x42caa  box      [mscorlib]System.Guid
0x42caf  stelem.ref
0x42cb0  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::HandleTrace(valuetype [System]System.Diagnostics.TraceLevel traceLevel, string format, object[] args)
0x42cb5  leave.s  loc_42D28
0x42cb7  stloc.3
0x42cb8  ldarg.0
0x42cb9  ldc.i4.1
0x42cba  ldstr    aFailedToUninst// "Failed to uninstall the MailApp for mai"...
0x42cbf  ldc.i4.4
0x42cc0  newarr   [mscorlib]System.Object
0x42cc5  dup
0x42cc6  ldc.i4.0
0x42cc7  ldarg.0
0x42cc8  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IExchangeIncomingEmailProvider Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::provider
0x42ccd  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailState Microsoft.Crm.Asynchronous.EmailConnector.IIncomingEmailProvider::get_Mailbox()
0x42cd2  ldstr    aMailboxid// "mailboxid"
0x42cd7  callvirt instance object Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailState::get_Item(string attributeName)
0x42cdc  stelem.ref
0x42cdd  dup
0x42cde  ldc.i4.1
0x42cdf  ldarg.0
0x42ce0  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IEmailProviderContext Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::Context
0x42ce5  callvirt instance class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IAsyncEvent Microsoft.Crm.Asynchronous.EmailConnector.IActivityProviderContext::get_AsyncEvent()
0x42cea  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IAsyncEvent::get_OrganizationId()
0x42cef  box      [mscorlib]System.Guid
0x42cf4  stelem.ref
0x42cf5  dup
0x42cf6  ldc.i4.2
0x42cf7  ldarg.0
0x42cf8  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IEmailProviderContext Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::Context
0x42cfd  callvirt instance class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IAsyncEvent Microsoft.Crm.Asynchronous.EmailConnector.IActivityProviderContext::get_AsyncEvent()
0x42d02  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IAsyncEvent::get_EventId()
0x42d07  box      [mscorlib]System.Guid
0x42d0c  stelem.ref
0x42d0d  dup
0x42d0e  ldc.i4.3
0x42d0f  ldloc.3
0x42d10  ldarg.0
0x42d11  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IEmailProviderContext Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::Context
0x42d16  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext::get_OrganizationId()
0x42d1b  call     string Microsoft.Crm.Asynchronous.EmailConnector.EmailConnectorTraceHandler::EmailConnectorExceptionToString(class [mscorlib]System.Exception e, valuetype [mscorlib]System.Guid orgId)
0x42d20  stelem.ref
0x42d21  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::HandleTrace(valuetype [System]System.Diagnostics.TraceLevel traceLevel, string format, object[] args)
0x42d26  leave.s  loc_42D28
0x42d28  ret
```
