# Microsoft.Crm.ReportingServices.ReportingService::BeginGetSystemPermissions

- ea: `0x13080`
- end: `0x13094`
- name: `Microsoft.Crm.ReportingServices.ReportingService::BeginGetSystemPermissions`
- size: `20`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## string_xrefs

- `0x13081`: `GetSystemPermissions`

## pseudocode

```c

```

## disassembly

```asm
0x13080  ldarg.0
0x13081  ldstr    aGetsystempermi// "GetSystemPermissions"
0x13086  ldc.i4.0
0x13087  newarr   [mscorlib]System.Object
0x1308c  ldarg.1
0x1308d  ldarg.2
0x1308e  call     instance class [mscorlib]System.IAsyncResult [System.Web.Services]System.Web.Services.Protocols.SoapHttpClientProtocol::BeginInvoke(string, object[], class [mscorlib]System.AsyncCallback, object)
0x13093  ret
```
