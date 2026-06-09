# Microsoft.Crm.ReportingServices.ReportingService::CreateReport

- ea: `0x11150`
- end: `0x11184`
- name: `Microsoft.Crm.ReportingServices.ReportingService::CreateReport`
- size: `52`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## string_xrefs

- `0x11151`: `CreateReport`

## pseudocode

```c

```

## disassembly

```asm
0x11150  ldarg.0
0x11151  ldstr    aCreatereport// "CreateReport"
0x11156  ldc.i4.5
0x11157  newarr   [mscorlib]System.Object
0x1115c  dup
0x1115d  ldc.i4.0
0x1115e  ldarg.1
0x1115f  stelem.ref
0x11160  dup
0x11161  ldc.i4.1
0x11162  ldarg.2
0x11163  stelem.ref
0x11164  dup
0x11165  ldc.i4.2
0x11166  ldarg.3
0x11167  box      [mscorlib]System.Boolean
0x1116c  stelem.ref
0x1116d  dup
0x1116e  ldc.i4.3
0x1116f  ldarg.s  4
0x11171  stelem.ref
0x11172  dup
0x11173  ldc.i4.4
0x11174  ldarg.s  5
0x11176  stelem.ref
0x11177  call     instance object[] [System.Web.Services]System.Web.Services.Protocols.SoapHttpClientProtocol::Invoke(string, object[])
0x1117c  ldc.i4.0
0x1117d  ldelem.ref
0x1117e  castclass class Microsoft.Crm.ReportingServices.Warning[]
0x11183  ret
```
