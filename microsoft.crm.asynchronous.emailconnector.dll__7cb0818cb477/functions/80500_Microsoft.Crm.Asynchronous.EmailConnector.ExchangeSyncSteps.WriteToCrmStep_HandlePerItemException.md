# Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncSteps.WriteToCrmStep::HandlePerItemException

- ea: `0x80500`
- end: `0x807c8`
- name: `Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncSteps.WriteToCrmStep::HandlePerItemException`
- size: `712`
- prototype: ``
- caller_count: `4`
- callee_count: `19`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x807d0`
- `0x80d00`
- `0x811b0`
- `0x81350`

## callees

- `0x4da80`
- `0x4f410`
- `0x50ea0`
- `0x51950`
- `0x51960`
- `0x53440`
- `0x53480`
- `0x53490`
- `0x59a50`
- `0x5a930`
- `0x5aa10`
- `0x5eae0`
- `0x5eb00`
- `0x5f0c0`
- `0x5f0e0`
- `0x5f150`
- `0x5f170`
- `0x6fc50`
- `0x80500`

## string_xrefs

- `0x8056c`: `The item {0} was not synced to CRM side because a duplicate item was found in CRM. The item is being added to the sync error table for retry. Mailbox : {1}. Exception details : {2}.`
- `0x805da`: `The item {0} was not synced to CRM side because of a scheduling conflict. The item is being added to the sync error table for retry. Mailbox : {1}. Exception details : {2}.`
- `0x80668`: `The item {0} failed to update on the CRM side since the regarding object does not exist in the current CRM org for the mailbox: {1}. The user could be using an older version of Outlook Client. Exception details : {2}.`
- `0x8066f`: `The item {0} failed to update on the CRM side since it is read-only for the mailbox : {1}. Exception details : {2}.`
- `0x806bf`: `The item {0} failed to sync on the CRM side and is being added to the sync error table for the mailbox : {1}. Exception details : {2}.`

## pseudocode

```c

```

## disassembly

```asm
0x80500  ldarg.2
0x80501  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.SyncItemChangeInfo Microsoft.Crm.Asynchronous.EmailConnector.SyncData::get_CrmSyncItemChangeInfo()
0x80506  brtrue.s loc_8050F
0x80508  ldsfld   string [mscorlib]System.String::Empty
0x8050d  br.s     loc_8051A
0x8050f  ldarg.2
0x80510  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.SyncItemChangeInfo Microsoft.Crm.Asynchronous.EmailConnector.SyncData::get_CrmSyncItemChangeInfo()
0x80515  callvirt instance string Microsoft.Crm.Asynchronous.EmailConnector.SyncItemChangeInfo::get_CrmId()
0x8051a  stloc.0
0x8051b  ldloc.0
0x8051c  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x80521  brfalse.s loc_80537
0x80523  ldarg.2
0x80524  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.SyncItemChangeInfo Microsoft.Crm.Asynchronous.EmailConnector.SyncData::get_ExchangeSideSyncItemChangeInfo()
0x80529  brfalse.s loc_80537
0x8052b  ldarg.2
0x8052c  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.SyncItemChangeInfo Microsoft.Crm.Asynchronous.EmailConnector.SyncData::get_ExchangeSideSyncItemChangeInfo()
0x80531  callvirt instance string Microsoft.Crm.Asynchronous.EmailConnector.SyncItemChangeInfo::get_ExchangeEntryId()
0x80536  stloc.0
0x80537  ldarg.1
0x80538  isinst   Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncException
0x8053d  stloc.1
0x8053e  ldloc.1
0x8053f  brfalse.s loc_805AC
0x80541  ldloc.1
0x80542  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.MailboxErrorInfo Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncException::get_MailboxErrorInfo()
0x80547  brfalse.s loc_805AC
0x80549  ldloc.1
0x8054a  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.MailboxErrorInfo Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncException::get_MailboxErrorInfo()
0x8054f  callvirt instance class [Microsoft.Crm]Microsoft.Crm.TraceData Microsoft.Crm.Asynchronous.EmailConnector.ErrorInfo::get_TraceData()
0x80554  brfalse.s loc_805AC
0x80556  ldloc.1
0x80557  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.MailboxErrorInfo Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncException::get_MailboxErrorInfo()
0x8055c  callvirt instance class [Microsoft.Crm]Microsoft.Crm.TraceData Microsoft.Crm.Asynchronous.EmailConnector.ErrorInfo::get_TraceData()
0x80561  callvirt instance int32 [Microsoft.Crm]Microsoft.Crm.TraceData::get_TraceCode()
0x80566  ldc.i4.s 0x66
0x80568  bne.un.s loc_805AC
0x8056a  ldarg.0
0x8056b  ldc.i4.2
0x8056c  ldstr    aTheItem0WasNot// "The item {0} was not synced to CRM side"...
0x80571  ldc.i4.3
0x80572  newarr   [mscorlib]System.Object
0x80577  dup
0x80578  ldc.i4.0
0x80579  ldloc.0
0x8057a  stelem.ref
0x8057b  dup
0x8057c  ldc.i4.1
0x8057d  ldarg.0
0x8057e  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncWorkerStepContext class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncSteps.ExchangeSyncStep`1<bool>::get_StepContext()
0x80583  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncWorker Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncWorkerStepContext::get_Worker()
0x80588  callvirt instance string Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncWorker::get_MailboxId()
0x8058d  stelem.ref
0x8058e  dup
0x8058f  ldc.i4.2
0x80590  ldarg.1
0x80591  ldarg.0
0x80592  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncSteps.ExchangeSyncStep`1<bool>::get_ACTContext()
0x80597  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext::get_OrganizationId()
0x8059c  call     string Microsoft.Crm.Asynchronous.EmailConnector.EmailConnectorTraceHandler::EmailConnectorExceptionToString(class [mscorlib]System.Exception e, valuetype [mscorlib]System.Guid orgId)
0x805a1  stelem.ref
0x805a2  call     instance void class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncSteps.ExchangeSyncStep`1<bool>::HandleTrace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0x805a7  br       loc_80703
0x805ac  ldloc.1
0x805ad  brfalse.s loc_8061A
0x805af  ldloc.1
0x805b0  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.MailboxErrorInfo Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncException::get_MailboxErrorInfo()
0x805b5  brfalse.s loc_8061A
0x805b7  ldloc.1
0x805b8  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.MailboxErrorInfo Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncException::get_MailboxErrorInfo()
0x805bd  callvirt instance class [Microsoft.Crm]Microsoft.Crm.TraceData Microsoft.Crm.Asynchronous.EmailConnector.ErrorInfo::get_TraceData()
0x805c2  brfalse.s loc_8061A
0x805c4  ldloc.1
0x805c5  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.MailboxErrorInfo Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncException::get_MailboxErrorInfo()
0x805ca  callvirt instance class [Microsoft.Crm]Microsoft.Crm.TraceData Microsoft.Crm.Asynchronous.EmailConnector.ErrorInfo::get_TraceData()
0x805cf  callvirt instance int32 [Microsoft.Crm]Microsoft.Crm.TraceData::get_TraceCode()
0x805d4  ldc.i4.s 0x65
0x805d6  bne.un.s loc_8061A
0x805d8  ldarg.0
0x805d9  ldc.i4.2
0x805da  ldstr    aTheItem0WasNot_0// "The item {0} was not synced to CRM side"...
0x805df  ldc.i4.3
0x805e0  newarr   [mscorlib]System.Object
0x805e5  dup
0x805e6  ldc.i4.0
0x805e7  ldloc.0
0x805e8  stelem.ref
0x805e9  dup
0x805ea  ldc.i4.1
0x805eb  ldarg.0
0x805ec  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncWorkerStepContext class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncSteps.ExchangeSyncStep`1<bool>::get_StepContext()
0x805f1  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncWorker Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncWorkerStepContext::get_Worker()
0x805f6  callvirt instance string Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncWorker::get_MailboxId()
0x805fb  stelem.ref
0x805fc  dup
0x805fd  ldc.i4.2
0x805fe  ldarg.1
0x805ff  ldarg.0
0x80600  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncSteps.ExchangeSyncStep`1<bool>::get_ACTContext()
0x80605  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext::get_OrganizationId()
0x8060a  call     string Microsoft.Crm.Asynchronous.EmailConnector.EmailConnectorTraceHandler::EmailConnectorExceptionToString(class [mscorlib]System.Exception e, valuetype [mscorlib]System.Guid orgId)
0x8060f  stelem.ref
0x80610  call     instance void class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncSteps.ExchangeSyncStep`1<bool>::HandleTrace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0x80615  br       loc_80703
0x8061a  ldarg.1
0x8061b  isinst   class [System.ServiceModel]System.ServiceModel.FaultException`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationServiceFault>
0x80620  stloc.2
0x80621  ldloc.2
0x80622  brfalse  loc_806BD
0x80627  ldloc.2
0x80628  callvirt instance var<u1> class [System.ServiceModel]System.ServiceModel.FaultException`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationServiceFault>::get_Detail()
0x8062d  brfalse  loc_806BD
0x80632  ldloc.2
0x80633  callvirt instance var<u1> class [System.ServiceModel]System.ServiceModel.FaultException`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationServiceFault>::get_Detail()
0x80638  callvirt instance int32 [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.BaseServiceFault::get_ErrorCode()
0x8063d  ldc.i4   0x8004022E
0x80642  beq.s    loc_80656
0x80644  ldloc.2
0x80645  callvirt instance var<u1> class [System.ServiceModel]System.ServiceModel.FaultException`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationServiceFault>::get_Detail()
0x8064a  callvirt instance int32 [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.BaseServiceFault::get_ErrorCode()
0x8064f  ldc.i4   0x80040217
0x80654  bne.un.s loc_806BD
0x80656  ldloc.2
0x80657  callvirt instance var<u1> class [System.ServiceModel]System.ServiceModel.FaultException`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationServiceFault>::get_Detail()
0x8065c  callvirt instance int32 [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.BaseServiceFault::get_ErrorCode()
0x80661  ldc.i4   0x8004022E
0x80666  beq.s    loc_8066F
0x80668  ldstr    aTheItem0Failed_1// "The item {0} failed to update on the CR"...
0x8066d  br.s     loc_80674
0x8066f  ldstr    aTheItem0Failed_2// "The item {0} failed to update on the CR"...
0x80674  stloc.3
0x80675  ldarg.0
0x80676  ldc.i4.2
0x80677  ldloc.3
0x80678  ldc.i4.3
0x80679  newarr   [mscorlib]System.Object
0x8067e  dup
0x8067f  ldc.i4.0
0x80680  ldloc.0
0x80681  stelem.ref
0x80682  dup
0x80683  ldc.i4.1
0x80684  ldarg.0
0x80685  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncWorkerStepContext class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncSteps.ExchangeSyncStep`1<bool>::get_StepContext()
0x8068a  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncWorker Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncWorkerStepContext::get_Worker()
0x8068f  callvirt instance string Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncWorker::get_MailboxId()
0x80694  stelem.ref
0x80695  dup
0x80696  ldc.i4.2
0x80697  ldarg.1
0x80698  ldarg.0
0x80699  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncSteps.ExchangeSyncStep`1<bool>::get_ACTContext()
0x8069e  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext::get_OrganizationId()
0x806a3  call     string Microsoft.Crm.Asynchronous.EmailConnector.EmailConnectorTraceHandler::EmailConnectorExceptionToString(class [mscorlib]System.Exception e, valuetype [mscorlib]System.Guid orgId)
0x806a8  stelem.ref
0x806a9  call     instance void class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncSteps.ExchangeSyncStep`1<bool>::HandleTrace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0x806ae  ldarg.2
0x806af  ldc.i4.1
0x806b0  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.SyncData::set_CrmState(valuetype Microsoft.Crm.Asynchronous.EmailConnector.SyncState value)
0x806b5  ldarg.2
0x806b6  ldc.i4.1
0x806b7  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.SyncData::set_ExchangeState(valuetype Microsoft.Crm.Asynchronous.EmailConnector.SyncState value)
0x806bc  ret
0x806bd  ldarg.0
0x806be  ldc.i4.1
0x806bf  ldstr    aTheItem0Failed_3// "The item {0} failed to sync on the CRM "...
0x806c4  ldc.i4.4
0x806c5  newarr   [mscorlib]System.Object
0x806ca  dup
0x806cb  ldc.i4.0
0x806cc  ldloc.0
0x806cd  stelem.ref
0x806ce  dup
0x806cf  ldc.i4.1
0x806d0  ldarg.0
0x806d1  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncWorkerStepContext class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncSteps.ExchangeSyncStep`1<bool>::get_StepContext()
0x806d6  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncWorker Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncWorkerStepContext::get_Worker()
0x806db  callvirt instance string Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncWorker::get_MailboxId()
0x806e0  stelem.ref
0x806e1  dup
0x806e2  ldc.i4.2
0x806e3  ldarg.1
0x806e4  ldarg.0
0x806e5  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncSteps.ExchangeSyncStep`1<bool>::get_ACTContext()
0x806ea  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext::get_OrganizationId()
0x806ef  call     string Microsoft.Crm.Asynchronous.EmailConnector.EmailConnectorTraceHandler::EmailConnectorExceptionToString(class [mscorlib]System.Exception e, valuetype [mscorlib]System.Guid orgId)
0x806f4  stelem.ref
0x806f5  dup
0x806f6  ldc.i4.3
0x806f7  ldc.i4.1
0x806f8  box      [mscorlib]System.Int32
0x806fd  stelem.ref
0x806fe  call     instance void class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncSteps.ExchangeSyncStep`1<bool>::HandleTrace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0x80703  ldarg.2
0x80704  ldc.i4.2
0x80705  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.SyncData::set_CrmState(valuetype Microsoft.Crm.Asynchronous.EmailConnector.SyncState value)
0x8070a  ldloc.1
0x8070b  brfalse.s loc_80728
0x8070d  ldloc.1
0x8070e  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.MailboxErrorInfo Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncException::get_MailboxErrorInfo()
0x80713  brfalse.s loc_80728
0x80715  ldarg.0
0x80716  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncWorkerStepContext class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncSteps.ExchangeSyncStep`1<bool>::get_StepContext()
0x8071b  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.SyncDriver Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncWorkerStepContext::get_CurrentSyncDriver()
0x80720  ldarg.2
0x80721  ldarg.1
0x80722  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.SyncDriver::AddFailureToSyncErrorTable(class Microsoft.Crm.Asynchronous.EmailConnector.SyncData syncData, class [mscorlib]System.Exception ex)
0x80727  ret
0x80728  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x8072d  ldstr    aFailedToSyncIt// "Failed to sync item to CRM server : {0}"
0x80732  ldc.i4.1
0x80733  newarr   [mscorlib]System.Object
0x80738  dup
0x80739  ldc.i4.0
0x8073a  ldarg.1
0x8073b  ldarg.0
0x8073c  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncSteps.ExchangeSyncStep`1<bool>::get_ACTContext()
0x80741  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext::get_OrganizationId()
0x80746  call     string Microsoft.Crm.Asynchronous.EmailConnector.EmailConnectorTraceHandler::EmailConnectorExceptionToString(class [mscorlib]System.Exception e, valuetype [mscorlib]System.Guid orgId)
0x8074b  stelem.ref
0x8074c  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x80751  newobj   instance void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncException::.ctor(string message)
0x80756  stloc.s  4
0x80758  ldloc.s  4
0x8075a  call     class Microsoft.Crm.Asynchronous.EmailConnector.MailboxExceptionProcessor`1<class Microsoft.Crm.Asynchronous.EmailConnector.MailboxErrorInfo> Microsoft.Crm.Asynchronous.EmailConnector.ExceptionProcessorFactory::CreateMailboxExceptionProcessor()
0x8075f  ldarg.0
0x80760  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncSteps.ExchangeSyncStep`1<bool>::get_ACTContext()
0x80765  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext::get_OrganizationId()
0x8076a  ldarg.1
0x8076b  ldc.i4.2
0x8076c  ldc.i4.1
0x8076d  callvirt instance var<u1> class Microsoft.Crm.Asynchronous.EmailConnector.MailboxExceptionProcessor`1<class Microsoft.Crm.Asynchronous.EmailConnector.MailboxErrorInfo>::GetErrorInfo(!!T0, valuetype [mscorlib]System.Guid, class [mscorlib]System.Exception, valuetype Microsoft.Crm.Asynchronous.EmailConnector.MailboxOperationType)
0x80772  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncException::set_MailboxErrorInfo(class Microsoft.Crm.Asynchronous.EmailConnector.MailboxErrorInfo value)
0x80777  ldloc.s  4
0x80779  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.MailboxErrorInfo Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncException::get_MailboxErrorInfo()
0x8077e  callvirt instance valuetype Microsoft.Crm.Asynchronous.EmailConnector.MailboxErrorScope Microsoft.Crm.Asynchronous.EmailConnector.MailboxErrorInfo::get_ErrorScope()
0x80783  brfalse.s loc_807B4
0x80785  ldloc.s  4
0x80787  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.MailboxErrorInfo Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncException::get_MailboxErrorInfo()
0x8078c  ldc.i4.0
0x8078d  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.MailboxErrorInfo::set_ErrorScope(valuetype Microsoft.Crm.Asynchronous.EmailConnector.MailboxErrorScope value)
0x80792  ldloc.s  4
0x80794  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.MailboxErrorInfo Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncException::get_MailboxErrorInfo()
0x80799  callvirt instance class [Microsoft.Crm]Microsoft.Crm.TraceData Microsoft.Crm.Asynchronous.EmailConnector.ErrorInfo::get_TraceData()
0x8079e  ldarg.1
0x8079f  isinst   [Microsoft.Crm.Core]Microsoft.Crm.CrmSecurityException
0x807a4  brtrue.s loc_807AD
0x807a6  ldc.i4   0x82
0x807ab  br.s     loc_807AF
0x807ad  ldc.i4.s 0x71
0x807af  callvirt instance void [Microsoft.Crm]Microsoft.Crm.TraceData::set_TraceCode(int32)
0x807b4  ldarg.0
0x807b5  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncWorkerStepContext class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncSteps.ExchangeSyncStep`1<bool>::get_StepContext()
0x807ba  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.SyncDriver Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncWorkerStepContext::get_CurrentSyncDriver()
0x807bf  ldarg.2
0x807c0  ldloc.s  4
0x807c2  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.SyncDriver::AddFailureToSyncErrorTable(class Microsoft.Crm.Asynchronous.EmailConnector.SyncData syncData, class [mscorlib]System.Exception ex)
0x807c7  ret
```
