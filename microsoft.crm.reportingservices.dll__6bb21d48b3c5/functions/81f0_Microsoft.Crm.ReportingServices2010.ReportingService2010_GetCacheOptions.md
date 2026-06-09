# Microsoft.Crm.ReportingServices2010.ReportingService2010::GetCacheOptions

- ea: `0x81f0`
- end: `0x8219`
- name: `Microsoft.Crm.ReportingServices2010.ReportingService2010::GetCacheOptions`
- size: `41`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## string_xrefs

- `0x81f1`: `GetCacheOptions`

## pseudocode

```c

```

## disassembly

```asm
0x81f0  ldarg.0
0x81f1  ldstr    aGetcacheoption// "GetCacheOptions"
0x81f6  ldc.i4.1
0x81f7  newarr   [mscorlib]System.Object
0x81fc  dup
0x81fd  ldc.i4.0
0x81fe  ldarg.1
0x81ff  stelem.ref
0x8200  call     instance object[] [System.Web.Services]System.Web.Services.Protocols.SoapHttpClientProtocol::Invoke(string, object[])
0x8205  stloc.0
0x8206  ldarg.2
0x8207  ldloc.0
0x8208  ldc.i4.1
0x8209  ldelem.ref
0x820a  castclass Microsoft.Crm.ReportingServices2010.ExpirationDefinition
0x820f  stind.ref
0x8210  ldloc.0
0x8211  ldc.i4.0
0x8212  ldelem.ref
0x8213  unbox.any [mscorlib]System.Boolean
0x8218  ret
```
