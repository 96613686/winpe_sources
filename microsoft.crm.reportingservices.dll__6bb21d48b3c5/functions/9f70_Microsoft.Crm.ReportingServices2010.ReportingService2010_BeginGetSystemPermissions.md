# Microsoft.Crm.ReportingServices2010.ReportingService2010::BeginGetSystemPermissions

- ea: `0x9f70`
- end: `0x9f84`
- name: `Microsoft.Crm.ReportingServices2010.ReportingService2010::BeginGetSystemPermissions`
- size: `20`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## string_xrefs

- `0x9f71`: `GetSystemPermissions`

## pseudocode

```c

```

## disassembly

```asm
0x9f70  ldarg.0
0x9f71  ldstr    aGetsystempermi// "GetSystemPermissions"
0x9f76  ldc.i4.0
0x9f77  newarr   [mscorlib]System.Object
0x9f7c  ldarg.1
0x9f7d  ldarg.2
0x9f7e  call     instance class [mscorlib]System.IAsyncResult [System.Web.Services]System.Web.Services.Protocols.SoapHttpClientProtocol::BeginInvoke(string, object[], class [mscorlib]System.AsyncCallback, object)
0x9f83  ret
```
