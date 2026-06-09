# Microsoft.Crm.ReportingServices2010.ReportingService2010::BeginGetCacheOptions

- ea: `0x8220`
- end: `0x8238`
- name: `Microsoft.Crm.ReportingServices2010.ReportingService2010::BeginGetCacheOptions`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## string_xrefs

- `0x8221`: `GetCacheOptions`

## pseudocode

```c

```

## disassembly

```asm
0x8220  ldarg.0
0x8221  ldstr    aGetcacheoption// "GetCacheOptions"
0x8226  ldc.i4.1
0x8227  newarr   [mscorlib]System.Object
0x822c  dup
0x822d  ldc.i4.0
0x822e  ldarg.1
0x822f  stelem.ref
0x8230  ldarg.2
0x8231  ldarg.3
0x8232  call     instance class [mscorlib]System.IAsyncResult [System.Web.Services]System.Web.Services.Protocols.SoapHttpClientProtocol::BeginInvoke(string, object[], class [mscorlib]System.AsyncCallback, object)
0x8237  ret
```
