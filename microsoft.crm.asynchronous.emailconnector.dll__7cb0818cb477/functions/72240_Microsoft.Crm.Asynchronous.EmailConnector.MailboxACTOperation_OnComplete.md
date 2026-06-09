# Microsoft.Crm.Asynchronous.EmailConnector.MailboxACTOperation::OnComplete

- ea: `0x72240`
- end: `0x7237b`
- name: `Microsoft.Crm.Asynchronous.EmailConnector.MailboxACTOperation::OnComplete`
- size: `315`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x72380`

## callees

- `0x3a60`
- `0x4d560`
- `0x4d6c0`
- `0x4d810`
- `0x4d8c0`
- `0x4da80`
- `0x55bb0`
- `0x55bc0`
- `0x55c40`
- `0x71a80`
- `0x71c20`
- `0x71d00`
- `0x71e10`
- `0x72240`
- `0x72490`

## string_xrefs

- `0x722f8`: `Server-Side Synchronization: ACT Average Processing Duration`
- `0x72303`: `Server-Side Synchronization: ACT Average Processing Duration Base`
- `0x7230d`: `Server-Side Synchronization: ACT Processing Last Duration`
- `0x72318`: `Server-Side Synchronization: Mailboxes processed for ACT`

## pseudocode

```c

```

## disassembly

```asm
0x72240  ldarg.0
0x72241  ldfld    class [System]System.Diagnostics.Stopwatch Microsoft.Crm.Asynchronous.EmailConnector.MailboxACTOperation::_mailboxLatency
0x72246  callvirt instance void [System]System.Diagnostics.Stopwatch::Stop()
0x7224b  ldarg.0
0x7224c  ldfld    class [System]System.Diagnostics.Stopwatch Microsoft.Crm.Asynchronous.EmailConnector.MailboxACTOperation::_mailboxLatency
0x72251  callvirt instance int64 [System]System.Diagnostics.Stopwatch::get_ElapsedMilliseconds()
0x72256  stloc.0
0x72257  ldarg.0
0x72258  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.Mailbox Microsoft.Crm.Asynchronous.EmailConnector.MailboxACTOperation::get_Mailbox()
0x7225d  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.EmailConnector.Mailbox::get_OrganizationId()
0x72262  stloc.2
0x72263  ldloca.s 2
0x72265  constrained. [mscorlib]System.Guid
0x7226b  callvirt instance string [mscorlib]System.Object::ToString()
0x72270  ldarg.0
0x72271  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.Mailbox Microsoft.Crm.Asynchronous.EmailConnector.MailboxACTOperation::get_Mailbox()
0x72276  ldstr    aMailboxid// "mailboxid"
0x7227b  callvirt instance object Microsoft.Crm.Asynchronous.EmailConnector.Mailbox::get_Item(string attributeName)
0x72280  callvirt instance string [mscorlib]System.Object::ToString()
0x72285  dup
0x72286  brtrue.s loc_7228E
0x72288  pop
0x72289  ldsfld   string [mscorlib]System.String::Empty
0x7228e  ldloca.s 0
0x72290  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x72295  call     instance string [mscorlib]System.Int64::ToString(class [mscorlib]System.IFormatProvider)
0x7229a  ldarg.0
0x7229b  ldfld    string Microsoft.Crm.Asynchronous.EmailConnector.MailboxACTOperation::_individualStepDuration
0x722a0  dup
0x722a1  brtrue.s loc_722A9
0x722a3  pop
0x722a4  ldsfld   string [mscorlib]System.String::Empty
0x722a9  call     bool Microsoft.Crm.Performance.Instrumentation.CrmEtwProvider::EventWriteExchangeSyncProcessDurationStop(string organizationId, string mailboxId, string TotalDuration, string IndividualDuration)
0x722ae  pop
0x722af  ldarg.0
0x722b0  ldfld    class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, class [Microsoft.Dynamics.Telemetry]Microsoft.Dynamics.Telemetry.IJsonValueFormat>> Microsoft.Crm.Asynchronous.EmailConnector.MailboxACTOperation::actProviderInfoLevelPayloadLists
0x722b5  call     class Microsoft.Crm.Asynchronous.EmailConnector.MailboxTelemetryEvents Microsoft.Crm.Asynchronous.EmailConnector.MailboxTelemetryEvents::get_Instance()
0x722ba  ldarg.0
0x722bb  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.Mailbox Microsoft.Crm.Asynchronous.EmailConnector.MailboxACTOperation::get_Mailbox()
0x722c0  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, class [Microsoft.Dynamics.Telemetry]Microsoft.Dynamics.Telemetry.IJsonValueFormat>> Microsoft.Crm.Asynchronous.EmailConnector.MailboxTelemetryEvents::GetActSyncPayloadData(class Microsoft.Crm.Asynchronous.EmailConnector.Mailbox mailbox)
0x722c5  call     T0x2B0000C4
0x722ca  call     T0x2B0000C5
0x722cf  stloc.1
0x722d0  call     class Microsoft.Crm.Asynchronous.EmailConnector.MailboxTelemetryEvents Microsoft.Crm.Asynchronous.EmailConnector.MailboxTelemetryEvents::get_Instance()
0x722d5  ldarg.0
0x722d6  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.Mailbox Microsoft.Crm.Asynchronous.EmailConnector.MailboxACTOperation::get_Mailbox()
0x722db  ldsfld   string Microsoft.Crm.Asynchronous.EmailConnector.MailboxEventName::ActSyncCompleted
0x722e0  ldloc.0
0x722e1  ldarg.0
0x722e2  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.Mailbox Microsoft.Crm.Asynchronous.EmailConnector.MailboxACTOperation::get_Mailbox()
0x722e7  callvirt instance valuetype [mscorlib]System.DateTime Microsoft.Crm.Asynchronous.EmailConnector.Mailbox::get_LastSyncStartedOnForACT()
0x722ec  ldloc.1
0x722ed  ldarg.0
0x722ee  ldfld    class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, class [Microsoft.Dynamics.Telemetry]Microsoft.Dynamics.Telemetry.IJsonValueFormat>> Microsoft.Crm.Asynchronous.EmailConnector.MailboxACTOperation::actProviderStepDurationLists
0x722f3  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.MailboxTelemetryEvents::WriteMailboxDataEvent(class Microsoft.Crm.Asynchronous.EmailConnector.Mailbox mailbox, string eventName, int64 executionTimeMilliseconds, valuetype [mscorlib]System.DateTime startTime, class [mscorlib]System.Collections.Generic.IEnumerable`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, class [Microsoft.Dynamics.Telemetry]Microsoft.Dynamics.Telemetry.IJsonValueFormat>> infoLevelPayload, class [mscorlib]System.Collections.Generic.IEnumerable`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, class [Microsoft.Dynamics.Telemetry]Microsoft.Dynamics.Telemetry.IJsonValueFormat>> stepExecutionTimes)
0x722f8  ldstr    aServerSideSync_100// "Server-Side Synchronization: ACT Averag"...
0x722fd  ldloc.0
0x722fe  call     void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncPerformanceCounters::IncrementPerformanceCounter(string performanceCounterName, int64 increment)
0x72303  ldstr    aServerSideSync_101// "Server-Side Synchronization: ACT Averag"...
0x72308  call     void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncPerformanceCounters::IncrementPerformanceCounter(string performanceCounterName)
0x7230d  ldstr    aServerSideSync_102// "Server-Side Synchronization: ACT Proces"...
0x72312  ldloc.0
0x72313  call     void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncPerformanceCounters::SetPerformanceCounter(string performanceCounterName, int64 newValue)
0x72318  ldstr    aServerSideSync_103// "Server-Side Synchronization: Mailboxes "...
0x7231d  call     void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncPerformanceCounters::IncrementPerformanceCounter(string performanceCounterName)
0x72322  ldarg.0
0x72323  ldfld    class [System]System.Diagnostics.Stopwatch Microsoft.Crm.Asynchronous.EmailConnector.MailboxACTOperation::_mailboxLatency
0x72328  callvirt instance void [System]System.Diagnostics.Stopwatch::Reset()
0x7232d  leave.s  loc_7237A
0x7232f  stloc.3
0x72330  ldarg.0
0x72331  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.Mailbox Microsoft.Crm.Asynchronous.EmailConnector.MailboxACTOperation::get_Mailbox()
0x72336  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.EmailConnector.Mailbox::get_OrganizationId()
0x7233b  ldarg.0
0x7233c  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.Mailbox Microsoft.Crm.Asynchronous.EmailConnector.MailboxACTOperation::get_Mailbox()
0x72341  ldarg.0
0x72342  call     instance var<u1> class Microsoft.Crm.Asynchronous.EmailConnector.MailboxOperationBase`1<class Microsoft.Crm.Asynchronous.EmailConnector.IMailboxOperationContext>::get_Context()
0x72347  callvirt instance class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IAsyncEvent Microsoft.Crm.Asynchronous.EmailConnector.IMailboxOperationContext::get_AsyncEvent()
0x7234c  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IAsyncEvent::get_EventId()
0x72351  ldc.i4.s 0x3C
0x72353  ldc.i4.1
0x72354  ldstr    aEtwInstrumenta_0// "ETW instrumentation (ExchangeSyncProces"...
0x72359  ldc.i4.1
0x7235a  newarr   [mscorlib]System.Object
0x7235f  dup
0x72360  ldc.i4.0
0x72361  ldloc.3
0x72362  ldarg.0
0x72363  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.Mailbox Microsoft.Crm.Asynchronous.EmailConnector.MailboxACTOperation::get_Mailbox()
0x72368  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.EmailConnector.Mailbox::get_OrganizationId()
0x7236d  call     string Microsoft.Crm.Asynchronous.EmailConnector.EmailConnectorTraceHandler::EmailConnectorExceptionToString(class [mscorlib]System.Exception e, valuetype [mscorlib]System.Guid orgId)
0x72372  stelem.ref
0x72373  call     void Microsoft.Crm.Asynchronous.EmailConnector.EmailConnectorTraceHandler::EmailConnectorTraceFormat(valuetype [mscorlib]System.Guid orgId, object mailbox, valuetype [mscorlib]System.Guid asyncEventId, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory traceCategory, valuetype [System]System.Diagnostics.TraceLevel traceLevel, string format, object[] args)
0x72378  leave.s  loc_7237A
0x7237a  ret
```
