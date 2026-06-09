# Microsoft.Xrm.Tools.OwinJobManager.Server.WebapiExceptionLogger::Log

- ea: `0x12b0`
- end: `0x12dd`
- name: `Microsoft.Xrm.Tools.OwinJobManager.Server.WebapiExceptionLogger::Log`
- size: `45`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x12b0`
- `0x12e0`

## pseudocode

```c

```

## disassembly

```asm
0x12b0  ldstr    aRequest0Except// "Request: {0}, exception: {1}"
0x12b5  ldarg.1
0x12b6  callvirt instance class [System.Net.Http]System.Net.Http.HttpRequestMessage [System.Web.Http]System.Web.Http.ExceptionHandling.ExceptionLoggerContext::get_Request()
0x12bb  call     string Microsoft.Xrm.Tools.OwinJobManager.Server.WebapiExceptionLogger::RequestToString(class [System.Net.Http]System.Net.Http.HttpRequestMessage request)
0x12c0  ldarg.1
0x12c1  callvirt instance class [mscorlib]System.Exception [System.Web.Http]System.Web.Http.ExceptionHandling.ExceptionLoggerContext::get_Exception()
0x12c6  call     string [mscorlib]System.String::Format(string, object, object)
0x12cb  stloc.0
0x12cc  ldsfld   class [mscorlib]System.Action`1<string> Microsoft.Xrm.Tools.OwinJobManager.Server.WebapiExceptionLogger::Logger
0x12d1  dup
0x12d2  brtrue.s loc_12D6
0x12d4  pop
0x12d5  ret
0x12d6  ldloc.0
0x12d7  callvirt instance void class [mscorlib]System.Action`1<string>::Invoke(var<u1>)
0x12dc  ret
```
