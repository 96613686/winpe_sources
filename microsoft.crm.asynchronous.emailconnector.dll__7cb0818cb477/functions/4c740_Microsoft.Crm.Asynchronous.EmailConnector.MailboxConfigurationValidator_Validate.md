# Microsoft.Crm.Asynchronous.EmailConnector.MailboxConfigurationValidator::Validate

- ea: `0x4c740`
- end: `0x4c948`
- name: `Microsoft.Crm.Asynchronous.EmailConnector.MailboxConfigurationValidator::Validate`
- size: `520`
- prototype: ``
- caller_count: `6`
- callee_count: `19`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x32b10`
- `0x474e0`
- `0x52340`
- `0x75030`
- `0x76790`
- `0x788a0`

## callees

- `0x9300`
- `0x4c0a0`
- `0x4c740`
- `0x4c950`
- `0x4c9e0`
- `0x4ca00`
- `0x4cf90`
- `0x4cfb0`
- `0x4cfd0`
- `0x4d030`
- `0x4d070`
- `0x4d080`
- `0x4d0a0`
- `0x4f410`
- `0x50ea0`
- `0x53480`
- `0x584c0`
- `0x71d00`
- `0x71ea0`

## string_xrefs

- `0x4c782`: `isserviceaccount`
- `0x4c794`: `isserviceaccount`
- `0x4c7d8`: `Check and Update configuration folder on exchange failed.`
- `0x4c7fe`: `Validation Failed for Mailbox {0}. Service request exception occured: {1}.`

## pseudocode

```c

```

## disassembly

```asm
0x4c740  ldnull
0x4c741  stloc.0
0x4c742  ldarg.0
0x4c743  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.MailboxErrorInfo Microsoft.Crm.Asynchronous.EmailConnector.MailboxConfigurationValidator::ValidateMailboxConfiguration()
0x4c748  stloc.0
0x4c749  ldloc.0
0x4c74a  brfalse.s loc_4C753
0x4c74c  ldloc.0
0x4c74d  stloc.1
0x4c74e  leave    loc_4C946
0x4c753  ldarg.0
0x4c754  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.EmailServerProfileConfigurationValidator Microsoft.Crm.Asynchronous.EmailConnector.MailboxConfigurationValidator::get_AssociatedEmailServerProfileValidator()
0x4c759  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.MailboxErrorInfo Microsoft.Crm.Asynchronous.EmailConnector.EmailServerProfileConfigurationValidator::ValidateAssociatedEmailServerProfile()
0x4c75e  stloc.0
0x4c75f  ldloc.0
0x4c760  brfalse.s loc_4C769
0x4c762  ldloc.0
0x4c763  stloc.1
0x4c764  leave    loc_4C946
0x4c769  ldarg.0
0x4c76a  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IEmailServerProfile Microsoft.Crm.Asynchronous.EmailConnector.MailboxConfigurationValidator::get_Profile()
0x4c76f  callvirt instance valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.EmailServerType [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IEmailServerProfile::get_ServerType()
0x4c774  ldc.i4.1
0x4c775  beq.s    loc_4C7F3
0x4c777  ldarg.0
0x4c778  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.Mailbox Microsoft.Crm.Asynchronous.EmailConnector.MailboxConfigurationValidator::get_InternalMailbox()
0x4c77d  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity Microsoft.Crm.Asynchronous.EmailConnector.Mailbox::get_InternalEntity()
0x4c782  ldstr    aIsserviceaccou// "isserviceaccount"
0x4c787  callvirt instance bool [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::Contains(string)
0x4c78c  brfalse.s loc_4C7A5
0x4c78e  ldarg.0
0x4c78f  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.Mailbox Microsoft.Crm.Asynchronous.EmailConnector.MailboxConfigurationValidator::get_InternalMailbox()
0x4c794  ldstr    aIsserviceaccou// "isserviceaccount"
0x4c799  callvirt instance object Microsoft.Crm.Asynchronous.EmailConnector.Mailbox::get_Item(string attributeName)
0x4c79e  unbox.any [mscorlib]System.Boolean
0x4c7a3  brtrue.s loc_4C7F3
0x4c7a5  ldarg.0
0x4c7a6  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IMailboxData Microsoft.Crm.Asynchronous.EmailConnector.MailboxConfigurationValidator::get_Mailbox()
0x4c7ab  brfalse.s loc_4C7F3
0x4c7ad  ldarg.0
0x4c7ae  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IEmailServerProfile Microsoft.Crm.Asynchronous.EmailConnector.MailboxConfigurationValidator::get_Profile()
0x4c7b3  brfalse.s loc_4C7F3
0x4c7b5  ldarg.0
0x4c7b6  call     instance class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.EmailConnector.MailboxAsyncEvent Microsoft.Crm.Asynchronous.EmailConnector.MailboxConfigurationValidator::get_AsyncEvent()
0x4c7bb  brfalse.s loc_4C7F3
0x4c7bd  ldarg.0
0x4c7be  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeMailboxToCrmOrgBinder Microsoft.Crm.Asynchronous.EmailConnector.MailboxConfigurationValidator::get_ExchangeMailboxToCrmOrgBinder()
0x4c7c3  ldarg.0
0x4c7c4  callvirt instance valuetype Microsoft.Crm.Asynchronous.EmailConnector.MailboxOperationType Microsoft.Crm.Asynchronous.EmailConnector.MailboxConfigurationValidator::get_OperationType()
0x4c7c9  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.MailboxErrorInfo Microsoft.Crm.Asynchronous.EmailConnector.ExchangeMailboxToCrmOrgBinder::CheckAndUpdateConfigFolderOnExchange(valuetype Microsoft.Crm.Asynchronous.EmailConnector.MailboxOperationType operationType)
0x4c7ce  stloc.0
0x4c7cf  ldloc.0
0x4c7d0  brfalse.s loc_4C7F3
0x4c7d2  ldloc.0
0x4c7d3  callvirt instance class [Microsoft.Crm]Microsoft.Crm.TraceData Microsoft.Crm.Asynchronous.EmailConnector.ErrorInfo::get_TraceData()
0x4c7d8  ldstr    aCheckAndUpdate// "Check and Update configuration folder o"...
0x4c7dd  ldc.i4   0x400
0x4c7e2  call     string Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncUtility::FormatExceptionMessage(string message, int32 maxLength)
0x4c7e7  callvirt instance void [Microsoft.Crm]Microsoft.Crm.TraceData::set_ErrorDetails(string)
0x4c7ec  ldloc.0
0x4c7ed  stloc.1
0x4c7ee  leave    loc_4C946
0x4c7f3  leave    loc_4C944
0x4c7f8  stloc.2
0x4c7f9  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x4c7fe  ldstr    aValidationFail_16// "Validation Failed for Mailbox {0}. Serv"...
0x4c803  ldc.i4.2
0x4c804  newarr   [mscorlib]System.Object
0x4c809  dup
0x4c80a  ldc.i4.0
0x4c80b  ldarg.0
0x4c80c  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IMailboxData Microsoft.Crm.Asynchronous.EmailConnector.MailboxConfigurationValidator::get_Mailbox()
0x4c811  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IMailboxData::get_MailboxId()
0x4c816  box      [mscorlib]System.Guid
0x4c81b  stelem.ref
0x4c81c  dup
0x4c81d  ldc.i4.1
0x4c81e  ldloc.2
0x4c81f  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmException::ExceptionToString(class [mscorlib]System.Exception)
0x4c824  stelem.ref
0x4c825  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x4c82a  stloc.3
0x4c82b  ldnull
0x4c82c  stloc.s  4
0x4c82e  ldloc.2
0x4c82f  callvirt instance class [mscorlib]System.Exception [mscorlib]System.Exception::get_InnerException()
0x4c834  brfalse.s loc_4C876
0x4c836  ldarg.0
0x4c837  ldc.i4.1
0x4c838  ldc.i4.s 0x3C
0x4c83a  ldloc.3
0x4c83b  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.MailboxConfigurationValidator::HandleTrace(valuetype [System]System.Diagnostics.TraceLevel traceLevel, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory traceCategory, string format)
0x4c840  call     class Microsoft.Crm.Asynchronous.EmailConnector.MailboxExceptionProcessor`1<class Microsoft.Crm.Asynchronous.EmailConnector.MailboxErrorInfo> Microsoft.Crm.Asynchronous.EmailConnector.ExceptionProcessorFactory::CreateMailboxExceptionProcessor()
0x4c845  ldarg.0
0x4c846  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IMailboxData Microsoft.Crm.Asynchronous.EmailConnector.MailboxConfigurationValidator::get_Mailbox()
0x4c84b  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IMailboxData::get_OrganizationId()
0x4c850  ldloc.2
0x4c851  ldarg.0
0x4c852  callvirt instance valuetype Microsoft.Crm.Asynchronous.EmailConnector.MailboxOperationType Microsoft.Crm.Asynchronous.EmailConnector.MailboxConfigurationValidator::get_OperationType()
0x4c857  ldc.i4.0
0x4c858  callvirt instance var<u1> class Microsoft.Crm.Asynchronous.EmailConnector.MailboxExceptionProcessor`1<class Microsoft.Crm.Asynchronous.EmailConnector.MailboxErrorInfo>::GetErrorInfo(!!T0, valuetype [mscorlib]System.Guid, class [mscorlib]System.Exception, valuetype Microsoft.Crm.Asynchronous.EmailConnector.MailboxOperationType)
0x4c85d  stloc.s  4
0x4c85f  ldloc.s  4
0x4c861  callvirt instance class [Microsoft.Crm]Microsoft.Crm.TraceData Microsoft.Crm.Asynchronous.EmailConnector.ErrorInfo::get_TraceData()
0x4c866  ldloc.3
0x4c867  ldc.i4   0x400
0x4c86c  call     string Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncUtility::FormatExceptionMessage(string message, int32 maxLength)
0x4c871  callvirt instance void [Microsoft.Crm]Microsoft.Crm.TraceData::set_ErrorDetails(string)
0x4c876  ldloc.s  4
0x4c878  brfalse.s loc_4C87E
0x4c87a  ldloc.s  4
0x4c87c  br.s     loc_4C885
0x4c87e  ldarg.0
0x4c87f  ldloc.3
0x4c880  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.MailboxErrorInfo Microsoft.Crm.Asynchronous.EmailConnector.MailboxConfigurationValidator::CreateGenericErrorInfo(string errorMessage)
0x4c885  stloc.1
0x4c886  leave    loc_4C946
0x4c88b  stloc.s  5
0x4c88d  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x4c892  ldstr    aValidationFail_17// "Validation Failed for Mailbox {0}. Exch"...
0x4c897  ldc.i4.2
0x4c898  newarr   [mscorlib]System.Object
0x4c89d  dup
0x4c89e  ldc.i4.0
0x4c89f  ldarg.0
0x4c8a0  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IMailboxData Microsoft.Crm.Asynchronous.EmailConnector.MailboxConfigurationValidator::get_Mailbox()
0x4c8a5  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IMailboxData::get_MailboxId()
0x4c8aa  box      [mscorlib]System.Guid
0x4c8af  stelem.ref
0x4c8b0  dup
0x4c8b1  ldc.i4.1
0x4c8b2  ldloc.s  5
0x4c8b4  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmException::ExceptionToString(class [mscorlib]System.Exception)
0x4c8b9  stelem.ref
0x4c8ba  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x4c8bf  stloc.s  6
0x4c8c1  ldloc.s  5
0x4c8c3  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.MailboxErrorInfo Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncException::get_MailboxErrorInfo()
0x4c8c8  brfalse.s loc_4C8FC
0x4c8ca  ldarg.0
0x4c8cb  ldc.i4.1
0x4c8cc  ldc.i4.s 0x3C
0x4c8ce  ldloc.s  6
0x4c8d0  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.MailboxConfigurationValidator::HandleTrace(valuetype [System]System.Diagnostics.TraceLevel traceLevel, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory traceCategory, string format)
0x4c8d5  ldloc.s  5
0x4c8d7  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.MailboxErrorInfo Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncException::get_MailboxErrorInfo()
0x4c8dc  callvirt instance class [Microsoft.Crm]Microsoft.Crm.TraceData Microsoft.Crm.Asynchronous.EmailConnector.ErrorInfo::get_TraceData()
0x4c8e1  ldloc.s  6
0x4c8e3  ldc.i4   0x400
0x4c8e8  call     string Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncUtility::FormatExceptionMessage(string message, int32 maxLength)
0x4c8ed  callvirt instance void [Microsoft.Crm]Microsoft.Crm.TraceData::set_ErrorDetails(string)
0x4c8f2  ldloc.s  5
0x4c8f4  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.MailboxErrorInfo Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncException::get_MailboxErrorInfo()
0x4c8f9  stloc.1
0x4c8fa  leave.s  loc_4C946
0x4c8fc  ldarg.0
0x4c8fd  ldloc.s  6
0x4c8ff  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.MailboxErrorInfo Microsoft.Crm.Asynchronous.EmailConnector.MailboxConfigurationValidator::CreateGenericErrorInfo(string errorMessage)
0x4c904  stloc.1
0x4c905  leave.s  loc_4C946
0x4c907  stloc.s  7
0x4c909  ldarg.0
0x4c90a  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x4c90f  ldstr    aValidationFail_18// "Validation Failed for Mailbox {0}. Unex"...
0x4c914  ldc.i4.2
0x4c915  newarr   [mscorlib]System.Object
0x4c91a  dup
0x4c91b  ldc.i4.0
0x4c91c  ldarg.0
0x4c91d  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IMailboxData Microsoft.Crm.Asynchronous.EmailConnector.MailboxConfigurationValidator::get_Mailbox()
0x4c922  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IMailboxData::get_MailboxId()
0x4c927  box      [mscorlib]System.Guid
0x4c92c  stelem.ref
0x4c92d  dup
0x4c92e  ldc.i4.1
0x4c92f  ldloc.s  7
0x4c931  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmException::ExceptionToString(class [mscorlib]System.Exception)
0x4c936  stelem.ref
0x4c937  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x4c93c  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.MailboxErrorInfo Microsoft.Crm.Asynchronous.EmailConnector.MailboxConfigurationValidator::CreateGenericErrorInfo(string errorMessage)
0x4c941  stloc.1
0x4c942  leave.s  loc_4C946
0x4c944  ldnull
0x4c945  ret
0x4c946  ldloc.1
0x4c947  ret
```
