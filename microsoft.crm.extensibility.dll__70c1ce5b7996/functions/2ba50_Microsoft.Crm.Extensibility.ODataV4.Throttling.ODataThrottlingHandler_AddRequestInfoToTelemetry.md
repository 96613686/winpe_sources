# Microsoft.Crm.Extensibility.ODataV4.Throttling.ODataThrottlingHandler::AddRequestInfoToTelemetry

- ea: `0x2ba50`
- end: `0x2bace`
- name: `Microsoft.Crm.Extensibility.ODataV4.Throttling.ODataThrottlingHandler::AddRequestInfoToTelemetry`
- size: `126`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x34900`

## callees

- `0x2ba50`

## string_xrefs

- `0x2ba6f`: `RequestUri`

## pseudocode

```c

```

## disassembly

```asm
0x2ba50  ldarg.1
0x2ba51  brfalse.s loc_2BAA8
0x2ba53  ldstr    aMethod// "Method"
0x2ba58  ldarg.1
0x2ba59  callvirt instance class [System.Net.Http]System.Net.Http.HttpMethod [System.Net.Http]System.Net.Http.HttpRequestMessage::get_Method()
0x2ba5e  dup
0x2ba5f  brtrue.s loc_2BA65
0x2ba61  pop
0x2ba62  ldnull
0x2ba63  br.s     loc_2BA6A
0x2ba65  callvirt instance string [mscorlib]System.Object::ToString()
0x2ba6a  call     void [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryContext::AddCustomProperty(string, string)
0x2ba6f  ldstr    aRequesturi// "RequestUri"
0x2ba74  ldarg.1
0x2ba75  callvirt instance class [System]System.Uri [System.Net.Http]System.Net.Http.HttpRequestMessage::get_RequestUri()
0x2ba7a  dup
0x2ba7b  brtrue.s loc_2BA81
0x2ba7d  pop
0x2ba7e  ldnull
0x2ba7f  br.s     loc_2BA86
0x2ba81  callvirt instance string [mscorlib]System.Object::ToString()
0x2ba86  call     void [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryContext::AddCustomProperty(string, string)
0x2ba8b  ldstr    aVersion// "Version"
0x2ba90  ldarg.1
0x2ba91  callvirt instance class [mscorlib]System.Version [System.Net.Http]System.Net.Http.HttpRequestMessage::get_Version()
0x2ba96  dup
0x2ba97  brtrue.s loc_2BA9D
0x2ba99  pop
0x2ba9a  ldnull
0x2ba9b  br.s     loc_2BAA2
0x2ba9d  callvirt instance string [mscorlib]System.Object::ToString()
0x2baa2  call     void [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryContext::AddCustomProperty(string, string)
0x2baa7  ret
0x2baa8  ldsfld   class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger Microsoft.Crm.Extensibility.ODataV4.Throttling.ODataThrottlingHandler::Logger
0x2baad  ldstr    a01IsNull// "{0}.{1} is null"
0x2bab2  ldc.i4.2
0x2bab3  newarr   [mscorlib]System.Object
0x2bab8  dup
0x2bab9  ldc.i4.0
0x2baba  ldstr    aOdatathrottlin_0// "ODataThrottlingHandler"
0x2babf  stelem.ref
0x2bac0  dup
0x2bac1  ldc.i4.1
0x2bac2  ldstr    aRequest_0// "request"
0x2bac7  stelem.ref
0x2bac8  call     void [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.LoggerExtensions::LogWarning(class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger, string, object[])
0x2bacd  ret
```
