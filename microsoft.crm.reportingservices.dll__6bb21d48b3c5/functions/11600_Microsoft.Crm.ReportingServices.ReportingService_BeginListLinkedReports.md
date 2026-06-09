# Microsoft.Crm.ReportingServices.ReportingService::BeginListLinkedReports

- ea: `0x11600`
- end: `0x11618`
- name: `Microsoft.Crm.ReportingServices.ReportingService::BeginListLinkedReports`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## string_xrefs

- `0x11601`: `ListLinkedReports`

## pseudocode

```c

```

## disassembly

```asm
0x11600  ldarg.0
0x11601  ldstr    aListlinkedrepo// "ListLinkedReports"
0x11606  ldc.i4.1
0x11607  newarr   [mscorlib]System.Object
0x1160c  dup
0x1160d  ldc.i4.0
0x1160e  ldarg.1
0x1160f  stelem.ref
0x11610  ldarg.2
0x11611  ldarg.3
0x11612  call     instance class [mscorlib]System.IAsyncResult [System.Web.Services]System.Web.Services.Protocols.SoapHttpClientProtocol::BeginInvoke(string, object[], class [mscorlib]System.AsyncCallback, object)
0x11617  ret
```
