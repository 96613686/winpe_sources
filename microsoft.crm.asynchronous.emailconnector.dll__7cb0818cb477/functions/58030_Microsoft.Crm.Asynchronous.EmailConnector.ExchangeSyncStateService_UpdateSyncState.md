# Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncStateService::UpdateSyncState

- ea: `0x58030`
- end: `0x58112`
- name: `Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncStateService::UpdateSyncState`
- size: `226`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x57c00`
- `0x57c30`

## callees

- `0x4da80`
- `0x50ea0`
- `0x53440`
- `0x53490`
- `0x58030`
- `0x58b30`

## string_xrefs

- `0x58077`: `exchangesyncstatexml`
- `0x58082`: `exchangesyncstatexml`
- `0x58037`: `UpdateRequest`
- `0x580f8`: `UpdateRequest`
- `0x58041`: `UpdateSyncState`
- `0x58102`: `UpdateSyncState`
- `0x580b2`: `Failed to update the sync state : `

## pseudocode

```c

```

## disassembly

```asm
0x58030  ldc.i4.0
0x58031  ldarg.0
0x58032  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncStateService::_context
0x58037  ldstr    aUpdaterequest// "UpdateRequest"
0x5803c  ldstr    aMailbox_0// "Mailbox"
0x58041  ldstr    aUpdatesyncstat// "UpdateSyncState"
0x58046  ldstr    asc_8A7C2// ""
0x5804b  call     void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncUtility::WriteCrmServiceExecuteEvent(valuetype Microsoft.Crm.Asynchronous.EmailConnector.EtwLogType etwLogType, class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext context, string requestName, string entityType, string functionName, [opt] string functionParam)
0x58050  ldstr    aMailbox// "mailbox"
0x58055  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::.ctor(string)
0x5805a  stloc.0
0x5805b  ldloc.0
0x5805c  ldstr    aMailboxid// "mailboxid"
0x58061  ldarg.0
0x58062  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncStateService::_mailbox
0x58067  ldstr    aMailboxid// "mailboxid"
0x5806c  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0x58071  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_Item(string, object)
0x58076  ldloc.0
0x58077  ldstr    aExchangesyncst// "exchangesyncstatexml"
0x5807c  ldarg.0
0x5807d  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncStateService::_mailbox
0x58082  ldstr    aExchangesyncst// "exchangesyncstatexml"
0x58087  ldarg.1
0x58088  dup
0x58089  stloc.2
0x5808a  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_Item(string, object)
0x5808f  ldloc.2
0x58090  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_Item(string, object)
0x58095  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Messages.UpdateRequest::.ctor()
0x5809a  stloc.1
0x5809b  ldloc.1
0x5809c  ldloc.0
0x5809d  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Messages.UpdateRequest::set_Target(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity)
0x580a2  ldarg.0
0x580a3  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncStateService::_crmService
0x580a8  ldloc.1
0x580a9  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationResponse [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService::Execute(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest)
0x580ae  pop
0x580af  leave.s  loc_580F1
0x580b1  stloc.3
0x580b2  ldstr    aFailedToUpdate// "Failed to update the sync state : "
0x580b7  ldloc.3
0x580b8  ldarg.0
0x580b9  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncStateService::_context
0x580be  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext::get_OrganizationId()
0x580c3  call     string Microsoft.Crm.Asynchronous.EmailConnector.EmailConnectorTraceHandler::EmailConnectorExceptionToString(class [mscorlib]System.Exception e, valuetype [mscorlib]System.Guid orgId)
0x580c8  call     string [mscorlib]System.String::Concat(string, string)
0x580cd  newobj   instance void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncException::.ctor(string message)
0x580d2  dup
0x580d3  call     class Microsoft.Crm.Asynchronous.EmailConnector.MailboxExceptionProcessor`1<class Microsoft.Crm.Asynchronous.EmailConnector.MailboxErrorInfo> Microsoft.Crm.Asynchronous.EmailConnector.ExceptionProcessorFactory::CreateMailboxExceptionProcessor()
0x580d8  ldarg.0
0x580d9  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncStateService::_context
0x580de  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext::get_OrganizationId()
0x580e3  ldloc.3
0x580e4  ldc.i4.2
0x580e5  ldc.i4.2
0x580e6  callvirt instance var<u1> class Microsoft.Crm.Asynchronous.EmailConnector.MailboxExceptionProcessor`1<class Microsoft.Crm.Asynchronous.EmailConnector.MailboxErrorInfo>::GetErrorInfo(!!T0, valuetype [mscorlib]System.Guid, class [mscorlib]System.Exception, valuetype Microsoft.Crm.Asynchronous.EmailConnector.MailboxOperationType)
0x580eb  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncException::set_MailboxErrorInfo(class Microsoft.Crm.Asynchronous.EmailConnector.MailboxErrorInfo value)
0x580f0  throw
0x580f1  ldc.i4.1
0x580f2  ldarg.0
0x580f3  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncStateService::_context
0x580f8  ldstr    aUpdaterequest// "UpdateRequest"
0x580fd  ldstr    aMailbox_0// "Mailbox"
0x58102  ldstr    aUpdatesyncstat// "UpdateSyncState"
0x58107  ldstr    asc_8A7C2// ""
0x5810c  call     void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncUtility::WriteCrmServiceExecuteEvent(valuetype Microsoft.Crm.Asynchronous.EmailConnector.EtwLogType etwLogType, class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext context, string requestName, string entityType, string functionName, [opt] string functionParam)
0x58111  ret
```
