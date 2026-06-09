# Microsoft.Crm.Asynchronous.EmailConnector.CrmProvider::CreateException

- ea: `0x62fe0`
- end: `0x63138`
- name: `Microsoft.Crm.Asynchronous.EmailConnector.CrmProvider::CreateException`
- size: `344`
- prototype: ``
- caller_count: `3`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x609d0`
- `0x60a20`
- `0x60a70`

## callees

- `0x4da80`
- `0x589e0`
- `0x58a20`
- `0x58b30`
- `0x62580`
- `0x625c0`
- `0x62680`
- `0x62fe0`

## string_xrefs

- `0x63018`: `seriesid`
- `0x62fe7`: `CreateExceptionRequest`
- `0x6311b`: `CreateExceptionRequest`
- `0x62ff1`: `CreateException`
- `0x63125`: `CreateException`
- `0x63077`: `Created an recurring appointment exception {0} on the crm server for the mailbox : {1}.`
- `0x630c0`: `The appointment has been deleted for the mailbox : {0}.`
- `0x630e4`: `Failed to create the exception item for the mailbox : {0}. Exception details : {1}.`

## pseudocode

```c

```

## disassembly

```asm
0x62fe0  ldc.i4.0
0x62fe1  ldarg.0
0x62fe2  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext Microsoft.Crm.Asynchronous.EmailConnector.CrmProvider::_context
0x62fe7  ldstr    aCreateexceptio// "CreateExceptionRequest"
0x62fec  ldstr    aRecurringappoi// "RecurringAppointment"
0x62ff1  ldstr    aCreateexceptio_0// "CreateException"
0x62ff6  ldstr    asc_8A7C2// ""
0x62ffb  call     void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncUtility::WriteCrmServiceExecuteEvent(valuetype Microsoft.Crm.Asynchronous.EmailConnector.EtwLogType etwLogType, class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext context, string requestName, string entityType, string functionName, [opt] string functionParam)
0x63000  newobj   instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.CreateExceptionRequest::.ctor()
0x63005  stloc.0
0x63006  ldstr    aAppointment_0// "appointment"
0x6300b  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::.ctor(string)
0x63010  stloc.1
0x63011  ldarg.s  4
0x63013  brtrue.s loc_63017
0x63015  ldarg.1
0x63016  stloc.1
0x63017  ldloc.1
0x63018  ldstr    aSeriesid// "seriesid"
0x6301d  ldarg.3
0x6301e  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x63023  box      [mscorlib]System.Guid
0x63028  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_Item(string, object)
0x6302d  ldloc.0
0x6302e  ldarg.s  4
0x63030  callvirt instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.CreateExceptionRequest::set_IsDeleted(bool)
0x63035  ldarg.2
0x63036  call     valuetype [mscorlib]System.DateTime Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncUtility::ToDateTimeValue(string propertyValue)
0x6303b  stloc.s  4
0x6303d  ldloca.s 4
0x6303f  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::ToUniversalTime()
0x63044  stloc.2
0x63045  ldloc.0
0x63046  ldloc.2
0x63047  ldc.i4.1
0x63048  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::SpecifyKind(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTimeKind)
0x6304d  callvirt instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.CreateExceptionRequest::set_OriginalStartDate(valuetype [mscorlib]System.DateTime)
0x63052  ldloc.0
0x63053  ldloc.1
0x63054  callvirt instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.CreateExceptionRequest::set_Target(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity)
0x63059  ldarg.0
0x6305a  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService Microsoft.Crm.Asynchronous.EmailConnector.CrmProvider::get_CrmService()
0x6305f  ldloc.0
0x63060  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationResponse [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService::Execute(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest)
0x63065  castclass [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.CreateExceptionResponse
0x6306a  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.CreateExceptionResponse::get_id()
0x6306f  call     string Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncUtility::ToStringValue(valuetype [mscorlib]System.Guid propertyValue)
0x63074  stloc.3
0x63075  ldarg.0
0x63076  ldc.i4.4
0x63077  ldstr    aCreatedAnRecur// "Created an recurring appointment except"...
0x6307c  ldc.i4.2
0x6307d  newarr   [mscorlib]System.Object
0x63082  dup
0x63083  ldc.i4.0
0x63084  ldloc.3
0x63085  stelem.ref
0x63086  dup
0x63087  ldc.i4.1
0x63088  ldarg.0
0x63089  call     instance string Microsoft.Crm.Asynchronous.EmailConnector.CrmProvider::get_MailboxId()
0x6308e  stelem.ref
0x6308f  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.CrmProvider::HandleTrace(valuetype [System]System.Diagnostics.TraceLevel traceLevel, string format, object[] args)
0x63094  ldloc.3
0x63095  stloc.s  5
0x63097  leave    loc_63135
0x6309c  stloc.s  6
0x6309e  ldloc.s  6
0x630a0  isinst   class [System.ServiceModel]System.ServiceModel.FaultException`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationServiceFault>
0x630a5  stloc.s  7
0x630a7  ldloc.s  7
0x630a9  brfalse.s loc_630E2
0x630ab  ldloc.s  7
0x630ad  callvirt instance var<u1> class [System.ServiceModel]System.ServiceModel.FaultException`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationServiceFault>::get_Detail()
0x630b2  callvirt instance int32 [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.BaseServiceFault::get_ErrorCode()
0x630b7  ldc.i4   0x8004E106
0x630bc  bne.un.s loc_630E2
0x630be  ldarg.0
0x630bf  ldc.i4.4
0x630c0  ldstr    aTheAppointment_1// "The appointment has been deleted for th"...
0x630c5  ldc.i4.1
0x630c6  newarr   [mscorlib]System.Object
0x630cb  dup
0x630cc  ldc.i4.0
0x630cd  ldarg.0
0x630ce  call     instance string Microsoft.Crm.Asynchronous.EmailConnector.CrmProvider::get_MailboxId()
0x630d3  stelem.ref
0x630d4  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.CrmProvider::HandleTrace(valuetype [System]System.Diagnostics.TraceLevel traceLevel, string format, object[] args)
0x630d9  ldsfld   string [mscorlib]System.String::Empty
0x630de  stloc.s  5
0x630e0  leave.s  loc_63135
0x630e2  ldarg.0
0x630e3  ldc.i4.2
0x630e4  ldstr    aFailedToCreate_0// "Failed to create the exception item for"...
0x630e9  ldc.i4.2
0x630ea  newarr   [mscorlib]System.Object
0x630ef  dup
0x630f0  ldc.i4.0
0x630f1  ldarg.0
0x630f2  call     instance string Microsoft.Crm.Asynchronous.EmailConnector.CrmProvider::get_MailboxId()
0x630f7  stelem.ref
0x630f8  dup
0x630f9  ldc.i4.1
0x630fa  ldloc.s  6
0x630fc  ldarg.0
0x630fd  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext Microsoft.Crm.Asynchronous.EmailConnector.CrmProvider::_context
0x63102  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext::get_OrganizationId()
0x63107  call     string Microsoft.Crm.Asynchronous.EmailConnector.EmailConnectorTraceHandler::EmailConnectorExceptionToString(class [mscorlib]System.Exception e, valuetype [mscorlib]System.Guid orgId)
0x6310c  stelem.ref
0x6310d  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.CrmProvider::HandleTrace(valuetype [System]System.Diagnostics.TraceLevel traceLevel, string format, object[] args)
0x63112  rethrow
0x63114  ldc.i4.1
0x63115  ldarg.0
0x63116  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext Microsoft.Crm.Asynchronous.EmailConnector.CrmProvider::_context
0x6311b  ldstr    aCreateexceptio// "CreateExceptionRequest"
0x63120  ldstr    aRecurringappoi// "RecurringAppointment"
0x63125  ldstr    aCreateexceptio_0// "CreateException"
0x6312a  ldstr    asc_8A7C2// ""
0x6312f  call     void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncUtility::WriteCrmServiceExecuteEvent(valuetype Microsoft.Crm.Asynchronous.EmailConnector.EtwLogType etwLogType, class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext context, string requestName, string entityType, string functionName, [opt] string functionParam)
0x63134  endfinally
0x63135  ldloc.s  5
0x63137  ret
```
