# Microsoft.Crm.ReportingServices.ReportingService::GetCacheOptions

- ea: `0x119c0`
- end: `0x119e9`
- name: `Microsoft.Crm.ReportingServices.ReportingService::GetCacheOptions`
- size: `41`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## string_xrefs

- `0x119c1`: `GetCacheOptions`

## pseudocode

```c

```

## disassembly

```asm
0x119c0  ldarg.0
0x119c1  ldstr    aGetcacheoption// "GetCacheOptions"
0x119c6  ldc.i4.1
0x119c7  newarr   [mscorlib]System.Object
0x119cc  dup
0x119cd  ldc.i4.0
0x119ce  ldarg.1
0x119cf  stelem.ref
0x119d0  call     instance object[] [System.Web.Services]System.Web.Services.Protocols.SoapHttpClientProtocol::Invoke(string, object[])
0x119d5  stloc.0
0x119d6  ldarg.2
0x119d7  ldloc.0
0x119d8  ldc.i4.1
0x119d9  ldelem.ref
0x119da  castclass Microsoft.Crm.ReportingServices.ExpirationDefinition
0x119df  stind.ref
0x119e0  ldloc.0
0x119e1  ldc.i4.0
0x119e2  ldelem.ref
0x119e3  unbox.any [mscorlib]System.Boolean
0x119e8  ret
```
