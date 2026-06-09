# Microsoft.Crm.Asynchronous.EmailConnector.MimeEmailMessage::ValidateMessage

- ea: `0x30850`
- end: `0x3098f`
- name: `Microsoft.Crm.Asynchronous.EmailConnector.MimeEmailMessage::ValidateMessage`
- size: `319`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x39070`

## callees

- `0x30830`
- `0x30850`
- `0x309f0`
- `0x4da80`
- `0x4e480`
- `0x814f0`
- `0x81500`

## string_xrefs

- `0x3086e`: `Server-Side Synchronization (Incoming): Items Suspected`
- `0x308d5`: `Server-Side Synchronization (Incoming): Items Suspected`
- `0x30878`: `Server-Side Synchronization (Incoming): Items Suspected Throughput`
- `0x308df`: `Server-Side Synchronization (Incoming): Items Suspected Throughput`

## pseudocode

```c

```

## disassembly

```asm
0x30850  ldarg.1
0x30851  brfalse  loc_30974
0x30856  ldarg.0
0x30857  ldfld    class [CDOSYS]CDOSYS.Message Microsoft.Crm.Asynchronous.EmailConnector.MimeEmailMessage::envelopeMessage
0x3085c  callvirt instance class [CDOSYS]CDOSYS.IBodyParts [CDOSYS]CDOSYS.IMessage::get_Attachments()
0x30861  stloc.0
0x30862  ldloc.0
0x30863  brfalse.s loc_3086E
0x30865  ldc.i4.1
0x30866  ldloc.0
0x30867  callvirt instance int32 [CDOSYS]CDOSYS.IBodyParts::get_Count()
0x3086c  beq.s    loc_308AB
0x3086e  ldstr    aServerSideSync_4// "Server-Side Synchronization (Incoming):"...
0x30873  call     void Microsoft.Crm.Asynchronous.EmailConnector.EmailConnectorPerformanceCounters::IncrementPerformanceCounter(string performanceCounterName)
0x30878  ldstr    aServerSideSync_5// "Server-Side Synchronization (Incoming):"...
0x3087d  call     void Microsoft.Crm.Asynchronous.EmailConnector.EmailConnectorPerformanceCounters::IncrementPerformanceCounter(string performanceCounterName)
0x30882  ldstr    aForwardMailbox// "Forward-mailbox email with message id: "...
0x30887  ldarg.0
0x30888  call     instance string Microsoft.Crm.Asynchronous.EmailConnector.MimeEmailMessage::get_MessageId()
0x3088d  call     string [mscorlib]System.String::Format(string, object)
0x30892  stloc.2
0x30893  ldarg.0
0x30894  ldc.i4.2
0x30895  ldloc.2
0x30896  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.MimeEmailMessage::HandleTrace(valuetype [System]System.Diagnostics.TraceLevel traceLevel, string format)
0x3089b  ldarg.0
0x3089c  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.Common.ISyncResponseFactory Microsoft.Crm.Asynchronous.EmailConnector.MimeEmailMessage::syncResponseFactory
0x308a1  ldc.i4.s 0x12
0x308a3  ldloc.2
0x308a4  ldc.i4.1
0x308a5  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.Common.SyncResponse Microsoft.Crm.Asynchronous.EmailConnector.Common.ISyncResponseFactory::GetErrorSyncResponse(int32 traceCode, string traceData, valuetype Microsoft.Crm.Asynchronous.EmailConnector.Common.ChangeType changeType)
0x308aa  ret
0x308ab  ldarg.0
0x308ac  ldfld    class [CDOSYS]CDOSYS.Message Microsoft.Crm.Asynchronous.EmailConnector.MimeEmailMessage::envelopeMessage
0x308b1  callvirt instance class [CDOSYS]CDOSYS.IBodyParts [CDOSYS]CDOSYS.IMessage::get_Attachments()
0x308b6  ldc.i4.1
0x308b7  callvirt instance class [CDOSYS]CDOSYS.IBodyPart [CDOSYS]CDOSYS.IBodyParts::get_Item(int32)
0x308bc  stloc.1
0x308bd  ldloc.1
0x308be  callvirt instance string [CDOSYS]CDOSYS.IBodyPart::get_ContentMediaType()
0x308c3  callvirt instance string [mscorlib]System.String::Trim()
0x308c8  ldstr    aMessageRfc822// "message/rfc822"
0x308cd  ldc.i4.5
0x308ce  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x308d3  brfalse.s loc_30912
0x308d5  ldstr    aServerSideSync_4// "Server-Side Synchronization (Incoming):"...
0x308da  call     void Microsoft.Crm.Asynchronous.EmailConnector.EmailConnectorPerformanceCounters::IncrementPerformanceCounter(string performanceCounterName)
0x308df  ldstr    aServerSideSync_5// "Server-Side Synchronization (Incoming):"...
0x308e4  call     void Microsoft.Crm.Asynchronous.EmailConnector.EmailConnectorPerformanceCounters::IncrementPerformanceCounter(string performanceCounterName)
0x308e9  ldstr    aAttachmentForM// "Attachment for message id: {0} doesn't "...
0x308ee  ldarg.0
0x308ef  call     instance string Microsoft.Crm.Asynchronous.EmailConnector.MimeEmailMessage::get_MessageId()
0x308f4  call     string [mscorlib]System.String::Format(string, object)
0x308f9  stloc.3
0x308fa  ldarg.0
0x308fb  ldc.i4.2
0x308fc  ldloc.3
0x308fd  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.MimeEmailMessage::HandleTrace(valuetype [System]System.Diagnostics.TraceLevel traceLevel, string format)
0x30902  ldarg.0
0x30903  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.Common.ISyncResponseFactory Microsoft.Crm.Asynchronous.EmailConnector.MimeEmailMessage::syncResponseFactory
0x30908  ldc.i4.s 0x12
0x3090a  ldloc.3
0x3090b  ldc.i4.1
0x3090c  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.Common.SyncResponse Microsoft.Crm.Asynchronous.EmailConnector.Common.ISyncResponseFactory::GetErrorSyncResponse(int32 traceCode, string traceData, valuetype Microsoft.Crm.Asynchronous.EmailConnector.Common.ChangeType changeType)
0x30911  ret
0x30912  nop
0x30913  ldarg.0
0x30914  newobj   instance void [CDOSYS]CDOSYS.MessageClass::.ctor()
0x30919  stfld    class [CDOSYS]CDOSYS.Message Microsoft.Crm.Asynchronous.EmailConnector.MimeEmailMessage::message
0x3091e  ldarg.0
0x3091f  ldfld    class [CDOSYS]CDOSYS.Message Microsoft.Crm.Asynchronous.EmailConnector.MimeEmailMessage::message
0x30924  callvirt instance class [CDOSYS]CDOSYS.IDataSource [CDOSYS]CDOSYS.IMessage::get_DataSource()
0x30929  ldloc.1
0x3092a  ldstr    aIbodypart// "IBodyPart"
0x3092f  callvirt instance void [CDOSYS]CDOSYS.IDataSource::OpenObject(object, string)
0x30934  leave.s  loc_30974
0x30936  stloc.s  4
0x30938  ldstr    aExceptionWhile// "Exception while getting attachment for "...
0x3093d  ldarg.0
0x3093e  call     instance string Microsoft.Crm.Asynchronous.EmailConnector.MimeEmailMessage::get_MessageId()
0x30943  ldloc.s  4
0x30945  ldarg.0
0x30946  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.EmailConnector.MimeEmailMessage::organizationId
0x3094b  call     string Microsoft.Crm.Asynchronous.EmailConnector.EmailConnectorTraceHandler::EmailConnectorExceptionToString(class [mscorlib]System.Exception e, valuetype [mscorlib]System.Guid orgId)
0x30950  call     string [mscorlib]System.String::Format(string, object, object)
0x30955  stloc.s  5
0x30957  ldarg.0
0x30958  ldc.i4.1
0x30959  ldloc.s  5
0x3095b  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.MimeEmailMessage::HandleTrace(valuetype [System]System.Diagnostics.TraceLevel traceLevel, string format)
0x30960  ldarg.0
0x30961  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.Common.ISyncResponseFactory Microsoft.Crm.Asynchronous.EmailConnector.MimeEmailMessage::syncResponseFactory
0x30966  ldc.i4.s 0x12
0x30968  ldloc.s  5
0x3096a  ldc.i4.1
0x3096b  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.Common.SyncResponse Microsoft.Crm.Asynchronous.EmailConnector.Common.ISyncResponseFactory::GetErrorSyncResponse(int32 traceCode, string traceData, valuetype Microsoft.Crm.Asynchronous.EmailConnector.Common.ChangeType changeType)
0x30970  stloc.s  6
0x30972  leave.s  loc_3098C
0x30974  ldarg.0
0x30975  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.Common.ISyncResponseFactory Microsoft.Crm.Asynchronous.EmailConnector.MimeEmailMessage::syncResponseFactory
0x3097a  ldsfld   string [mscorlib]System.String::Empty
0x3097f  ldc.i4.1
0x30980  ldc.i4.0
0x30981  ldstr    asc_8A7C2// ""
0x30986  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.Common.SyncResponse Microsoft.Crm.Asynchronous.EmailConnector.Common.ISyncResponseFactory::GetSuccessSyncResponse(string traceData, valuetype Microsoft.Crm.Asynchronous.EmailConnector.Common.ChangeType changeTypeInCrm, [opt] int32 traceCode, [opt] string traceCodeString)
0x3098b  ret
0x3098c  ldloc.s  6
0x3098e  ret
```
