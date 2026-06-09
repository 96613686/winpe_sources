# Microsoft.Crm.Extensibility.OData.ActionController::AddRequestInfoToTelemetry

- ea: `0x10c20`
- end: `0x10cc8`
- name: `Microsoft.Crm.Extensibility.OData.ActionController::AddRequestInfoToTelemetry`
- size: `168`
- prototype: ``
- caller_count: `6`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x31670`
- `0x316e0`
- `0x31750`
- `0x317e0`
- `0x31840`
- `0x318b0`

## callees

- `0x10c20`

## string_xrefs

- `0x10c5f`: `RequestUri`

## pseudocode

```c

```

## disassembly

```asm
0x10c20  ldarg.0
0x10c21  call     instance class [System.Net.Http]System.Net.Http.HttpRequestMessage [System.Web.Http]System.Web.Http.ApiController::get_Request()
0x10c26  brfalse.s loc_10CA2
0x10c28  ldstr    aMethodname// "methodName"
0x10c2d  ldarg.1
0x10c2e  call     void [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryContext::AddCustomProperty(string, string)
0x10c33  ldstr    aOperationname// "operationName"
0x10c38  ldarg.2
0x10c39  call     void [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryContext::AddCustomProperty(string, string)
0x10c3e  ldstr    aMethod// "Method"
0x10c43  ldarg.0
0x10c44  call     instance class [System.Net.Http]System.Net.Http.HttpRequestMessage [System.Web.Http]System.Web.Http.ApiController::get_Request()
0x10c49  callvirt instance class [System.Net.Http]System.Net.Http.HttpMethod [System.Net.Http]System.Net.Http.HttpRequestMessage::get_Method()
0x10c4e  dup
0x10c4f  brtrue.s loc_10C55
0x10c51  pop
0x10c52  ldnull
0x10c53  br.s     loc_10C5A
0x10c55  callvirt instance string [mscorlib]System.Object::ToString()
0x10c5a  call     void [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryContext::AddCustomProperty(string, string)
0x10c5f  ldstr    aRequesturi// "RequestUri"
0x10c64  ldarg.0
0x10c65  call     instance class [System.Net.Http]System.Net.Http.HttpRequestMessage [System.Web.Http]System.Web.Http.ApiController::get_Request()
0x10c6a  callvirt instance class [System]System.Uri [System.Net.Http]System.Net.Http.HttpRequestMessage::get_RequestUri()
0x10c6f  dup
0x10c70  brtrue.s loc_10C76
0x10c72  pop
0x10c73  ldnull
0x10c74  br.s     loc_10C7B
0x10c76  callvirt instance string [mscorlib]System.Object::ToString()
0x10c7b  call     void [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryContext::AddCustomProperty(string, string)
0x10c80  ldstr    aVersion// "Version"
0x10c85  ldarg.0
0x10c86  call     instance class [System.Net.Http]System.Net.Http.HttpRequestMessage [System.Web.Http]System.Web.Http.ApiController::get_Request()
0x10c8b  callvirt instance class [mscorlib]System.Version [System.Net.Http]System.Net.Http.HttpRequestMessage::get_Version()
0x10c90  dup
0x10c91  brtrue.s loc_10C97
0x10c93  pop
0x10c94  ldnull
0x10c95  br.s     loc_10C9C
0x10c97  callvirt instance string [mscorlib]System.Object::ToString()
0x10c9c  call     void [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryContext::AddCustomProperty(string, string)
0x10ca1  ret
0x10ca2  ldsfld   class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger Microsoft.Crm.Extensibility.OData.ActionController::Logger
0x10ca7  ldstr    a01IsNull// "{0}.{1} is null"
0x10cac  ldc.i4.2
0x10cad  newarr   [mscorlib]System.Object
0x10cb2  dup
0x10cb3  ldc.i4.0
0x10cb4  ldstr    aActioncontroll// "ActionController"
0x10cb9  stelem.ref
0x10cba  dup
0x10cbb  ldc.i4.1
0x10cbc  ldstr    aRequest// "Request"
0x10cc1  stelem.ref
0x10cc2  call     void [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.LoggerExtensions::LogWarning(class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger, string, object[])
0x10cc7  ret
```
