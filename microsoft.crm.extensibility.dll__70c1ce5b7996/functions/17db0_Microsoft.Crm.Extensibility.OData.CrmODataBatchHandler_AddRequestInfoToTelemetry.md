# Microsoft.Crm.Extensibility.OData.CrmODataBatchHandler::AddRequestInfoToTelemetry

- ea: `0x17db0`
- end: `0x17e39`
- name: `Microsoft.Crm.Extensibility.OData.CrmODataBatchHandler::AddRequestInfoToTelemetry`
- size: `137`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x35210`

## callees

- `0x17db0`

## string_xrefs

- `0x17dda`: `RequestUri`

## pseudocode

```c

```

## disassembly

```asm
0x17db0  ldarg.2
0x17db1  brfalse.s loc_17E13
0x17db3  ldstr    aMethodname// "methodName"
0x17db8  ldarg.1
0x17db9  call     void [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryContext::AddCustomProperty(string, string)
0x17dbe  ldstr    aMethod// "Method"
0x17dc3  ldarg.2
0x17dc4  callvirt instance class [System.Net.Http]System.Net.Http.HttpMethod [System.Net.Http]System.Net.Http.HttpRequestMessage::get_Method()
0x17dc9  dup
0x17dca  brtrue.s loc_17DD0
0x17dcc  pop
0x17dcd  ldnull
0x17dce  br.s     loc_17DD5
0x17dd0  callvirt instance string [mscorlib]System.Object::ToString()
0x17dd5  call     void [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryContext::AddCustomProperty(string, string)
0x17dda  ldstr    aRequesturi// "RequestUri"
0x17ddf  ldarg.2
0x17de0  callvirt instance class [System]System.Uri [System.Net.Http]System.Net.Http.HttpRequestMessage::get_RequestUri()
0x17de5  dup
0x17de6  brtrue.s loc_17DEC
0x17de8  pop
0x17de9  ldnull
0x17dea  br.s     loc_17DF1
0x17dec  callvirt instance string [mscorlib]System.Object::ToString()
0x17df1  call     void [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryContext::AddCustomProperty(string, string)
0x17df6  ldstr    aVersion// "Version"
0x17dfb  ldarg.2
0x17dfc  callvirt instance class [mscorlib]System.Version [System.Net.Http]System.Net.Http.HttpRequestMessage::get_Version()
0x17e01  dup
0x17e02  brtrue.s loc_17E08
0x17e04  pop
0x17e05  ldnull
0x17e06  br.s     loc_17E0D
0x17e08  callvirt instance string [mscorlib]System.Object::ToString()
0x17e0d  call     void [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryContext::AddCustomProperty(string, string)
0x17e12  ret
0x17e13  ldsfld   class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger Microsoft.Crm.Extensibility.OData.CrmODataBatchHandler::Logger
0x17e18  ldstr    a01IsNull// "{0}.{1} is null"
0x17e1d  ldc.i4.2
0x17e1e  newarr   [mscorlib]System.Object
0x17e23  dup
0x17e24  ldc.i4.0
0x17e25  ldstr    aCrmodatabatchh// "CrmODataBatchHandler"
0x17e2a  stelem.ref
0x17e2b  dup
0x17e2c  ldc.i4.1
0x17e2d  ldstr    aRequest_0// "request"
0x17e32  stelem.ref
0x17e33  call     void [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.LoggerExtensions::LogWarning(class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger, string, object[])
0x17e38  ret
```
