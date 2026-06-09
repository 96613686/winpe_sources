# Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailProviderBase::Validate

- ea: `0x32b10`
- end: `0x32c49`
- name: `Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailProviderBase::Validate`
- size: `313`
- prototype: ``
- caller_count: `0`
- callee_count: `18`
- tags: `broker_com_uri`

## callees

- `0x32680`
- `0x32980`
- `0x32b10`
- `0x32d90`
- `0x35770`
- `0x417a0`
- `0x41920`
- `0x4c740`
- `0x4daa0`
- `0x4e870`
- `0x4f410`
- `0x4f460`
- `0x71c90`
- `0x71e20`
- `0x71e40`
- `0x71ea0`
- `0x71ed0`
- `0x71ff0`

## string_xrefs

- `0x32b9c`: `Validation skipped for incoming mailbox: {0}, validation failed with TraceCode {1}`
- `0x32bf1`: `Validation failed for incoming mailbox: {0}, validation failed with TraceCode {1}`

## pseudocode

```c

```

## disassembly

```asm
0x32b10  ldarg.0
0x32b11  isinst   Microsoft.Crm.Asynchronous.EmailConnector.ManualIncomingEmailProvider
0x32b16  brfalse.s loc_32B2F
0x32b18  ldarg.0
0x32b19  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailState Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailProviderBase::get_Mailbox()
0x32b1e  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.Mailbox Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailState::get_InternalMailbox()
0x32b23  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x32b28  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.Mailbox::set_LastSyncStartedOnForManualEC(valuetype [mscorlib]System.DateTime value)
0x32b2d  br.s     loc_32B44
0x32b2f  ldarg.0
0x32b30  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailState Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailProviderBase::get_Mailbox()
0x32b35  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.Mailbox Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailState::get_InternalMailbox()
0x32b3a  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x32b3f  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.Mailbox::set_LastSyncStartedOnForEC(valuetype [mscorlib]System.DateTime value)
0x32b44  ldarg.0
0x32b45  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailState Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailProviderBase::get_Mailbox()
0x32b4a  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.Mailbox Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailState::get_InternalMailbox()
0x32b4f  ldarg.0
0x32b50  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailState Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailProviderBase::get_Mailbox()
0x32b55  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.Mailbox Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailState::get_InternalMailbox()
0x32b5a  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IEmailServerProfile Microsoft.Crm.Asynchronous.EmailConnector.Mailbox::GetEmailServerProfileData()
0x32b5f  ldarg.0
0x32b60  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.IEmailProviderContext Microsoft.Crm.Asynchronous.EmailConnector.IncomingActivityProviderBase::get_Context()
0x32b65  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext::get_OrganizationId()
0x32b6a  ldarg.0
0x32b6b  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.IEmailProviderContext Microsoft.Crm.Asynchronous.EmailConnector.IncomingActivityProviderBase::get_Context()
0x32b70  callvirt instance bool Microsoft.Crm.Asynchronous.EmailConnector.IEmailProviderContext::get_IsInTestAccessContext()
0x32b75  ldarg.0
0x32b76  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.IEmailProviderContext Microsoft.Crm.Asynchronous.EmailConnector.IncomingActivityProviderBase::get_Context()
0x32b7b  callvirt instance class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IAsyncEvent Microsoft.Crm.Asynchronous.EmailConnector.IActivityProviderContext::get_AsyncEvent()
0x32b80  newobj   instance void Microsoft.Crm.Asynchronous.EmailConnector.MailboxIncomingConfigurationValidator::.ctor(class Microsoft.Crm.Asynchronous.EmailConnector.Mailbox mailbox, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IEmailServerProfile profileData, valuetype [mscorlib]System.Guid organizationId, bool isTestAccessOperation, class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IAsyncEvent asyncEvent)
0x32b85  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.MailboxErrorInfo Microsoft.Crm.Asynchronous.EmailConnector.MailboxConfigurationValidator::Validate()
0x32b8a  stloc.0
0x32b8b  ldloc.0
0x32b8c  brfalse  loc_32C47
0x32b91  ldloc.0
0x32b92  callvirt instance valuetype Microsoft.Crm.Asynchronous.EmailConnector.ErrorType Microsoft.Crm.Asynchronous.EmailConnector.ErrorInfo::get_ErrorType()
0x32b97  ldc.i4.2
0x32b98  bne.un.s loc_32BEF
0x32b9a  ldarg.0
0x32b9b  ldc.i4.4
0x32b9c  ldstr    aValidationSkip// "Validation skipped for incoming mailbox"...
0x32ba1  ldc.i4.2
0x32ba2  newarr   [mscorlib]System.Object
0x32ba7  dup
0x32ba8  ldc.i4.0
0x32ba9  ldarg.0
0x32baa  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailState Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailProviderBase::get_Mailbox()
0x32baf  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.Mailbox Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailState::get_InternalMailbox()
0x32bb4  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity Microsoft.Crm.Asynchronous.EmailConnector.Mailbox::get_InternalEntity()
0x32bb9  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Id()
0x32bbe  box      [mscorlib]System.Guid
0x32bc3  stelem.ref
0x32bc4  dup
0x32bc5  ldc.i4.1
0x32bc6  ldloc.0
0x32bc7  callvirt instance class [Microsoft.Crm]Microsoft.Crm.TraceData Microsoft.Crm.Asynchronous.EmailConnector.ErrorInfo::get_TraceData()
0x32bcc  callvirt instance int32 [Microsoft.Crm]Microsoft.Crm.TraceData::get_TraceCode()
0x32bd1  box      [mscorlib]System.Int32
0x32bd6  stelem.ref
0x32bd7  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailProviderBase::HandleTrace(valuetype [System]System.Diagnostics.TraceLevel traceLevel, string format, object[] args)
0x32bdc  ldarg.0
0x32bdd  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailState Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailProviderBase::get_Mailbox()
0x32be2  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.Mailbox Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailState::get_InternalMailbox()
0x32be7  ldc.i4.4
0x32be8  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.Mailbox::set_ProcessingResult(valuetype Microsoft.Crm.Asynchronous.EmailConnector.MailboxProcessingResult value)
0x32bed  br.s     loc_32C47
0x32bef  ldarg.0
0x32bf0  ldc.i4.1
0x32bf1  ldstr    aValidationFail// "Validation failed for incoming mailbox:"...
0x32bf6  ldc.i4.2
0x32bf7  newarr   [mscorlib]System.Object
0x32bfc  dup
0x32bfd  ldc.i4.0
0x32bfe  ldarg.0
0x32bff  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailState Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailProviderBase::get_Mailbox()
0x32c04  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.Mailbox Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailState::get_InternalMailbox()
0x32c09  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity Microsoft.Crm.Asynchronous.EmailConnector.Mailbox::get_InternalEntity()
0x32c0e  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Id()
0x32c13  box      [mscorlib]System.Guid
0x32c18  stelem.ref
0x32c19  dup
0x32c1a  ldc.i4.1
0x32c1b  ldloc.0
0x32c1c  callvirt instance class [Microsoft.Crm]Microsoft.Crm.TraceData Microsoft.Crm.Asynchronous.EmailConnector.ErrorInfo::get_TraceData()
0x32c21  callvirt instance int32 [Microsoft.Crm]Microsoft.Crm.TraceData::get_TraceCode()
0x32c26  box      [mscorlib]System.Int32
0x32c2b  stelem.ref
0x32c2c  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailProviderBase::HandleTrace(valuetype [System]System.Diagnostics.TraceLevel traceLevel, string format, object[] args)
0x32c31  ldarg.0
0x32c32  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailState Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailProviderBase::get_Mailbox()
0x32c37  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.Mailbox Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailState::get_InternalMailbox()
0x32c3c  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.IErrorHandler Microsoft.Crm.Asynchronous.EmailConnector.Mailbox::get_ErrorHandler()
0x32c41  ldloc.0
0x32c42  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.IErrorHandler::HandleError(class Microsoft.Crm.Asynchronous.EmailConnector.IErrorInfo errorInfo)
0x32c47  ldc.i4.1
0x32c48  ret
```
