# Microsoft.Crm.ReportingServices.ReportingService::BeginGetCacheOptions

- ea: `0x119f0`
- end: `0x11a08`
- name: `Microsoft.Crm.ReportingServices.ReportingService::BeginGetCacheOptions`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## string_xrefs

- `0x119f1`: `GetCacheOptions`

## pseudocode

```c

```

## disassembly

```asm
0x119f0  ldarg.0
0x119f1  ldstr    aGetcacheoption// "GetCacheOptions"
0x119f6  ldc.i4.1
0x119f7  newarr   [mscorlib]System.Object
0x119fc  dup
0x119fd  ldc.i4.0
0x119fe  ldarg.1
0x119ff  stelem.ref
0x11a00  ldarg.2
0x11a01  ldarg.3
0x11a02  call     instance class [mscorlib]System.IAsyncResult [System.Web.Services]System.Web.Services.Protocols.SoapHttpClientProtocol::BeginInvoke(string, object[], class [mscorlib]System.AsyncCallback, object)
0x11a07  ret
```
