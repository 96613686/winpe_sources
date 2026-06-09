# Microsoft.Crm.Asynchronous.EmailConnector.ExchangeMailboxToCrmOrgBinder::CheckAndUpdateConfigFolderOnExchange

- ea: `0x9300`
- end: `0x976e`
- name: `Microsoft.Crm.Asynchronous.EmailConnector.ExchangeMailboxToCrmOrgBinder::CheckAndUpdateConfigFolderOnExchange`
- size: `1134`
- prototype: ``
- caller_count: `1`
- callee_count: `24`
- tags: `file_ops, authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x4c740`

## callees

- `0x9210`
- `0x9230`
- `0x9300`
- `0x98e0`
- `0x9940`
- `0x99e0`
- `0x9a60`
- `0x9af0`
- `0x9b80`
- `0x15850`
- `0x15870`
- `0x15910`
- `0x21820`
- `0x4d8c0`
- `0x4da80`
- `0x4e7b0`
- `0x4e870`
- `0x4f270`
- `0x4f410`
- `0x4f450`
- `0x516f0`
- `0x71c20`
- `0x71ea0`
- `0x71ff0`

## string_xrefs

- `0x939e`: `Check for the Primary Org config folder threw SoapException, considering {0} to be the syncing primary org and continuing. Exception details: {1}`
- `0x93f5`: `Found {0} CRM org config folders present for the mailbox. Trying to delete all the config folders and create one for the OrgId {1}`
- `0x9462`: `Did not find any CRM org config folders present for the mailbox. Trying to create one for the OrgId {0}`
- `0x9559`: `Found a CRM org config folder already existing. Updating the Org details in this folder. Details: isCrmOrgPrimaryExchangeOrg: {0}, Org Details Property: {1}`
- `0x961a`: `Email address of the mailbox {0} is configured with another Microsoft Dynamics 365 organization. Details: isCrmOrgPrimaryExchangeOrg: {1}, Org Details Property: {2}`
- `0x96e0`: `Check for the Primary Org config folder threw invalid operation exception exception, considering {0} to be the syncing primary org and continuing. Exception details: {1}`
- `0x972e`: `Check for the Primary Org config folder threw an exception, considering {0} to be the syncing primary org and continuing. Exception details: {1}`

## pseudocode

```c

```

## disassembly

```asm
0x9300  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.EmailConnector.BaseFolderType>::.ctor()
0x9305  stloc.0
0x9306  ldarg.0
0x9307  ldarg.0
0x9308  call     instance class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IAsyncEvent Microsoft.Crm.Asynchronous.EmailConnector.ExchangeMailboxToCrmOrgBinder::get_AsyncEvent()
0x930d  call     instance class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.EmailConnector.BaseFolderType> Microsoft.Crm.Asynchronous.EmailConnector.ExchangeMailboxToCrmOrgBinder::GetCrmOrgConfigFolders(class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IAsyncEvent asyncEvent)
0x9312  stloc.0
0x9313  leave    loc_93CD
0x9318  ldarg.0
0x9319  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.Mailbox Microsoft.Crm.Asynchronous.EmailConnector.ExchangeMailboxToCrmOrgBinder::get_Mailbox()
0x931e  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.EmailConnector.Mailbox::get_OrganizationId()
0x9323  call     string Microsoft.Crm.Asynchronous.EmailConnector.EmailConnectorTraceHandler::EmailConnectorExceptionToString(class [mscorlib]System.Exception e, valuetype [mscorlib]System.Guid orgId)
0x9328  stloc.1
0x9329  ldloc.1
0x932a  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x932f  brtrue.s loc_933E
0x9331  ldloc.1
0x9332  ldstr    aSmtpAddress// "SMTP address"
0x9337  callvirt instance bool [mscorlib]System.String::Contains(string)
0x933c  brtrue.s loc_9341
0x933e  ldc.i4.1
0x933f  br.s     loc_9342
0x9341  ldc.i4.2
0x9342  stloc.2
0x9343  ldloc.2
0x9344  ldc.i4.2
0x9345  bne.un.s loc_937F
0x9347  ldarg.0
0x9348  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.Mailbox Microsoft.Crm.Asynchronous.EmailConnector.ExchangeMailboxToCrmOrgBinder::get_Mailbox()
0x934d  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.EmailConnector.Mailbox::get_OrganizationId()
0x9352  ldc.i4   0xBC
0x9357  ldc.i4.1
0x9358  ldc.i4.0
0x9359  ldc.i4.3
0x935a  ldarg.1
0x935b  ldnull
0x935c  call     class Microsoft.Crm.Asynchronous.EmailConnector.MailboxErrorInfo Microsoft.Crm.Asynchronous.EmailConnector.ErrorHandler::MailboxErrorInfoWithDynamicLink(valuetype [mscorlib]System.Guid organizationId, int32 traceCode, valuetype Microsoft.Crm.Asynchronous.EmailConnector.ErrorType errorType, valuetype Microsoft.Crm.Asynchronous.EmailConnector.ErrorSource errorSource, valuetype Microsoft.Crm.Asynchronous.EmailConnector.MailboxErrorScope errorScope, valuetype Microsoft.Crm.Asynchronous.EmailConnector.MailboxOperationType mailboxOperationType, [opt] string errorString)
0x9361  stloc.3
0x9362  ldloc.3
0x9363  callvirt instance class [Microsoft.Crm]Microsoft.Crm.TraceData Microsoft.Crm.Asynchronous.EmailConnector.ErrorInfo::get_TraceData()
0x9368  ldc.i4.2
0x9369  callvirt instance void [Microsoft.Crm]Microsoft.Crm.TraceData::set_Level(int32)
0x936e  ldarg.0
0x936f  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.Mailbox Microsoft.Crm.Asynchronous.EmailConnector.ExchangeMailboxToCrmOrgBinder::get_Mailbox()
0x9374  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.IErrorHandler Microsoft.Crm.Asynchronous.EmailConnector.Mailbox::get_ErrorHandler()
0x9379  ldloc.3
0x937a  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.IErrorHandler::HandleError(class Microsoft.Crm.Asynchronous.EmailConnector.IErrorInfo errorInfo)
0x937f  ldarg.0
0x9380  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.Mailbox Microsoft.Crm.Asynchronous.EmailConnector.ExchangeMailboxToCrmOrgBinder::get_Mailbox()
0x9385  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.EmailConnector.Mailbox::get_OrganizationId()
0x938a  ldarg.0
0x938b  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.Mailbox Microsoft.Crm.Asynchronous.EmailConnector.ExchangeMailboxToCrmOrgBinder::get_Mailbox()
0x9390  ldarg.0
0x9391  call     instance class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IAsyncEvent Microsoft.Crm.Asynchronous.EmailConnector.ExchangeMailboxToCrmOrgBinder::get_AsyncEvent()
0x9396  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IAsyncEvent::get_EventId()
0x939b  ldc.i4.s 0x3D
0x939d  ldloc.2
0x939e  ldstr    aCheckForThePri// "Check for the Primary Org config folder"...
0x93a3  ldc.i4.2
0x93a4  newarr   [mscorlib]System.Object
0x93a9  dup
0x93aa  ldc.i4.0
0x93ab  ldarg.0
0x93ac  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.Mailbox Microsoft.Crm.Asynchronous.EmailConnector.ExchangeMailboxToCrmOrgBinder::get_Mailbox()
0x93b1  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.EmailConnector.Mailbox::get_OrganizationId()
0x93b6  box      [mscorlib]System.Guid
0x93bb  stelem.ref
0x93bc  dup
0x93bd  ldc.i4.1
0x93be  ldloc.1
0x93bf  stelem.ref
0x93c0  call     void Microsoft.Crm.Asynchronous.EmailConnector.EmailConnectorTraceHandler::EmailConnectorTraceFormat(valuetype [mscorlib]System.Guid orgId, object mailbox, valuetype [mscorlib]System.Guid asyncEventId, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory traceCategory, valuetype [System]System.Diagnostics.TraceLevel traceLevel, string format, object[] args)
0x93c5  ldnull
0x93c6  stloc.s  4
0x93c8  leave    loc_976B
0x93cd  ldloc.0
0x93ce  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.EmailConnector.BaseFolderType>::get_Count()
0x93d3  ldc.i4.1
0x93d4  ble.s    loc_943B
0x93d6  ldarg.0
0x93d7  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.Mailbox Microsoft.Crm.Asynchronous.EmailConnector.ExchangeMailboxToCrmOrgBinder::get_Mailbox()
0x93dc  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.EmailConnector.Mailbox::get_OrganizationId()
0x93e1  ldarg.0
0x93e2  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.Mailbox Microsoft.Crm.Asynchronous.EmailConnector.ExchangeMailboxToCrmOrgBinder::get_Mailbox()
0x93e7  ldarg.0
0x93e8  call     instance class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IAsyncEvent Microsoft.Crm.Asynchronous.EmailConnector.ExchangeMailboxToCrmOrgBinder::get_AsyncEvent()
0x93ed  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IAsyncEvent::get_EventId()
0x93f2  ldc.i4.s 0x3D
0x93f4  ldc.i4.2
0x93f5  ldstr    aFound0CrmOrgCo// "Found {0} CRM org config folders presen"...
0x93fa  ldc.i4.2
0x93fb  newarr   [mscorlib]System.Object
0x9400  dup
0x9401  ldc.i4.0
0x9402  ldloc.0
0x9403  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.EmailConnector.BaseFolderType>::get_Count()
0x9408  box      [mscorlib]System.Int32
0x940d  stelem.ref
0x940e  dup
0x940f  ldc.i4.1
0x9410  ldarg.0
0x9411  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.Mailbox Microsoft.Crm.Asynchronous.EmailConnector.ExchangeMailboxToCrmOrgBinder::get_Mailbox()
0x9416  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.EmailConnector.Mailbox::get_OrganizationId()
0x941b  box      [mscorlib]System.Guid
0x9420  stelem.ref
0x9421  call     void Microsoft.Crm.Asynchronous.EmailConnector.EmailConnectorTraceHandler::EmailConnectorTraceFormat(valuetype [mscorlib]System.Guid orgId, object mailbox, valuetype [mscorlib]System.Guid asyncEventId, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory traceCategory, valuetype [System]System.Diagnostics.TraceLevel traceLevel, string format, object[] args)
0x9426  ldarg.0
0x9427  ldloc.0
0x9428  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeMailboxToCrmOrgBinder::DeleteConfigFolders(class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.EmailConnector.BaseFolderType> folders)
0x942d  ldarg.0
0x942e  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeMailboxToCrmOrgBinder::CreateConfigFolder()
0x9433  ldnull
0x9434  stloc.s  4
0x9436  leave    loc_976B
0x943b  ldloc.0
0x943c  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.EmailConnector.BaseFolderType>::get_Count()
0x9441  brtrue.s loc_9493
0x9443  ldarg.0
0x9444  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.Mailbox Microsoft.Crm.Asynchronous.EmailConnector.ExchangeMailboxToCrmOrgBinder::get_Mailbox()
0x9449  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.EmailConnector.Mailbox::get_OrganizationId()
0x944e  ldarg.0
0x944f  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.Mailbox Microsoft.Crm.Asynchronous.EmailConnector.ExchangeMailboxToCrmOrgBinder::get_Mailbox()
0x9454  ldarg.0
0x9455  call     instance class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IAsyncEvent Microsoft.Crm.Asynchronous.EmailConnector.ExchangeMailboxToCrmOrgBinder::get_AsyncEvent()
0x945a  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IAsyncEvent::get_EventId()
0x945f  ldc.i4.s 0x3D
0x9461  ldc.i4.4
0x9462  ldstr    aDidNotFindAnyC// "Did not find any CRM org config folders"...
0x9467  ldc.i4.1
0x9468  newarr   [mscorlib]System.Object
0x946d  dup
0x946e  ldc.i4.0
0x946f  ldarg.0
0x9470  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.Mailbox Microsoft.Crm.Asynchronous.EmailConnector.ExchangeMailboxToCrmOrgBinder::get_Mailbox()
0x9475  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.EmailConnector.Mailbox::get_OrganizationId()
0x947a  box      [mscorlib]System.Guid
0x947f  stelem.ref
0x9480  call     void Microsoft.Crm.Asynchronous.EmailConnector.EmailConnectorTraceHandler::EmailConnectorTraceFormat(valuetype [mscorlib]System.Guid orgId, object mailbox, valuetype [mscorlib]System.Guid asyncEventId, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory traceCategory, valuetype [System]System.Diagnostics.TraceLevel traceLevel, string format, object[] args)
0x9485  ldarg.0
0x9486  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeMailboxToCrmOrgBinder::CreateConfigFolder()
0x948b  ldnull
0x948c  stloc.s  4
0x948e  leave    loc_976B
0x9493  ldloc.0
0x9494  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.EmailConnector.BaseFolderType>::get_Count()
0x9499  ldc.i4.1
0x949a  bne.un   loc_9689
0x949f  ldloc.0
0x94a0  ldc.i4.0
0x94a1  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.EmailConnector.BaseFolderType>::get_Item(!!T0)
0x94a6  stloc.s  5
0x94a8  ldloc.s  5
0x94aa  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.ExtendedPropertyType[] Microsoft.Crm.Asynchronous.EmailConnector.BaseFolderType::get_ExtendedProperty()
0x94af  stloc.s  6
0x94b1  ldc.i4.0
0x94b2  stloc.s  7
0x94b4  br       loc_967E
0x94b9  ldloc.s  6
0x94bb  ldloc.s  7
0x94bd  ldelem.ref
0x94be  stloc.s  8
0x94c0  ldloc.s  8
0x94c2  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.PathToExtendedFieldType Microsoft.Crm.Asynchronous.EmailConnector.ExtendedPropertyType::get_ExtendedFieldURI()
0x94c7  callvirt instance string Microsoft.Crm.Asynchronous.EmailConnector.PathToExtendedFieldType::get_PropertyTag()
0x94cc  ldstr    a0x3004// "0x3004"
0x94d1  call     bool [mscorlib]System.String::op_Equality(string, string)
0x94d6  brfalse  loc_9678
0x94db  ldloc.s  8
0x94dd  callvirt instance object Microsoft.Crm.Asynchronous.EmailConnector.ExtendedPropertyType::get_Item()
0x94e2  brfalse.s loc_950E
0x94e4  ldloc.s  8
0x94e6  callvirt instance object Microsoft.Crm.Asynchronous.EmailConnector.ExtendedPropertyType::get_Item()
0x94eb  callvirt instance string [mscorlib]System.Object::ToString()
0x94f0  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x94f5  brtrue.s loc_950E
0x94f7  ldarg.0
0x94f8  ldloc.s  8
0x94fa  callvirt instance object Microsoft.Crm.Asynchronous.EmailConnector.ExtendedPropertyType::get_Item()
0x94ff  callvirt instance string [mscorlib]System.Object::ToString()
0x9504  call     instance bool Microsoft.Crm.Asynchronous.EmailConnector.ExchangeMailboxToCrmOrgBinder::ValidateMailboxConfigurationAgainstCrmOrg(string configurationString)
0x9509  brtrue   loc_9689
0x950e  ldarg.0
0x950f  ldfld    bool Microsoft.Crm.Asynchronous.EmailConnector.ExchangeMailboxToCrmOrgBinder::isCrmOrgPrimaryExchangeOrg
0x9514  brtrue.s loc_9532
0x9516  ldloc.s  8
0x9518  callvirt instance object Microsoft.Crm.Asynchronous.EmailConnector.ExtendedPropertyType::get_Item()
0x951d  brfalse.s loc_9532
0x951f  ldloc.s  8
0x9521  callvirt instance object Microsoft.Crm.Asynchronous.EmailConnector.ExtendedPropertyType::get_Item()
0x9526  callvirt instance string [mscorlib]System.Object::ToString()
0x952b  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x9530  brfalse.s loc_959B
0x9532  ldarg.0
0x9533  ldloc.s  5
0x9535  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeMailboxToCrmOrgBinder::UpdateConfigFolder(class Microsoft.Crm.Asynchronous.EmailConnector.BaseFolderType folder)
0x953a  ldarg.0
0x953b  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.Mailbox Microsoft.Crm.Asynchronous.EmailConnector.ExchangeMailboxToCrmOrgBinder::get_Mailbox()
0x9540  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.EmailConnector.Mailbox::get_OrganizationId()
0x9545  ldarg.0
0x9546  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.Mailbox Microsoft.Crm.Asynchronous.EmailConnector.ExchangeMailboxToCrmOrgBinder::get_Mailbox()
0x954b  ldarg.0
0x954c  call     instance class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IAsyncEvent Microsoft.Crm.Asynchronous.EmailConnector.ExchangeMailboxToCrmOrgBinder::get_AsyncEvent()
0x9551  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IAsyncEvent::get_EventId()
0x9556  ldc.i4.s 0x3D
0x9558  ldc.i4.4
0x9559  ldstr    aFoundACrmOrgCo// "Found a CRM org config folder already e"...
0x955e  ldc.i4.2
0x955f  newarr   [mscorlib]System.Object
0x9564  dup
0x9565  ldc.i4.0
0x9566  ldarg.0
0x9567  ldfld    bool Microsoft.Crm.Asynchronous.EmailConnector.ExchangeMailboxToCrmOrgBinder::isCrmOrgPrimaryExchangeOrg
0x956c  box      [mscorlib]System.Boolean
0x9571  stelem.ref
0x9572  dup
0x9573  ldc.i4.1
0x9574  ldloc.s  8
0x9576  callvirt instance object Microsoft.Crm.Asynchronous.EmailConnector.ExtendedPropertyType::get_Item()
0x957b  brfalse.s loc_958B
0x957d  ldloc.s  8
0x957f  callvirt instance object Microsoft.Crm.Asynchronous.EmailConnector.ExtendedPropertyType::get_Item()
0x9584  callvirt instance string [mscorlib]System.Object::ToString()
0x9589  br.s     loc_9590
0x958b  ldsfld   string [mscorlib]System.String::Empty
0x9590  stelem.ref
0x9591  call     void Microsoft.Crm.Asynchronous.EmailConnector.EmailConnectorTraceHandler::EmailConnectorTraceFormat(valuetype [mscorlib]System.Guid orgId, object mailbox, valuetype [mscorlib]System.Guid asyncEventId, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory traceCategory, valuetype [System]System.Diagnostics.TraceLevel traceLevel, string format, object[] args)
0x9596  br       loc_9689
0x959b  ldarg.1
0x959c  brfalse.s loc_95B0
0x959e  ldarg.1
0x959f  ldc.i4.1
0x95a0  beq.s    loc_95A9
0x95a2  ldc.i4   0x8C
0x95a7  br.s     loc_95B5
0x95a9  ldc.i4   0xAE
0x95ae  br.s     loc_95B5
0x95b0  ldc.i4   0xAD
0x95b5  stloc.s  9
0x95b7  ldarg.0
0x95b8  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.Mailbox Microsoft.Crm.Asynchronous.EmailConnector.ExchangeMailboxToCrmOrgBinder::get_Mailbox()
0x95bd  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.EmailConnector.Mailbox::get_OrganizationId()
0x95c2  ldloc.s  9
0x95c4  ldc.i4.0
0x95c5  ldc.i4.3
0x95c6  ldc.i4.3
0x95c7  ldarg.1
0x95c8  ldnull
0x95c9  call     class Microsoft.Crm.Asynchronous.EmailConnector.MailboxErrorInfo Microsoft.Crm.Asynchronous.EmailConnector.ErrorHandler::MailboxErrorInfoWithDynamicLink(valuetype [mscorlib]System.Guid organizationId, int32 traceCode, valuetype Microsoft.Crm.Asynchronous.EmailConnector.ErrorType errorType, valuetype Microsoft.Crm.Asynchronous.EmailConnector.ErrorSource errorSource, valuetype Microsoft.Crm.Asynchronous.EmailConnector.MailboxErrorScope errorScope, valuetype Microsoft.Crm.Asynchronous.EmailConnector.MailboxOperationType mailboxOperationType, [opt] string errorString)
0x95ce  stloc.s  0xA
0x95d0  ldloc.s  0xA
0x95d2  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<class Microsoft.Crm.Asynchronous.EmailConnector.CustomTraceParameter> Microsoft.Crm.Asynchronous.EmailConnector.ErrorInfo::get_CustomTraceParameters()
0x95d7  ldc.i4.0
0x95d8  ldc.i4.1
0x95d9  ldarg.0
0x95da  ldloc.s  8
0x95dc  callvirt instance object Microsoft.Crm.Asynchronous.EmailConnector.ExtendedPropertyType::get_Item()
0x95e1  callvirt instance string [mscorlib]System.Object::ToString()
0x95e6  call     instance string Microsoft.Crm.Asynchronous.EmailConnector.ExchangeMailboxToCrmOrgBinder::GetLastUpdateTimeFromConfigurationString(string configurationString)
0x95eb  call     class [Microsoft.Crm]Microsoft.Crm.TraceParameter Microsoft.Crm.Asynchronous.EmailConnector.TraceLogHelper::GetTextTypeTraceParameter(string value)
0x95f0  ldc.i4.1
0x95f1  newobj   instance void Microsoft.Crm.Asynchronous.EmailConnector.CustomTraceParameter::.ctor(valuetype Microsoft.Crm.Asynchronous.EmailConnector.ErrorType errorType, int32 collationLevel, class [Microsoft.Crm]Microsoft.Crm.TraceParameter traceParameter, int32 index)
0x95f6  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<class Microsoft.Crm.Asynchronous.EmailConnector.CustomTraceParameter>::Add(var<u1>)
0x95fb  ldarg.0
0x95fc  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.Mailbox Microsoft.Crm.Asynchronous.EmailConnector.ExchangeMailboxToCrmOrgBinder::get_Mailbox()
0x9601  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.EmailConnector.Mailbox::get_OrganizationId()
0x9606  ldarg.0
0x9607  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.Mailbox Microsoft.Crm.Asynchronous.EmailConnector.ExchangeMailboxToCrmOrgBinder::get_Mailbox()
0x960c  ldarg.0
0x960d  call     instance class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IAsyncEvent Microsoft.Crm.Asynchronous.EmailConnector.ExchangeMailboxToCrmOrgBinder::get_AsyncEvent()
0x9612  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IAsyncEvent::get_EventId()
0x9617  ldc.i4.s 0x3D
0x9619  ldc.i4.4
0x961a  ldstr    aEmailAddressOf// "Email address of the mailbox {0} is con"...
0x961f  ldc.i4.3
0x9620  newarr   [mscorlib]System.Object
0x9625  dup
0x9626  ldc.i4.0
0x9627  ldarg.0
0x9628  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.Mailbox Microsoft.Crm.Asynchronous.EmailConnector.ExchangeMailboxToCrmOrgBinder::get_Mailbox()
0x962d  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity Microsoft.Crm.Asynchronous.EmailConnector.Mailbox::get_InternalEntity()
0x9632  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Id()
0x9637  box      [mscorlib]System.Guid
0x963c  stelem.ref
0x963d  dup
0x963e  ldc.i4.1
0x963f  ldarg.0
0x9640  ldfld    bool Microsoft.Crm.Asynchronous.EmailConnector.ExchangeMailboxToCrmOrgBinder::isCrmOrgPrimaryExchangeOrg
0x9645  box      [mscorlib]System.Boolean
0x964a  stelem.ref
0x964b  dup
0x964c  ldc.i4.2
0x964d  ldloc.s  8
0x964f  callvirt instance object Microsoft.Crm.Asynchronous.EmailConnector.ExtendedPropertyType::get_Item()
0x9654  brfalse.s loc_9664
0x9656  ldloc.s  8
0x9658  callvirt instance object Microsoft.Crm.Asynchronous.EmailConnector.ExtendedPropertyType::get_Item()
0x965d  callvirt instance string [mscorlib]System.Object::ToString()
0x9662  br.s     loc_9669
0x9664  ldsfld   string [mscorlib]System.String::Empty
0x9669  stelem.ref
  ... truncated ...
```
