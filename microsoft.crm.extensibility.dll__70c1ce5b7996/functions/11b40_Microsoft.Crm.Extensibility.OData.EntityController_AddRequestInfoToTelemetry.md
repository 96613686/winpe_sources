# Microsoft.Crm.Extensibility.OData.EntityController::AddRequestInfoToTelemetry

- ea: `0x11b40`
- end: `0x11be8`
- name: `Microsoft.Crm.Extensibility.OData.EntityController::AddRequestInfoToTelemetry`
- size: `168`
- prototype: ``
- caller_count: `25`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x319b0`
- `0x31a00`
- `0x31a60`
- `0x31ac0`
- `0x31b10`
- `0x31b80`
- `0x31bd0`
- `0x31c30`
- `0x31c90`
- `0x31cf0`
- `0x31d50`
- `0x31db0`
- `0x31e10`
- `0x31e70`
- `0x31ed0`
- `0x31f30`
- `0x31f90`
- `0x31ff0`
- `0x32050`
- `0x320b0`
- `0x32110`
- `0x32170`
- `0x321d0`
- `0x32230`
- `0x322a0`

## callees

- `0x11b40`

## string_xrefs

- `0x11b7f`: `RequestUri`

## pseudocode

```c

```

## disassembly

```asm
0x11b40  ldarg.0
0x11b41  call     instance class [System.Net.Http]System.Net.Http.HttpRequestMessage [System.Web.Http]System.Web.Http.ApiController::get_Request()
0x11b46  brfalse.s loc_11BC2
0x11b48  ldstr    aMethodname// "methodName"
0x11b4d  ldarg.1
0x11b4e  call     void [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryContext::AddCustomProperty(string, string)
0x11b53  ldstr    aEntitysetname// "entitySetName"
0x11b58  ldarg.2
0x11b59  call     void [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryContext::AddCustomProperty(string, string)
0x11b5e  ldstr    aMethod// "Method"
0x11b63  ldarg.0
0x11b64  call     instance class [System.Net.Http]System.Net.Http.HttpRequestMessage [System.Web.Http]System.Web.Http.ApiController::get_Request()
0x11b69  callvirt instance class [System.Net.Http]System.Net.Http.HttpMethod [System.Net.Http]System.Net.Http.HttpRequestMessage::get_Method()
0x11b6e  dup
0x11b6f  brtrue.s loc_11B75
0x11b71  pop
0x11b72  ldnull
0x11b73  br.s     loc_11B7A
0x11b75  callvirt instance string [mscorlib]System.Object::ToString()
0x11b7a  call     void [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryContext::AddCustomProperty(string, string)
0x11b7f  ldstr    aRequesturi// "RequestUri"
0x11b84  ldarg.0
0x11b85  call     instance class [System.Net.Http]System.Net.Http.HttpRequestMessage [System.Web.Http]System.Web.Http.ApiController::get_Request()
0x11b8a  callvirt instance class [System]System.Uri [System.Net.Http]System.Net.Http.HttpRequestMessage::get_RequestUri()
0x11b8f  dup
0x11b90  brtrue.s loc_11B96
0x11b92  pop
0x11b93  ldnull
0x11b94  br.s     loc_11B9B
0x11b96  callvirt instance string [mscorlib]System.Object::ToString()
0x11b9b  call     void [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryContext::AddCustomProperty(string, string)
0x11ba0  ldstr    aVersion// "Version"
0x11ba5  ldarg.0
0x11ba6  call     instance class [System.Net.Http]System.Net.Http.HttpRequestMessage [System.Web.Http]System.Web.Http.ApiController::get_Request()
0x11bab  callvirt instance class [mscorlib]System.Version [System.Net.Http]System.Net.Http.HttpRequestMessage::get_Version()
0x11bb0  dup
0x11bb1  brtrue.s loc_11BB7
0x11bb3  pop
0x11bb4  ldnull
0x11bb5  br.s     loc_11BBC
0x11bb7  callvirt instance string [mscorlib]System.Object::ToString()
0x11bbc  call     void [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryContext::AddCustomProperty(string, string)
0x11bc1  ret
0x11bc2  ldsfld   class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger Microsoft.Crm.Extensibility.OData.EntityController::Logger
0x11bc7  ldstr    a01IsNull// "{0}.{1} is null"
0x11bcc  ldc.i4.2
0x11bcd  newarr   [mscorlib]System.Object
0x11bd2  dup
0x11bd3  ldc.i4.0
0x11bd4  ldstr    aEntitycontroll// "EntityController"
0x11bd9  stelem.ref
0x11bda  dup
0x11bdb  ldc.i4.1
0x11bdc  ldstr    aRequest// "Request"
0x11be1  stelem.ref
0x11be2  call     void [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.LoggerExtensions::LogWarning(class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger, string, object[])
0x11be7  ret
```
