# Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncErrorLogger::LogEmailStatsToExchangeSyncIdMapping

- ea: `0x30fd0`
- end: `0x310d4`
- name: `Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncErrorLogger::LogEmailStatsToExchangeSyncIdMapping`
- size: `260`
- prototype: ``
- caller_count: `0`
- callee_count: `16`
- tags: `broker_com_uri`

## callees

- `0x30fd0`
- `0x310e0`
- `0x31100`
- `0x31140`
- `0x4da80`
- `0x549e0`
- `0x54a20`
- `0x54a40`
- `0x54b30`
- `0x5aa60`
- `0x5aa70`
- `0x71300`
- `0x7a9d0`
- `0x7aa10`
- `0x7aa30`
- `0x815b0`

## string_xrefs

- `0x30fe7`: `Attempting to log item level stats for message id {0} to Id mapping.`
- `0x310b2`: `An error occurred when writing SSSIncomingEmailItemStats to Id mapping. Exception : {0}`

## pseudocode

```c

```

## disassembly

```asm
0x30fd0  ldarg.1
0x30fd1  brfalse.s loc_30FDB
0x30fd3  ldarg.0
0x30fd4  call     instance bool Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncErrorLogger::IsItemLevelMonitoringEnabled()
0x30fd9  brtrue.s loc_30FE0
0x30fdb  leave    loc_310D3
0x30fe0  ldarg.0
0x30fe1  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.ITraceHandler Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncErrorLogger::traceHandler
0x30fe6  ldc.i4.3
0x30fe7  ldstr    aAttemptingToLo// "Attempting to log item level stats for "...
0x30fec  ldc.i4.1
0x30fed  newarr   [mscorlib]System.Object
0x30ff2  dup
0x30ff3  ldc.i4.0
0x30ff4  ldarg.1
0x30ff5  callvirt instance string Microsoft.Crm.Asynchronous.EmailConnector.ItemStatEvents.ItemStatsBase::get_MessageId()
0x30ffa  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x30fff  brtrue.s loc_31009
0x31001  ldarg.1
0x31002  callvirt instance string Microsoft.Crm.Asynchronous.EmailConnector.ItemStatEvents.ItemStatsBase::get_MessageId()
0x31007  br.s     loc_3100E
0x31009  ldsfld   string [mscorlib]System.String::Empty
0x3100e  stelem.ref
0x3100f  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.ITraceHandler::HandleTrace(valuetype [System]System.Diagnostics.TraceLevel traceLevel, string format, object[] args)
0x31014  ldarg.0
0x31015  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IExchangeSyncIdMappingOperations Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncErrorLogger::exchangeSyncIdMappingOperations
0x3101a  ldarg.1
0x3101b  callvirt instance string Microsoft.Crm.Asynchronous.EmailConnector.ItemStatEvents.ItemStatsBase::get_MessageId()
0x31020  ldarg.1
0x31021  callvirt instance string Microsoft.Crm.Asynchronous.EmailConnector.ItemStatEvents.ItemStatsBase::get_CrmId()
0x31026  callvirt instance class [mscorlib]System.Collections.Generic.ICollection`1<class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncIdMappingEntityWrapper> Microsoft.Crm.Asynchronous.EmailConnector.IExchangeSyncIdMappingOperations::RetrieveExchangeSyncIdMappings(string exchangeEntryId, string crmId)
0x3102b  stloc.0
0x3102c  ldarg.0
0x3102d  ldarg.3
0x3102e  brtrue.s loc_31033
0x31030  ldc.i4.0
0x31031  br.s     loc_31039
0x31033  ldarg.3
0x31034  callvirt instance int32 Microsoft.Crm.Asynchronous.EmailConnector.Common.SyncResponse::get_TraceCode()
0x31039  call     instance bool Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncErrorLogger::IsTraceCodeToBeIgnored(int32 errorCode)
0x3103e  brfalse.s loc_3104C
0x31040  ldarg.0
0x31041  ldloc.0
0x31042  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncErrorLogger::DeleteExchangeSyncErrors(class [mscorlib]System.Collections.Generic.ICollection`1<class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncIdMappingEntityWrapper> exchangeSyncErrors)
0x31047  leave    loc_310D3
0x3104c  ldloc.0
0x3104d  call     T0x2B00006B
0x31052  brtrue.s loc_31064
0x31054  ldarg.0
0x31055  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IExchangeSyncErrorMapper Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncErrorLogger::exchangeSyncErrorMapper
0x3105a  ldarg.1
0x3105b  ldarg.2
0x3105c  ldarg.3
0x3105d  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncIdMappingEntityWrapper Microsoft.Crm.Asynchronous.EmailConnector.IExchangeSyncErrorMapper::MapEmailStatsToExchangeSyncError(class Microsoft.Crm.Asynchronous.EmailConnector.ItemStatEvents.ItemStatsBase itemStatsBase, valuetype Microsoft.Crm.Asynchronous.EmailConnector.Common.ChangeType changeType, class Microsoft.Crm.Asynchronous.EmailConnector.Common.SyncResponse syncResponse)
0x31062  br.s     loc_31078
0x31064  ldarg.0
0x31065  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IExchangeSyncErrorMapper Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncErrorLogger::exchangeSyncErrorMapper
0x3106a  ldloc.0
0x3106b  call     T0x2B00006C
0x31070  ldarg.1
0x31071  ldarg.2
0x31072  ldarg.3
0x31073  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncIdMappingEntityWrapper Microsoft.Crm.Asynchronous.EmailConnector.IExchangeSyncErrorMapper::MapEmailStatsToExchangeSyncError(class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncIdMappingEntityWrapper exchangeSyncError, class Microsoft.Crm.Asynchronous.EmailConnector.ItemStatEvents.ItemStatsBase itemStatsBase, valuetype Microsoft.Crm.Asynchronous.EmailConnector.Common.ChangeType changeType, class Microsoft.Crm.Asynchronous.EmailConnector.Common.SyncResponse syncResponse)
0x31078  stloc.1
0x31079  ldloc.1
0x3107a  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncIdMappingEntityWrapper::get_ExchangeSyncIdMappingId()
0x3107f  stloc.2
0x31080  ldloca.s 2
0x31082  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x31087  call     instance int32 [mscorlib]System.Guid::CompareTo(valuetype [mscorlib]System.Guid)
0x3108c  brtrue.s loc_3109C
0x3108e  ldarg.0
0x3108f  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IExchangeSyncIdMappingOperations Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncErrorLogger::exchangeSyncIdMappingOperations
0x31094  ldloc.1
0x31095  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.IExchangeSyncIdMappingOperations::AddExchangeSyncIdMappingError(class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncIdMappingEntityWrapper exchangeSyncIdMappingError)
0x3109a  br.s     loc_310A8
0x3109c  ldarg.0
0x3109d  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IExchangeSyncIdMappingOperations Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncErrorLogger::exchangeSyncIdMappingOperations
0x310a2  ldloc.1
0x310a3  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.IExchangeSyncIdMappingOperations::UpdateExchangeSyncIdMapping(class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncIdMappingEntityWrapper exchangeSyncIdMapping)
0x310a8  leave.s  loc_310D3
0x310aa  stloc.3
0x310ab  ldarg.0
0x310ac  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.ITraceHandler Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncErrorLogger::traceHandler
0x310b1  ldc.i4.1
0x310b2  ldstr    aAnErrorOccurre// "An error occurred when writing SSSIncom"...
0x310b7  ldc.i4.1
0x310b8  newarr   [mscorlib]System.Object
0x310bd  dup
0x310be  ldc.i4.0
0x310bf  ldloc.3
0x310c0  ldarg.1
0x310c1  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.EmailConnector.ItemStatEvents.ItemStatsBase::get_OrganizationId()
0x310c6  call     string Microsoft.Crm.Asynchronous.EmailConnector.EmailConnectorTraceHandler::EmailConnectorExceptionToString(class [mscorlib]System.Exception e, valuetype [mscorlib]System.Guid orgId)
0x310cb  stelem.ref
0x310cc  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.ITraceHandler::HandleTrace(valuetype [System]System.Diagnostics.TraceLevel traceLevel, string format, object[] args)
0x310d1  leave.s  loc_310D3
0x310d3  ret
```
