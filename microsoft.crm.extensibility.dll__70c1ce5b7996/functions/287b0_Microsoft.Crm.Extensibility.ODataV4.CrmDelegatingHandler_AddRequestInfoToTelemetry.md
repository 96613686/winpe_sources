# Microsoft.Crm.Extensibility.ODataV4.CrmDelegatingHandler::AddRequestInfoToTelemetry

- ea: `0x287b0`
- end: `0x2882e`
- name: `Microsoft.Crm.Extensibility.ODataV4.CrmDelegatingHandler::AddRequestInfoToTelemetry`
- size: `126`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x35330`

## callees

- `0x287b0`

## string_xrefs

- `0x287cf`: `RequestUri`

## pseudocode

```c

```

## disassembly

```asm
0x287b0  ldarg.1
0x287b1  brfalse.s loc_28808
0x287b3  ldstr    aMethod// "Method"
0x287b8  ldarg.1
0x287b9  callvirt instance class [System.Net.Http]System.Net.Http.HttpMethod [System.Net.Http]System.Net.Http.HttpRequestMessage::get_Method()
0x287be  dup
0x287bf  brtrue.s loc_287C5
0x287c1  pop
0x287c2  ldnull
0x287c3  br.s     loc_287CA
0x287c5  callvirt instance string [mscorlib]System.Object::ToString()
0x287ca  call     void [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryContext::AddCustomProperty(string, string)
0x287cf  ldstr    aRequesturi// "RequestUri"
0x287d4  ldarg.1
0x287d5  callvirt instance class [System]System.Uri [System.Net.Http]System.Net.Http.HttpRequestMessage::get_RequestUri()
0x287da  dup
0x287db  brtrue.s loc_287E1
0x287dd  pop
0x287de  ldnull
0x287df  br.s     loc_287E6
0x287e1  callvirt instance string [mscorlib]System.Object::ToString()
0x287e6  call     void [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryContext::AddCustomProperty(string, string)
0x287eb  ldstr    aVersion// "Version"
0x287f0  ldarg.1
0x287f1  callvirt instance class [mscorlib]System.Version [System.Net.Http]System.Net.Http.HttpRequestMessage::get_Version()
0x287f6  dup
0x287f7  brtrue.s loc_287FD
0x287f9  pop
0x287fa  ldnull
0x287fb  br.s     loc_28802
0x287fd  callvirt instance string [mscorlib]System.Object::ToString()
0x28802  call     void [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryContext::AddCustomProperty(string, string)
0x28807  ret
0x28808  ldsfld   class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger Microsoft.Crm.Extensibility.ODataV4.CrmDelegatingHandler::Logger
0x2880d  ldstr    a01IsNull// "{0}.{1} is null"
0x28812  ldc.i4.2
0x28813  newarr   [mscorlib]System.Object
0x28818  dup
0x28819  ldc.i4.0
0x2881a  ldstr    aCrmdelegatingh// "CrmDelegatingHandler"
0x2881f  stelem.ref
0x28820  dup
0x28821  ldc.i4.1
0x28822  ldstr    aRequest_0// "request"
0x28827  stelem.ref
0x28828  call     void [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.LoggerExtensions::LogWarning(class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger, string, object[])
0x2882d  ret
```
