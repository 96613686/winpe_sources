# Microsoft.Crm.Asynchronous.EmailConnector.CrmProvider::DeleteOpenInstances

- ea: `0x63240`
- end: `0x63327`
- name: `Microsoft.Crm.Asynchronous.EmailConnector.CrmProvider::DeleteOpenInstances`
- size: `231`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, broker_com_uri`

## callers

- `0x643b0`

## callees

- `0x4da80`
- `0x58b30`
- `0x59000`
- `0x59a30`
- `0x5a9b0`
- `0x5e6d0`
- `0x62580`
- `0x625c0`
- `0x62680`
- `0x63240`

## string_xrefs

- `0x63247`: `DeleteOpenInstancesRequest`
- `0x6330c`: `DeleteOpenInstancesRequest`
- `0x63251`: `DeleteOpenInstances`
- `0x63316`: `DeleteOpenInstances`
- `0x632d2`: `Failed to delete open instances for recurring appointment {0} for the mailbox : {1}. Exception details : {2}.`

## pseudocode

```c

```

## disassembly

```asm
0x63240  ldc.i4.0
0x63241  ldarg.0
0x63242  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext Microsoft.Crm.Asynchronous.EmailConnector.CrmProvider::_context
0x63247  ldstr    aDeleteopeninst// "DeleteOpenInstancesRequest"
0x6324c  ldstr    aRecurringappoi_0// "recurringappointmentmaster"
0x63251  ldstr    aDeleteopeninst_0// "DeleteOpenInstances"
0x63256  ldstr    asc_8A7C2// ""
0x6325b  call     void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncUtility::WriteCrmServiceExecuteEvent(valuetype Microsoft.Crm.Asynchronous.EmailConnector.EtwLogType etwLogType, class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext context, string requestName, string entityType, string functionName, [opt] string functionParam)
0x63260  ldstr    aRecurringappoi_0// "recurringappointmentmaster"
0x63265  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::.ctor(string)
0x6326a  stloc.0
0x6326b  ldloc.0
0x6326c  ldstr    aActivityid// "activityid"
0x63271  ldarg.1
0x63272  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x63277  box      [mscorlib]System.Guid
0x6327c  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_Item(string, object)
0x63281  newobj   instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.DeleteOpenInstancesRequest::.ctor()
0x63286  stloc.1
0x63287  ldloc.1
0x63288  ldloc.0
0x63289  callvirt instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.DeleteOpenInstancesRequest::set_Target(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity)
0x6328e  ldloc.1
0x6328f  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x63294  callvirt instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.DeleteOpenInstancesRequest::set_SeriesEndDate(valuetype [mscorlib]System.DateTime)
0x63299  ldloc.1
0x6329a  ldc.i4.0
0x6329b  callvirt instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.DeleteOpenInstancesRequest::set_StateOfPastInstances(int32)
0x632a0  ldarg.0
0x632a1  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncWorker Microsoft.Crm.Asynchronous.EmailConnector.CrmProvider::_exchangeSyncWorker
0x632a6  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncWorkerStepContext Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncWorker::get_StepContext()
0x632ab  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.CrmItemFinder Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncWorkerStepContext::get_CrmFinder()
0x632b0  ldstr    aRecurringappoi_0// "recurringappointmentmaster"
0x632b5  call     valuetype Microsoft.Crm.Asynchronous.EmailConnector.ExchangeItemType Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncUtility::GetExchangeItemType(string entityName)
0x632ba  ldarg.1
0x632bb  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.ItemFinder::RecordCausedItemChange(valuetype Microsoft.Crm.Asynchronous.EmailConnector.ExchangeItemType itemType, string itemId)
0x632c0  ldarg.0
0x632c1  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService Microsoft.Crm.Asynchronous.EmailConnector.CrmProvider::get_CrmService()
0x632c6  ldloc.1
0x632c7  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationResponse [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService::Execute(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest)
0x632cc  pop
0x632cd  leave.s  loc_63326
0x632cf  stloc.2
0x632d0  ldarg.0
0x632d1  ldc.i4.2
0x632d2  ldstr    aFailedToDelete_1// "Failed to delete open instances for rec"...
0x632d7  ldc.i4.3
0x632d8  newarr   [mscorlib]System.Object
0x632dd  dup
0x632de  ldc.i4.0
0x632df  ldarg.1
0x632e0  stelem.ref
0x632e1  dup
0x632e2  ldc.i4.1
0x632e3  ldarg.0
0x632e4  call     instance string Microsoft.Crm.Asynchronous.EmailConnector.CrmProvider::get_MailboxId()
0x632e9  stelem.ref
0x632ea  dup
0x632eb  ldc.i4.2
0x632ec  ldloc.2
0x632ed  ldarg.0
0x632ee  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext Microsoft.Crm.Asynchronous.EmailConnector.CrmProvider::_context
0x632f3  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext::get_OrganizationId()
0x632f8  call     string Microsoft.Crm.Asynchronous.EmailConnector.EmailConnectorTraceHandler::EmailConnectorExceptionToString(class [mscorlib]System.Exception e, valuetype [mscorlib]System.Guid orgId)
0x632fd  stelem.ref
0x632fe  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.CrmProvider::HandleTrace(valuetype [System]System.Diagnostics.TraceLevel traceLevel, string format, object[] args)
0x63303  rethrow
0x63305  ldc.i4.1
0x63306  ldarg.0
0x63307  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext Microsoft.Crm.Asynchronous.EmailConnector.CrmProvider::_context
0x6330c  ldstr    aDeleteopeninst// "DeleteOpenInstancesRequest"
0x63311  ldstr    aRecurringappoi_0// "recurringappointmentmaster"
0x63316  ldstr    aDeleteopeninst_0// "DeleteOpenInstances"
0x6331b  ldstr    asc_8A7C2// ""
0x63320  call     void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncUtility::WriteCrmServiceExecuteEvent(valuetype Microsoft.Crm.Asynchronous.EmailConnector.EtwLogType etwLogType, class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext context, string requestName, string entityType, string functionName, [opt] string functionParam)
0x63325  endfinally
0x63326  ret
```
