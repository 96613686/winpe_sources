# Microsoft.Crm.Asynchronous.AsyncServiceTelemetryFacade::InitializeTelemetryOperation

- ea: `0x10720`
- end: `0x1088f`
- name: `Microsoft.Crm.Asynchronous.AsyncServiceTelemetryFacade::InitializeTelemetryOperation`
- size: `367`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `service_task, broker_com_uri`

## callees

- `0x2d60`
- `0x2da0`
- `0x2e40`
- `0x2e70`
- `0x2ea0`
- `0x10720`
- `0x121d0`
- `0x121e0`
- `0x121f0`
- `0x14900`

## pseudocode

```c

```

## disassembly

```asm
0x10720  ldarg.1
0x10721  ldnull
0x10722  cgt.un
0x10724  ldarg.3
0x10725  ldnull
0x10726  cgt.un
0x10728  stloc.0
0x10729  brfalse.s loc_1072E
0x1072b  ldloc.0
0x1072c  brtrue.s loc_10730
0x1072e  ldnull
0x1072f  ret
0x10730  ldarg.3
0x10731  callvirt instance bool Microsoft.Crm.Asynchronous.ITelemetryOperationQualityOfServiceStrategy::Execute()
0x10736  brtrue.s loc_1073A
0x10738  ldnull
0x10739  ret
0x1073a  ldtoken  [Microsoft.Crm.Constants]Microsoft.Crm.AsyncOperationType
0x1073f  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x10744  stloc.1
0x10745  ldarg.1
0x10746  callvirt instance int32 Microsoft.Crm.Asynchronous.IAsyncEvent::get_OperationType()
0x1074b  stloc.2
0x1074c  ldloca.s 2
0x1074e  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x10753  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x10758  stloc.3
0x10759  ldarg.0
0x1075a  ldfld    class Microsoft.Crm.Asynchronous.IConstantFieldValueToFieldNameMapper Microsoft.Crm.Asynchronous.AsyncServiceTelemetryFacade::fieldValueToNameMapper
0x1075f  ldloc.1
0x10760  ldloc.2
0x10761  ldloc.3
0x10762  callvirt T0x2B000029
0x10767  stloc.s  4
0x10769  ldsfld   string [mscorlib]System.String::Empty
0x1076e  stloc.s  5
0x10770  ldarg.1
0x10771  isinst   Microsoft.Crm.Asynchronous.AsyncEvent
0x10776  stloc.s  6
0x10778  ldloc.s  6
0x1077a  brfalse.s loc_107A2
0x1077c  ldloc.s  6
0x1077e  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup Microsoft.Crm.Asynchronous.AsyncEvent::get_OwningExtension()
0x10783  brfalse.s loc_107A2
0x10785  ldloc.s  6
0x10787  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup Microsoft.Crm.Asynchronous.AsyncEvent::get_OwningExtension()
0x1078c  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmReference::get_Value()
0x10791  stloc.s  0xA
0x10793  ldloca.s 0xA
0x10795  constrained. [mscorlib]System.Guid
0x1079b  callvirt instance string [mscorlib]System.Object::ToString()
0x107a0  stloc.s  5
0x107a2  ldarg.0
0x107a3  ldfld    class [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.ITelemetryFacade Microsoft.Crm.Asynchronous.AsyncServiceTelemetryFacade::telemetryFacade
0x107a8  ldloc.s  4
0x107aa  ldarg.1
0x107ab  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.IAsyncEvent::get_EventId()
0x107b0  stloc.s  0xA
0x107b2  ldloca.s 0xA
0x107b4  constrained. [mscorlib]System.Guid
0x107ba  callvirt instance string [mscorlib]System.Object::ToString()
0x107bf  ldloc.s  5
0x107c1  ldloc.s  6
0x107c3  brfalse.s loc_107D7
0x107c5  ldloc.s  6
0x107c7  callvirt instance int32 Microsoft.Crm.Asynchronous.AsyncEvent::get_Subtype()
0x107cc  stloc.s  0xB
0x107ce  ldloca.s 0xB
0x107d0  call     instance string [mscorlib]System.Int32::ToString()
0x107d5  br.s     loc_107DC
0x107d7  ldsfld   string [mscorlib]System.String::Empty
0x107dc  ldloc.s  6
0x107de  brfalse.s loc_10806
0x107e0  ldloc.s  6
0x107e2  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CorrelationToken Microsoft.Crm.Asynchronous.AsyncEvent::get_CorrelationToken()
0x107e7  brfalse.s loc_10806
0x107e9  ldloc.s  6
0x107eb  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CorrelationToken Microsoft.Crm.Asynchronous.AsyncEvent::get_CorrelationToken()
0x107f0  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CorrelationToken::get_CorrelationId()
0x107f5  stloc.s  0xA
0x107f7  ldloca.s 0xA
0x107f9  constrained. [mscorlib]System.Guid
0x107ff  callvirt instance string [mscorlib]System.Object::ToString()
0x10804  br.s     loc_1080B
0x10806  ldsfld   string [mscorlib]System.String::Empty
0x1080b  ldloc.s  6
0x1080d  brfalse.s loc_10818
0x1080f  ldloc.s  6
0x10811  callvirt instance int32 Microsoft.Crm.Asynchronous.AsyncEvent::get_Depth()
0x10816  br.s     loc_10819
0x10818  ldc.i4.0
0x10819  ldloc.s  6
0x1081b  brfalse.s loc_10826
0x1081d  ldloc.s  6
0x1081f  callvirt instance int32 Microsoft.Crm.Asynchronous.AsyncEvent::get_RetryCount()
0x10824  br.s     loc_10827
0x10826  ldc.i4.0
0x10827  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.ITelemetryOperation [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.ITelemetryFacade::CreateExtendedAsyncOperation(string, string, string, string, string, int32, int32)
0x1082c  stloc.s  7
0x1082e  ldloc.s  7
0x10830  ldc.i4.1
0x10831  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.ITelemetryOperation::set_ApiType(valuetype [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.TelemetryOperationApiType)
0x10836  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1083b  ldstr    aAsync0Queue1// "Async {0}:Queue-{1}"
0x10840  ldc.i4.2
0x10841  newarr   [mscorlib]System.Object
0x10846  dup
0x10847  ldc.i4.0
0x10848  ldtoken  Microsoft.Crm.Asynchronous.AsyncServiceContext
0x1084d  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x10852  ldarg.2
0x10853  box      Microsoft.Crm.Asynchronous.AsyncServiceContext
0x10858  call     string [mscorlib]System.Enum::GetName(class [mscorlib]System.Type, object)
0x1085d  stelem.ref
0x1085e  dup
0x1085f  ldc.i4.1
0x10860  ldarg.s  4
0x10862  stelem.ref
0x10863  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x10868  stloc.s  8
0x1086a  ldarg.1
0x1086b  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.IAsyncEvent::get_OrganizationId()
0x10870  stloc.s  0xA
0x10872  ldloca.s 0xA
0x10874  constrained. [mscorlib]System.Guid
0x1087a  callvirt instance string [mscorlib]System.Object::ToString()
0x1087f  stloc.s  9
0x10881  ldloc.s  7
0x10883  ldloc.s  8
0x10885  ldloc.s  9
0x10887  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.ITelemetryOperation::MarkImpactsQualityOfService(string, string)
0x1088c  ldloc.s  7
0x1088e  ret
```
