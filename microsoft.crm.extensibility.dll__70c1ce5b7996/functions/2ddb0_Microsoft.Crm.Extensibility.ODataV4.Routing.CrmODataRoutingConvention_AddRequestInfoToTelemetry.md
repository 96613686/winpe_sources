# Microsoft.Crm.Extensibility.ODataV4.Routing.CrmODataRoutingConvention::AddRequestInfoToTelemetry

- ea: `0x2ddb0`
- end: `0x2de4f`
- name: `Microsoft.Crm.Extensibility.ODataV4.Routing.CrmODataRoutingConvention::AddRequestInfoToTelemetry`
- size: `159`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x35050`
- `0x350b0`

## callees

- `0x2ddb0`

## string_xrefs

- `0x2ddf0`: `RequestUri`
- `0x2ddbe`: `odataPath`

## pseudocode

```c

```

## disassembly

```asm
0x2ddb0  ldarg.3
0x2ddb1  brfalse.s loc_2DE29
0x2ddb3  ldstr    aMethodname// "methodName"
0x2ddb8  ldarg.1
0x2ddb9  call     void [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryContext::AddCustomProperty(string, string)
0x2ddbe  ldstr    aOdatapath_0// "odataPath"
0x2ddc3  ldarg.2
0x2ddc4  brtrue.s loc_2DDC9
0x2ddc6  ldnull
0x2ddc7  br.s     loc_2DDCF
0x2ddc9  ldarg.2
0x2ddca  callvirt instance string [mscorlib]System.Object::ToString()
0x2ddcf  call     void [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryContext::AddCustomProperty(string, string)
0x2ddd4  ldstr    aMethod// "Method"
0x2ddd9  ldarg.3
0x2ddda  callvirt instance class [System.Net.Http]System.Net.Http.HttpMethod [System.Net.Http]System.Net.Http.HttpRequestMessage::get_Method()
0x2dddf  dup
0x2dde0  brtrue.s loc_2DDE6
0x2dde2  pop
0x2dde3  ldnull
0x2dde4  br.s     loc_2DDEB
0x2dde6  callvirt instance string [mscorlib]System.Object::ToString()
0x2ddeb  call     void [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryContext::AddCustomProperty(string, string)
0x2ddf0  ldstr    aRequesturi// "RequestUri"
0x2ddf5  ldarg.3
0x2ddf6  callvirt instance class [System]System.Uri [System.Net.Http]System.Net.Http.HttpRequestMessage::get_RequestUri()
0x2ddfb  dup
0x2ddfc  brtrue.s loc_2DE02
0x2ddfe  pop
0x2ddff  ldnull
0x2de00  br.s     loc_2DE07
0x2de02  callvirt instance string [mscorlib]System.Object::ToString()
0x2de07  call     void [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryContext::AddCustomProperty(string, string)
0x2de0c  ldstr    aVersion// "Version"
0x2de11  ldarg.3
0x2de12  callvirt instance class [mscorlib]System.Version [System.Net.Http]System.Net.Http.HttpRequestMessage::get_Version()
0x2de17  dup
0x2de18  brtrue.s loc_2DE1E
0x2de1a  pop
0x2de1b  ldnull
0x2de1c  br.s     loc_2DE23
0x2de1e  callvirt instance string [mscorlib]System.Object::ToString()
0x2de23  call     void [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryContext::AddCustomProperty(string, string)
0x2de28  ret
0x2de29  ldsfld   class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger Microsoft.Crm.Extensibility.ODataV4.Routing.CrmODataRoutingConvention::Logger
0x2de2e  ldstr    a01IsNull// "{0}.{1} is null"
0x2de33  ldc.i4.2
0x2de34  newarr   [mscorlib]System.Object
0x2de39  dup
0x2de3a  ldc.i4.0
0x2de3b  ldstr    aCrmodataroutin// "CrmODataRoutingConvention"
0x2de40  stelem.ref
0x2de41  dup
0x2de42  ldc.i4.1
0x2de43  ldstr    aRequest_0// "request"
0x2de48  stelem.ref
0x2de49  call     void [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.LoggerExtensions::LogWarning(class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger, string, object[])
0x2de4e  ret
```
