# Microsoft.Crm.Asynchronous.EmailConnector.MailboxConfigurationValidator::ValidateMailboxConfiguration

- ea: `0x4ca00`
- end: `0x4ccdb`
- name: `Microsoft.Crm.Asynchronous.EmailConnector.MailboxConfigurationValidator::ValidateMailboxConfiguration`
- size: `731`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callers

- `0x4c740`

## callees

- `0x4c9b0`
- `0x4c9e0`
- `0x4ca00`
- `0x4cce0`
- `0x4ce00`
- `0x4cf90`
- `0x4cfd0`
- `0x4d010`
- `0x4d050`
- `0x4d070`
- `0x4d0d0`
- `0x516f0`

## string_xrefs

- `0x4cc59`: `Validation failed: Mailbox: {0} is associated to a system user: {1} whose access mode: {2} is not valid for email processing .`

## pseudocode

```c

```

## disassembly

```asm
0x4ca00  ldarg.0
0x4ca01  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IMailboxData Microsoft.Crm.Asynchronous.EmailConnector.MailboxConfigurationValidator::get_Mailbox()
0x4ca06  brtrue.s loc_4CA32
0x4ca08  ldarg.0
0x4ca09  ldc.i4.3
0x4ca0a  ldc.i4.s 0x3D
0x4ca0c  ldstr    aValidationFail_14// "Validation failed: Invalid Mailbox foun"...
0x4ca11  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.MailboxConfigurationValidator::HandleTrace(valuetype [System]System.Diagnostics.TraceLevel traceLevel, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory traceCategory, string format)
0x4ca16  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x4ca1b  ldc.i4.3
0x4ca1c  ldc.i4.0
0x4ca1d  ldc.i4.0
0x4ca1e  ldc.i4.3
0x4ca1f  ldarg.0
0x4ca20  call     instance valuetype Microsoft.Crm.Asynchronous.EmailConnector.EmailDirectionCode Microsoft.Crm.Asynchronous.EmailConnector.MailboxConfigurationValidator::get_EmailDirection()
0x4ca25  brfalse.s loc_4CA2A
0x4ca27  ldc.i4.1
0x4ca28  br.s     loc_4CA2B
0x4ca2a  ldc.i4.0
0x4ca2b  ldnull
0x4ca2c  call     class Microsoft.Crm.Asynchronous.EmailConnector.MailboxErrorInfo Microsoft.Crm.Asynchronous.EmailConnector.ErrorHandler::MailboxErrorInfoWithDynamicLink(valuetype [mscorlib]System.Guid organizationId, int32 traceCode, valuetype Microsoft.Crm.Asynchronous.EmailConnector.ErrorType errorType, valuetype Microsoft.Crm.Asynchronous.EmailConnector.ErrorSource errorSource, valuetype Microsoft.Crm.Asynchronous.EmailConnector.MailboxErrorScope errorScope, valuetype Microsoft.Crm.Asynchronous.EmailConnector.MailboxOperationType mailboxOperationType, [opt] string errorString)
0x4ca31  ret
0x4ca32  ldarg.0
0x4ca33  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.MailboxErrorInfo Microsoft.Crm.Asynchronous.EmailConnector.MailboxConfigurationValidator::CheckForForwardMailbox()
0x4ca38  stloc.0
0x4ca39  ldloc.0
0x4ca3a  brfalse.s loc_4CA3E
0x4ca3c  ldloc.0
0x4ca3d  ret
0x4ca3e  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.OrganizationCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.OrganizationCache::Instance()
0x4ca43  ldarg.0
0x4ca44  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.EmailConnector.MailboxConfigurationValidator::get_OrganizationId()
0x4ca49  ldarg.0
0x4ca4a  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.EmailConnector.MailboxConfigurationValidator::get_OrganizationId()
0x4ca4f  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::.ctor(valuetype [mscorlib]System.Guid)
0x4ca54  callvirt instance var<u1> class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.CrmMultiOrgCacheBase`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings>::LookupEntry(void, var<u1>)
0x4ca59  callvirt instance valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.EmailConnectionChannelType [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings::get_EmailConnectionChannel()
0x4ca5e  ldc.i4.1
0x4ca5f  bne.un.s loc_4CAC5
0x4ca61  ldarg.0
0x4ca62  ldc.i4.3
0x4ca63  ldc.i4.s 0x3D
0x4ca65  ldstr    aValidationSkip_1// "Validation skipped: OragnizationId: {0}"...
0x4ca6a  ldc.i4.2
0x4ca6b  newarr   [mscorlib]System.Object
0x4ca70  dup
0x4ca71  ldc.i4.0
0x4ca72  ldarg.0
0x4ca73  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.EmailConnector.MailboxConfigurationValidator::get_OrganizationId()
0x4ca78  box      [mscorlib]System.Guid
0x4ca7d  stelem.ref
0x4ca7e  dup
0x4ca7f  ldc.i4.1
0x4ca80  ldarg.0
0x4ca81  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IMailboxData Microsoft.Crm.Asynchronous.EmailConnector.MailboxConfigurationValidator::get_Mailbox()
0x4ca86  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IMailboxData::get_MailboxId()
0x4ca8b  box      [mscorlib]System.Guid
0x4ca90  stelem.ref
0x4ca91  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.MailboxConfigurationValidator::HandleTrace(valuetype [System]System.Diagnostics.TraceLevel traceLevel, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory traceCategory, string format, object[] args)
0x4ca96  ldarg.0
0x4ca97  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IMailboxData Microsoft.Crm.Asynchronous.EmailConnector.MailboxConfigurationValidator::get_Mailbox()
0x4ca9c  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IMailboxData::get_OrganizationId()
0x4caa1  ldarg.0
0x4caa2  call     instance valuetype Microsoft.Crm.Asynchronous.EmailConnector.EmailDirectionCode Microsoft.Crm.Asynchronous.EmailConnector.MailboxConfigurationValidator::get_EmailDirection()
0x4caa7  brfalse.s loc_4CAB0
0x4caa9  ldc.i4   0xB1
0x4caae  br.s     loc_4CAB5
0x4cab0  ldc.i4   0xB0
0x4cab5  ldc.i4.0
0x4cab6  ldc.i4.0
0x4cab7  ldc.i4.4
0x4cab8  ldarg.0
0x4cab9  callvirt instance valuetype Microsoft.Crm.Asynchronous.EmailConnector.MailboxOperationType Microsoft.Crm.Asynchronous.EmailConnector.MailboxConfigurationValidator::get_OperationType()
0x4cabe  ldnull
0x4cabf  call     class Microsoft.Crm.Asynchronous.EmailConnector.MailboxErrorInfo Microsoft.Crm.Asynchronous.EmailConnector.ErrorHandler::MailboxErrorInfoWithDynamicLink(valuetype [mscorlib]System.Guid organizationId, int32 traceCode, valuetype Microsoft.Crm.Asynchronous.EmailConnector.ErrorType errorType, valuetype Microsoft.Crm.Asynchronous.EmailConnector.ErrorSource errorSource, valuetype Microsoft.Crm.Asynchronous.EmailConnector.MailboxErrorScope errorScope, valuetype Microsoft.Crm.Asynchronous.EmailConnector.MailboxOperationType mailboxOperationType, [opt] string errorString)
0x4cac4  ret
0x4cac5  ldarg.0
0x4cac6  call     instance valuetype Microsoft.Crm.Asynchronous.EmailConnector.EmailDirectionCode Microsoft.Crm.Asynchronous.EmailConnector.MailboxConfigurationValidator::get_EmailDirection()
0x4cacb  brfalse.s loc_4CADA
0x4cacd  ldarg.0
0x4cace  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IMailboxData Microsoft.Crm.Asynchronous.EmailConnector.MailboxConfigurationValidator::get_Mailbox()
0x4cad3  callvirt instance valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.EmailDeliveryMethod [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IMailboxData::get_OutgoingEmailDeliveryMethod()
0x4cad8  br.s     loc_4CAE5
0x4cada  ldarg.0
0x4cadb  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IMailboxData Microsoft.Crm.Asynchronous.EmailConnector.MailboxConfigurationValidator::get_Mailbox()
0x4cae0  callvirt instance valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.EmailDeliveryMethod [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IMailboxData::get_IncomingEmailDeliveryMethod()
0x4cae5  ldc.i4.2
0x4cae6  beq.s    loc_4CB38
0x4cae8  ldarg.0
0x4cae9  ldc.i4.3
0x4caea  ldc.i4.s 0x3D
0x4caec  ldstr    aValidationSkip_2// "Validation skipped: Mailbox: {0} delive"...
0x4caf1  ldc.i4.1
0x4caf2  newarr   [mscorlib]System.Object
0x4caf7  dup
0x4caf8  ldc.i4.0
0x4caf9  ldarg.0
0x4cafa  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IMailboxData Microsoft.Crm.Asynchronous.EmailConnector.MailboxConfigurationValidator::get_Mailbox()
0x4caff  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IMailboxData::get_MailboxId()
0x4cb04  box      [mscorlib]System.Guid
0x4cb09  stelem.ref
0x4cb0a  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.MailboxConfigurationValidator::HandleTrace(valuetype [System]System.Diagnostics.TraceLevel traceLevel, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory traceCategory, string format, object[] args)
0x4cb0f  ldarg.0
0x4cb10  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IMailboxData Microsoft.Crm.Asynchronous.EmailConnector.MailboxConfigurationValidator::get_Mailbox()
0x4cb15  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IMailboxData::get_OrganizationId()
0x4cb1a  ldarg.0
0x4cb1b  call     instance valuetype Microsoft.Crm.Asynchronous.EmailConnector.EmailDirectionCode Microsoft.Crm.Asynchronous.EmailConnector.MailboxConfigurationValidator::get_EmailDirection()
0x4cb20  brfalse.s loc_4CB26
0x4cb22  ldc.i4.s 0x28
0x4cb24  br.s     loc_4CB28
0x4cb26  ldc.i4.s 0x27
0x4cb28  ldc.i4.2
0x4cb29  ldc.i4.0
0x4cb2a  ldc.i4.3
0x4cb2b  ldarg.0
0x4cb2c  callvirt instance valuetype Microsoft.Crm.Asynchronous.EmailConnector.MailboxOperationType Microsoft.Crm.Asynchronous.EmailConnector.MailboxConfigurationValidator::get_OperationType()
0x4cb31  ldnull
0x4cb32  call     class Microsoft.Crm.Asynchronous.EmailConnector.MailboxErrorInfo Microsoft.Crm.Asynchronous.EmailConnector.ErrorHandler::MailboxErrorInfoWithDynamicLink(valuetype [mscorlib]System.Guid organizationId, int32 traceCode, valuetype Microsoft.Crm.Asynchronous.EmailConnector.ErrorType errorType, valuetype Microsoft.Crm.Asynchronous.EmailConnector.ErrorSource errorSource, valuetype Microsoft.Crm.Asynchronous.EmailConnector.MailboxErrorScope errorScope, valuetype Microsoft.Crm.Asynchronous.EmailConnector.MailboxOperationType mailboxOperationType, [opt] string errorString)
0x4cb37  ret
0x4cb38  ldarg.0
0x4cb39  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IMailboxData Microsoft.Crm.Asynchronous.EmailConnector.MailboxConfigurationValidator::get_Mailbox()
0x4cb3e  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IMailboxData::get_EmailAddress()
0x4cb43  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x4cb48  brfalse.s loc_4CB98
0x4cb4a  ldarg.0
0x4cb4b  ldc.i4.3
0x4cb4c  ldc.i4.s 0x3D
0x4cb4e  ldstr    aValidationFail_19// "Validation failed: Mailbox: {0} doesn't"...
0x4cb53  ldc.i4.1
0x4cb54  newarr   [mscorlib]System.Object
0x4cb59  dup
0x4cb5a  ldc.i4.0
0x4cb5b  ldarg.0
0x4cb5c  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IMailboxData Microsoft.Crm.Asynchronous.EmailConnector.MailboxConfigurationValidator::get_Mailbox()
0x4cb61  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IMailboxData::get_RegardingObjectId()
0x4cb66  box      [mscorlib]System.Guid
0x4cb6b  stelem.ref
0x4cb6c  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.MailboxConfigurationValidator::HandleTrace(valuetype [System]System.Diagnostics.TraceLevel traceLevel, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory traceCategory, string format, object[] args)
0x4cb71  ldarg.0
0x4cb72  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IMailboxData Microsoft.Crm.Asynchronous.EmailConnector.MailboxConfigurationValidator::get_Mailbox()
0x4cb77  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IMailboxData::get_OrganizationId()
0x4cb7c  ldarg.0
0x4cb7d  call     instance valuetype Microsoft.Crm.Asynchronous.EmailConnector.EmailDirectionCode Microsoft.Crm.Asynchronous.EmailConnector.MailboxConfigurationValidator::get_EmailDirection()
0x4cb82  brfalse.s loc_4CB87
0x4cb84  ldc.i4.5
0x4cb85  br.s     loc_4CB88
0x4cb87  ldc.i4.6
0x4cb88  ldc.i4.0
0x4cb89  ldc.i4.0
0x4cb8a  ldc.i4.4
0x4cb8b  ldarg.0
0x4cb8c  callvirt instance valuetype Microsoft.Crm.Asynchronous.EmailConnector.MailboxOperationType Microsoft.Crm.Asynchronous.EmailConnector.MailboxConfigurationValidator::get_OperationType()
0x4cb91  ldnull
0x4cb92  call     class Microsoft.Crm.Asynchronous.EmailConnector.MailboxErrorInfo Microsoft.Crm.Asynchronous.EmailConnector.ErrorHandler::MailboxErrorInfoWithDynamicLink(valuetype [mscorlib]System.Guid organizationId, int32 traceCode, valuetype Microsoft.Crm.Asynchronous.EmailConnector.ErrorType errorType, valuetype Microsoft.Crm.Asynchronous.EmailConnector.ErrorSource errorSource, valuetype Microsoft.Crm.Asynchronous.EmailConnector.MailboxErrorScope errorScope, valuetype Microsoft.Crm.Asynchronous.EmailConnector.MailboxOperationType mailboxOperationType, [opt] string errorString)
0x4cb97  ret
0x4cb98  ldarg.0
0x4cb99  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IEmailServerProfile Microsoft.Crm.Asynchronous.EmailConnector.MailboxConfigurationValidator::get_Profile()
0x4cb9e  brtrue.s loc_4CBF0
0x4cba0  ldarg.0
0x4cba1  ldc.i4.3
0x4cba2  ldc.i4.s 0x3D
0x4cba4  ldstr    aValidationFail_6// "Validation failed: Mailbox: {0} doesn't"...
0x4cba9  ldc.i4.1
0x4cbaa  newarr   [mscorlib]System.Object
0x4cbaf  dup
0x4cbb0  ldc.i4.0
0x4cbb1  ldarg.0
0x4cbb2  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IMailboxData Microsoft.Crm.Asynchronous.EmailConnector.MailboxConfigurationValidator::get_Mailbox()
0x4cbb7  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IMailboxData::get_MailboxId()
0x4cbbc  box      [mscorlib]System.Guid
0x4cbc1  stelem.ref
0x4cbc2  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.MailboxConfigurationValidator::HandleTrace(valuetype [System]System.Diagnostics.TraceLevel traceLevel, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory traceCategory, string format, object[] args)
0x4cbc7  ldarg.0
0x4cbc8  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IMailboxData Microsoft.Crm.Asynchronous.EmailConnector.MailboxConfigurationValidator::get_Mailbox()
0x4cbcd  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IMailboxData::get_OrganizationId()
0x4cbd2  ldarg.0
0x4cbd3  call     instance valuetype Microsoft.Crm.Asynchronous.EmailConnector.EmailDirectionCode Microsoft.Crm.Asynchronous.EmailConnector.MailboxConfigurationValidator::get_EmailDirection()
0x4cbd8  brfalse.s loc_4CBDE
0x4cbda  ldc.i4.s 0x2D
0x4cbdc  br.s     loc_4CBE0
0x4cbde  ldc.i4.s 0x2C
0x4cbe0  ldc.i4.0
0x4cbe1  ldc.i4.0
0x4cbe2  ldc.i4.3
0x4cbe3  ldarg.0
0x4cbe4  callvirt instance valuetype Microsoft.Crm.Asynchronous.EmailConnector.MailboxOperationType Microsoft.Crm.Asynchronous.EmailConnector.MailboxConfigurationValidator::get_OperationType()
0x4cbe9  ldnull
0x4cbea  call     class Microsoft.Crm.Asynchronous.EmailConnector.MailboxErrorInfo Microsoft.Crm.Asynchronous.EmailConnector.ErrorHandler::MailboxErrorInfoWithDynamicLink(valuetype [mscorlib]System.Guid organizationId, int32 traceCode, valuetype Microsoft.Crm.Asynchronous.EmailConnector.ErrorType errorType, valuetype Microsoft.Crm.Asynchronous.EmailConnector.ErrorSource errorSource, valuetype Microsoft.Crm.Asynchronous.EmailConnector.MailboxErrorScope errorScope, valuetype Microsoft.Crm.Asynchronous.EmailConnector.MailboxOperationType mailboxOperationType, [opt] string errorString)
0x4cbef  ret
0x4cbf0  ldarg.0
0x4cbf1  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IMailboxData Microsoft.Crm.Asynchronous.EmailConnector.MailboxConfigurationValidator::get_Mailbox()
0x4cbf6  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IMailboxData::get_IsForwardMailbox()
0x4cbfb  brtrue   loc_4CCC6
0x4cc00  ldarg.0
0x4cc01  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IMailboxData Microsoft.Crm.Asynchronous.EmailConnector.MailboxConfigurationValidator::get_Mailbox()
0x4cc06  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IMailboxData::get_RegardingObjectTypeCode()
0x4cc0b  ldc.i4.8
0x4cc0c  bne.un   loc_4CCC6
0x4cc11  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.UserDataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.UserDataCache::Instance()
0x4cc16  ldarg.0
0x4cc17  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IMailboxData Microsoft.Crm.Asynchronous.EmailConnector.MailboxConfigurationValidator::get_Mailbox()
0x4cc1c  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IMailboxData::get_RegardingObjectId()
0x4cc21  ldarg.0
0x4cc22  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.EmailConnector.MailboxConfigurationValidator::get_OrganizationId()
0x4cc27  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::.ctor(valuetype [mscorlib]System.Guid)
0x4cc2c  callvirt instance var<u1> class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.CrmMultiOrgCacheBase`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser>::LookupEntry(void, var<u1>)
0x4cc31  stloc.1
0x4cc32  ldloc.1
0x4cc33  brfalse  loc_4CCC6
0x4cc38  ldloc.1
0x4cc39  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser::get_AccessMode()
0x4cc3e  ldc.i4.2
0x4cc3f  beq      loc_4CCC6
0x4cc44  ldloc.1
0x4cc45  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser::get_AccessMode()
0x4cc4a  ldc.i4.4
0x4cc4b  beq.s    loc_4CCC6
0x4cc4d  ldloc.1
0x4cc4e  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser::get_AccessMode()
0x4cc53  brfalse.s loc_4CCC6
0x4cc55  ldarg.0
0x4cc56  ldc.i4.3
0x4cc57  ldc.i4.s 0x3D
0x4cc59  ldstr    aValidationFail_20// "Validation failed: Mailbox: {0} is asso"...
0x4cc5e  ldc.i4.3
0x4cc5f  newarr   [mscorlib]System.Object
0x4cc64  dup
0x4cc65  ldc.i4.0
0x4cc66  ldarg.0
0x4cc67  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IMailboxData Microsoft.Crm.Asynchronous.EmailConnector.MailboxConfigurationValidator::get_Mailbox()
0x4cc6c  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IMailboxData::get_MailboxId()
0x4cc71  box      [mscorlib]System.Guid
0x4cc76  stelem.ref
0x4cc77  dup
0x4cc78  ldc.i4.1
0x4cc79  ldarg.0
0x4cc7a  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IMailboxData Microsoft.Crm.Asynchronous.EmailConnector.MailboxConfigurationValidator::get_Mailbox()
0x4cc7f  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IMailboxData::get_RegardingObjectId()
0x4cc84  box      [mscorlib]System.Guid
0x4cc89  stelem.ref
0x4cc8a  dup
0x4cc8b  ldc.i4.2
0x4cc8c  ldloc.1
0x4cc8d  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser::get_AccessMode()
0x4cc92  box      [mscorlib]System.Int32
0x4cc97  stelem.ref
0x4cc98  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.MailboxConfigurationValidator::HandleTrace(valuetype [System]System.Diagnostics.TraceLevel traceLevel, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory traceCategory, string format, object[] args)
0x4cc9d  ldarg.0
0x4cc9e  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IMailboxData Microsoft.Crm.Asynchronous.EmailConnector.MailboxConfigurationValidator::get_Mailbox()
0x4cca3  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IMailboxData::get_OrganizationId()
0x4cca8  ldarg.0
0x4cca9  call     instance valuetype Microsoft.Crm.Asynchronous.EmailConnector.EmailDirectionCode Microsoft.Crm.Asynchronous.EmailConnector.MailboxConfigurationValidator::get_EmailDirection()
0x4ccae  brfalse.s loc_4CCB4
0x4ccb0  ldc.i4.s 0x45
0x4ccb2  br.s     loc_4CCB6
0x4ccb4  ldc.i4.s 0x44
0x4ccb6  ldc.i4.0
0x4ccb7  ldc.i4.0
0x4ccb8  ldc.i4.4
0x4ccb9  ldarg.0
0x4ccba  callvirt instance valuetype Microsoft.Crm.Asynchronous.EmailConnector.MailboxOperationType Microsoft.Crm.Asynchronous.EmailConnector.MailboxConfigurationValidator::get_OperationType()
0x4ccbf  ldnull
0x4ccc0  call     class Microsoft.Crm.Asynchronous.EmailConnector.MailboxErrorInfo Microsoft.Crm.Asynchronous.EmailConnector.ErrorHandler::MailboxErrorInfoWithDynamicLink(valuetype [mscorlib]System.Guid organizationId, int32 traceCode, valuetype Microsoft.Crm.Asynchronous.EmailConnector.ErrorType errorType, valuetype Microsoft.Crm.Asynchronous.EmailConnector.ErrorSource errorSource, valuetype Microsoft.Crm.Asynchronous.EmailConnector.MailboxErrorScope errorScope, valuetype Microsoft.Crm.Asynchronous.EmailConnector.MailboxOperationType mailboxOperationType, [opt] string errorString)
0x4ccc5  ret
0x4ccc6  ldarg.0
0x4ccc7  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.MailboxErrorInfo Microsoft.Crm.Asynchronous.EmailConnector.MailboxConfigurationValidator::ValidateEmailAddressApproval()
0x4cccc  stloc.0
0x4cccd  ldloc.0
0x4ccce  brfalse.s loc_4CCD2
0x4ccd0  ldloc.0
0x4ccd1  ret
0x4ccd2  ldarg.0
0x4ccd3  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.MailboxErrorInfo Microsoft.Crm.Asynchronous.EmailConnector.MailboxConfigurationValidator::ValidateExchangeSubscription()
0x4ccd8  stloc.0
0x4ccd9  ldloc.0
0x4ccda  ret
```
