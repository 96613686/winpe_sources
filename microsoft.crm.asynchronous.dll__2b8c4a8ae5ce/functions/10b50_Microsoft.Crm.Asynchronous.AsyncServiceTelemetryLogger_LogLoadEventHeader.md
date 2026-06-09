# Microsoft.Crm.Asynchronous.AsyncServiceTelemetryLogger::LogLoadEventHeader

- ea: `0x10b50`
- end: `0x10ea0`
- name: `Microsoft.Crm.Asynchronous.AsyncServiceTelemetryLogger::LogLoadEventHeader`
- size: `848`
- prototype: ``
- caller_count: `1`
- callee_count: `18`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x16b90`

## callees

- `0x2cd0`
- `0x2d40`
- `0x2d50`
- `0x2d60`
- `0x2dc0`
- `0x2dd0`
- `0x2e40`
- `0x2e70`
- `0x5f40`
- `0x6010`
- `0x6050`
- `0x10b50`
- `0x11740`
- `0x118c0`
- `0x118d0`
- `0x121d0`
- `0x121e0`
- `0x12200`

## string_xrefs

- `0x10bb4`: `DependencyToken`
- `0x10bd3`: `CorrelationToken`
- `0x10c65`: `CreatedOnMs`
- `0x10cb1`: `OwningExtensionId`

## pseudocode

```c

```

## disassembly

```asm
0x10b50  call     class Microsoft.Crm.Asynchronous.AsyncServiceTelemetryLoggingEvaluator Microsoft.Crm.Asynchronous.AsyncServiceTelemetryLoggingEvaluator::get_Instance()
0x10b55  ldarg.1
0x10b56  callvirt instance bool Microsoft.Crm.Asynchronous.AsyncServiceTelemetryLoggingEvaluator::IsLoggingAllowedForEvent(class Microsoft.Crm.Asynchronous.IAsyncEvent asyncEvent)
0x10b5b  brtrue.s loc_10B5E
0x10b5d  ret
0x10b5e  call     class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, class [Microsoft.Dynamics.Telemetry]Microsoft.Dynamics.Telemetry.IJsonValueFormat>> Microsoft.Crm.Asynchronous.AsyncServiceTelemetryLogger::GetPayLoadStructure()
0x10b63  stloc.0
0x10b64  ldarg.1
0x10b65  isinst   Microsoft.Crm.Asynchronous.AsyncEvent
0x10b6a  stloc.1
0x10b6b  ldloc.1
0x10b6c  brfalse  loc_10E04
0x10b71  ldloc.0
0x10b72  ldstr    aOperationtype_0// "OperationType"
0x10b77  ldloc.1
0x10b78  callvirt instance int32 Microsoft.Crm.Asynchronous.AsyncEventBase::get_OperationType()
0x10b7d  call     class [Microsoft.Dynamics.Telemetry]Microsoft.Dynamics.Telemetry.IntJsonValueFormat [Microsoft.Dynamics.Telemetry]Microsoft.Dynamics.Telemetry.TelemetryExtensions::ToJsonValueFormat(int32)
0x10b82  call     T0x2B00002C
0x10b87  ldloc.0
0x10b88  ldstr    aJobsubtype// "JobSubType"
0x10b8d  ldloc.1
0x10b8e  callvirt instance int32 Microsoft.Crm.Asynchronous.AsyncEvent::get_Subtype()
0x10b93  call     class [Microsoft.Dynamics.Telemetry]Microsoft.Dynamics.Telemetry.IntJsonValueFormat [Microsoft.Dynamics.Telemetry]Microsoft.Dynamics.Telemetry.TelemetryExtensions::ToJsonValueFormat(int32)
0x10b98  call     T0x2B00002C
0x10b9d  ldloc.0
0x10b9e  ldstr    aIsrecurrenceev// "IsRecurrenceEvent"
0x10ba3  ldloc.1
0x10ba4  callvirt instance bool Microsoft.Crm.Asynchronous.AsyncEvent::get_IsRecurrenceEvent()
0x10ba9  call     class [Microsoft.Dynamics.Telemetry]Microsoft.Dynamics.Telemetry.BoolJsonValueFormat [Microsoft.Dynamics.Telemetry]Microsoft.Dynamics.Telemetry.TelemetryExtensions::ToJsonValueFormat(bool)
0x10bae  call     T0x2B00002B
0x10bb3  ldloc.0
0x10bb4  ldstr    aDependencytoke// "DependencyToken"
0x10bb9  ldloc.1
0x10bba  callvirt instance string Microsoft.Crm.Asynchronous.AsyncEvent::get_DependencyToken()
0x10bbf  dup
0x10bc0  brtrue.s loc_10BC8
0x10bc2  pop
0x10bc3  ldsfld   string [mscorlib]System.String::Empty
0x10bc8  call     class [Microsoft.Dynamics.Telemetry]Microsoft.Dynamics.Telemetry.StringJsonValueFormat [Microsoft.Dynamics.Telemetry]Microsoft.Dynamics.Telemetry.TelemetryExtensions::ToJsonValueFormat(string)
0x10bcd  call     T0x2B00002A
0x10bd2  ldloc.0
0x10bd3  ldstr    aCorrelationtok// "CorrelationToken"
0x10bd8  ldloc.1
0x10bd9  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CorrelationToken Microsoft.Crm.Asynchronous.AsyncEvent::get_CorrelationToken()
0x10bde  brfalse.s loc_10C01
0x10be0  ldloc.1
0x10be1  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CorrelationToken Microsoft.Crm.Asynchronous.AsyncEvent::get_CorrelationToken()
0x10be6  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CorrelationToken::get_CorrelationId()
0x10beb  stloc.s  4
0x10bed  ldloca.s 4
0x10bef  constrained. [mscorlib]System.Guid
0x10bf5  callvirt instance string [mscorlib]System.Object::ToString()
0x10bfa  call     class [Microsoft.Dynamics.Telemetry]Microsoft.Dynamics.Telemetry.StringJsonValueFormat [Microsoft.Dynamics.Telemetry]Microsoft.Dynamics.Telemetry.TelemetryExtensions::ToJsonValueFormat(string)
0x10bff  br.s     loc_10C1A
0x10c01  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x10c06  stloc.s  4
0x10c08  ldloca.s 4
0x10c0a  constrained. [mscorlib]System.Guid
0x10c10  callvirt instance string [mscorlib]System.Object::ToString()
0x10c15  call     class [Microsoft.Dynamics.Telemetry]Microsoft.Dynamics.Telemetry.StringJsonValueFormat [Microsoft.Dynamics.Telemetry]Microsoft.Dynamics.Telemetry.TelemetryExtensions::ToJsonValueFormat(string)
0x10c1a  call     T0x2B00002A
0x10c1f  ldloc.0
0x10c20  ldstr    aRecurrencestar// "RecurrenceStartTimeMs"
0x10c25  ldloc.1
0x10c26  callvirt instance valuetype [mscorlib]System.DateTime Microsoft.Crm.Asynchronous.AsyncEvent::get_RecurrenceStartTime()
0x10c2b  stloc.s  5
0x10c2d  ldloca.s 5
0x10c2f  call     instance int64 [mscorlib]System.DateTime::get_Ticks()
0x10c34  ldc.i4   0x2710
0x10c39  conv.i8
0x10c3a  div
0x10c3b  call     class [Microsoft.Dynamics.Telemetry]Microsoft.Dynamics.Telemetry.LongJsonValueFormat [Microsoft.Dynamics.Telemetry]Microsoft.Dynamics.Telemetry.TelemetryExtensions::ToJsonValueFormat(int64)
0x10c40  call     T0x2B00002D
0x10c45  ldloc.0
0x10c46  ldstr    aRecurrencepatt// "RecurrencePattern"
0x10c4b  ldloc.1
0x10c4c  callvirt instance string Microsoft.Crm.Asynchronous.AsyncEvent::get_RecurrencePattern()
0x10c51  dup
0x10c52  brtrue.s loc_10C5A
0x10c54  pop
0x10c55  ldsfld   string [mscorlib]System.String::Empty
0x10c5a  call     class [Microsoft.Dynamics.Telemetry]Microsoft.Dynamics.Telemetry.StringJsonValueFormat [Microsoft.Dynamics.Telemetry]Microsoft.Dynamics.Telemetry.TelemetryExtensions::ToJsonValueFormat(string)
0x10c5f  call     T0x2B00002A
0x10c64  ldloc.0
0x10c65  ldstr    aCreatedonms// "CreatedOnMs"
0x10c6a  ldloc.1
0x10c6b  callvirt instance valuetype [mscorlib]System.DateTime Microsoft.Crm.Asynchronous.AsyncEventBase::get_CreatedOn()
0x10c70  stloc.s  5
0x10c72  ldloca.s 5
0x10c74  call     instance int64 [mscorlib]System.DateTime::get_Ticks()
0x10c79  ldc.i4   0x2710
0x10c7e  conv.i8
0x10c7f  div
0x10c80  call     class [Microsoft.Dynamics.Telemetry]Microsoft.Dynamics.Telemetry.LongJsonValueFormat [Microsoft.Dynamics.Telemetry]Microsoft.Dynamics.Telemetry.TelemetryExtensions::ToJsonValueFormat(int64)
0x10c85  call     T0x2B00002D
0x10c8a  ldloc.0
0x10c8b  ldstr    aPostponeduntil// "PostponedUntilMs"
0x10c90  ldloc.1
0x10c91  callvirt instance valuetype [mscorlib]System.DateTime Microsoft.Crm.Asynchronous.AsyncEventBase::get_PostponeUntil()
0x10c96  stloc.s  5
0x10c98  ldloca.s 5
0x10c9a  call     instance int64 [mscorlib]System.DateTime::get_Ticks()
0x10c9f  ldc.i4   0x2710
0x10ca4  conv.i8
0x10ca5  div
0x10ca6  call     class [Microsoft.Dynamics.Telemetry]Microsoft.Dynamics.Telemetry.LongJsonValueFormat [Microsoft.Dynamics.Telemetry]Microsoft.Dynamics.Telemetry.TelemetryExtensions::ToJsonValueFormat(int64)
0x10cab  call     T0x2B00002D
0x10cb0  ldloc.0
0x10cb1  ldstr    aOwningextensio// "OwningExtensionId"
0x10cb6  ldloc.1
0x10cb7  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup Microsoft.Crm.Asynchronous.AsyncEvent::get_OwningExtension()
0x10cbc  brfalse.s loc_10CDF
0x10cbe  ldloc.1
0x10cbf  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup Microsoft.Crm.Asynchronous.AsyncEvent::get_OwningExtension()
0x10cc4  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmReference::get_Value()
0x10cc9  stloc.s  4
0x10ccb  ldloca.s 4
0x10ccd  constrained. [mscorlib]System.Guid
0x10cd3  callvirt instance string [mscorlib]System.Object::ToString()
0x10cd8  call     class [Microsoft.Dynamics.Telemetry]Microsoft.Dynamics.Telemetry.StringJsonValueFormat [Microsoft.Dynamics.Telemetry]Microsoft.Dynamics.Telemetry.TelemetryExtensions::ToJsonValueFormat(string)
0x10cdd  br.s     loc_10CF8
0x10cdf  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x10ce4  stloc.s  4
0x10ce6  ldloca.s 4
0x10ce8  constrained. [mscorlib]System.Guid
0x10cee  callvirt instance string [mscorlib]System.Object::ToString()
0x10cf3  call     class [Microsoft.Dynamics.Telemetry]Microsoft.Dynamics.Telemetry.StringJsonValueFormat [Microsoft.Dynamics.Telemetry]Microsoft.Dynamics.Telemetry.TelemetryExtensions::ToJsonValueFormat(string)
0x10cf8  call     T0x2B00002A
0x10cfd  ldloc.0
0x10cfe  ldstr    aRegardingobjec// "RegardingObjectId"
0x10d03  ldloc.1
0x10d04  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup Microsoft.Crm.Asynchronous.AsyncEvent::get_RegardingObject()
0x10d09  brfalse.s loc_10D2C
0x10d0b  ldloc.1
0x10d0c  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup Microsoft.Crm.Asynchronous.AsyncEvent::get_RegardingObject()
0x10d11  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmReference::get_Value()
0x10d16  stloc.s  4
0x10d18  ldloca.s 4
0x10d1a  constrained. [mscorlib]System.Guid
0x10d20  callvirt instance string [mscorlib]System.Object::ToString()
0x10d25  call     class [Microsoft.Dynamics.Telemetry]Microsoft.Dynamics.Telemetry.StringJsonValueFormat [Microsoft.Dynamics.Telemetry]Microsoft.Dynamics.Telemetry.TelemetryExtensions::ToJsonValueFormat(string)
0x10d2a  br.s     loc_10D45
0x10d2c  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x10d31  stloc.s  4
0x10d33  ldloca.s 4
0x10d35  constrained. [mscorlib]System.Guid
0x10d3b  callvirt instance string [mscorlib]System.Object::ToString()
0x10d40  call     class [Microsoft.Dynamics.Telemetry]Microsoft.Dynamics.Telemetry.StringJsonValueFormat [Microsoft.Dynamics.Telemetry]Microsoft.Dynamics.Telemetry.TelemetryExtensions::ToJsonValueFormat(string)
0x10d45  call     T0x2B00002A
0x10d4a  ldloc.1
0x10d4b  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup Microsoft.Crm.Asynchronous.AsyncEvent::get_RegardingObject()
0x10d50  brfalse.s loc_10D6C
0x10d52  ldloc.1
0x10d53  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup Microsoft.Crm.Asynchronous.AsyncEvent::get_RegardingObject()
0x10d58  callvirt instance string [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmReference::get_type()
0x10d5d  brfalse.s loc_10D6C
0x10d5f  ldloc.1
0x10d60  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup Microsoft.Crm.Asynchronous.AsyncEvent::get_RegardingObject()
0x10d65  callvirt instance string [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmReference::get_type()
0x10d6a  br.s     loc_10D71
0x10d6c  ldsfld   string [mscorlib]System.String::Empty
0x10d71  call     class [Microsoft.Dynamics.Telemetry]Microsoft.Dynamics.Telemetry.StringJsonValueFormat [Microsoft.Dynamics.Telemetry]Microsoft.Dynamics.Telemetry.TelemetryExtensions::ToJsonValueFormat(string)
0x10d76  stloc.3
0x10d77  ldloc.0
0x10d78  ldstr    aRegardingobjec_0// "RegardingObjectType"
0x10d7d  ldloc.3
0x10d7e  call     T0x2B00002A
0x10d83  ldloc.1
0x10d84  callvirt instance valuetype [mscorlib]System.DateTime Microsoft.Crm.Asynchronous.AsyncEventBase::get_PostponeUntil()
0x10d89  ldsfld   valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::MaxValue
0x10d8e  call     bool [mscorlib]System.DateTime::op_Inequality(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x10d93  brfalse  loc_10E1F
0x10d98  ldloc.1
0x10d99  callvirt instance valuetype [mscorlib]System.DateTime Microsoft.Crm.Asynchronous.AsyncEventBase::get_PostponeUntil()
0x10d9e  ldsfld   valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::MinValue
0x10da3  call     bool [mscorlib]System.DateTime::op_GreaterThan(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x10da8  brfalse.s loc_10DCE
0x10daa  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x10daf  ldloc.1
0x10db0  callvirt instance valuetype [mscorlib]System.DateTime Microsoft.Crm.Asynchronous.AsyncEventBase::get_PostponeUntil()
0x10db5  call     valuetype [mscorlib]System.TimeSpan [mscorlib]System.DateTime::op_Subtraction(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x10dba  stloc.s  7
0x10dbc  ldloca.s 7
0x10dbe  call     instance int64 [mscorlib]System.TimeSpan::get_Ticks()
0x10dc3  ldc.i4   0x2710
0x10dc8  conv.i8
0x10dc9  div
0x10dca  stloc.s  6
0x10dcc  br.s     loc_10DF0
0x10dce  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x10dd3  ldloc.1
0x10dd4  callvirt instance valuetype [mscorlib]System.DateTime Microsoft.Crm.Asynchronous.AsyncEventBase::get_CreatedOn()
0x10dd9  call     valuetype [mscorlib]System.TimeSpan [mscorlib]System.DateTime::op_Subtraction(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x10dde  stloc.s  7
0x10de0  ldloca.s 7
0x10de2  call     instance int64 [mscorlib]System.TimeSpan::get_Ticks()
0x10de7  ldc.i4   0x2710
0x10dec  conv.i8
0x10ded  div
0x10dee  stloc.s  6
0x10df0  ldloc.0
0x10df1  ldstr    aCurrentloaddel// "CurrentLoadDelayMs"
0x10df6  ldloc.s  6
0x10df8  call     class [Microsoft.Dynamics.Telemetry]Microsoft.Dynamics.Telemetry.LongJsonValueFormat [Microsoft.Dynamics.Telemetry]Microsoft.Dynamics.Telemetry.TelemetryExtensions::ToJsonValueFormat(int64)
0x10dfd  call     T0x2B00002D
0x10e02  br.s     loc_10E1F
0x10e04  ldloc.0
0x10e05  ldstr    aAsynceventtype// "AsyncEventType"
0x10e0a  ldarg.1
0x10e0b  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x10e10  callvirt instance string [mscorlib]System.Object::ToString()
0x10e15  call     class [Microsoft.Dynamics.Telemetry]Microsoft.Dynamics.Telemetry.StringJsonValueFormat [Microsoft.Dynamics.Telemetry]Microsoft.Dynamics.Telemetry.TelemetryExtensions::ToJsonValueFormat(string)
0x10e1a  call     T0x2B00002A
0x10e1f  newobj   instance void [Microsoft.Dynamics.Telemetry]Microsoft.Dynamics.Telemetry.TelemetryEventHeader::.ctor()
0x10e24  dup
0x10e25  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x10e2a  callvirt instance void [Microsoft.Dynamics.Telemetry]Microsoft.Dynamics.Telemetry.TelemetryEventBase::set_StartTime(valuetype [mscorlib]System.DateTime)
0x10e2f  dup
0x10e30  ldarg.1
0x10e31  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.IAsyncEvent::get_EventId()
0x10e36  callvirt instance void [Microsoft.Dynamics.Telemetry]Microsoft.Dynamics.Telemetry.TelemetryEventHeader::set_RelatedActivityId(valuetype [mscorlib]System.Guid)
0x10e3b  dup
0x10e3c  ldarg.1
0x10e3d  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.IAsyncEvent::get_OrganizationId()
0x10e42  callvirt instance void [Microsoft.Dynamics.Telemetry]Microsoft.Dynamics.Telemetry.TelemetryEventHeader::set_OrganizationId(valuetype [mscorlib]System.Guid)
0x10e47  dup
0x10e48  ldloc.0
0x10e49  callvirt instance void [Microsoft.Dynamics.Telemetry]Microsoft.Dynamics.Telemetry.TelemetryEventBase::set_EventPayload(class [mscorlib]System.Collections.Generic.IEnumerable`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, class [Microsoft.Dynamics.Telemetry]Microsoft.Dynamics.Telemetry.IJsonValueFormat>>)
0x10e4e  dup
0x10e4f  ldc.i4.2
0x10e50  callvirt instance void [Microsoft.Dynamics.Telemetry]Microsoft.Dynamics.Telemetry.TelemetryEventBase::set_PayloadType(valuetype [Microsoft.Dynamics.Telemetry]Microsoft.Dynamics.Telemetry.PayloadType)
0x10e55  dup
0x10e56  ldstr    aAsync// "Async"
0x10e5b  callvirt instance void [Microsoft.Dynamics.Telemetry]Microsoft.Dynamics.Telemetry.TelemetryEventHeader::set_ClientType(string)
0x10e60  dup
0x10e61  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.CrmTelemetryContext::.ctor()
0x10e66  dup
0x10e67  ldarg.1
0x10e68  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.IAsyncEvent::get_OrganizationId()
0x10e6d  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.CrmTelemetryContext::set_OrganizationId(valuetype [mscorlib]System.Guid)
0x10e72  callvirt instance void [Microsoft.Dynamics.Telemetry]Microsoft.Dynamics.Telemetry.TelemetryEventBase::set_Context(class [Microsoft.Dynamics.Telemetry]Microsoft.Dynamics.Telemetry.ITelemetryContext)
0x10e77  stloc.2
0x10e78  call     class [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.CrmTelemetryManager [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.CrmTelemetryManager::get_Instance()
0x10e7d  newobj   instance void [Microsoft.Dynamics.Telemetry]Microsoft.Dynamics.Telemetry.TelemetryActivity::.ctor()
0x10e82  dup
0x10e83  ldarg.1
0x10e84  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.IAsyncEvent::get_TelemetryActivityId()
0x10e89  callvirt instance void [Microsoft.Dynamics.Telemetry]Microsoft.Dynamics.Telemetry.TelemetryActivity::set_Id(valuetype [mscorlib]System.Guid)
0x10e8e  dup
0x10e8f  ldstr    aAsyncoperation_0// "AsyncOperation"
0x10e94  callvirt instance void [Microsoft.Dynamics.Telemetry]Microsoft.Dynamics.Telemetry.TelemetryActivity::set_Name(string)
0x10e99  ldloc.2
0x10e9a  callvirt instance void [Microsoft.Dynamics.Telemetry]Microsoft.Dynamics.Telemetry.TelemetryManager::StartActivity(class [Microsoft.Dynamics.Telemetry]Microsoft.Dynamics.Telemetry.ITelemetryActivity, class [Microsoft.Dynamics.Telemetry]Microsoft.Dynamics.Telemetry.TelemetryEventHeader)
0x10e9f  ret
```
