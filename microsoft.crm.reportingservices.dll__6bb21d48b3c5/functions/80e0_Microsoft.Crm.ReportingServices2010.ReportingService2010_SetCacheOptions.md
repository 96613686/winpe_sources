# Microsoft.Crm.ReportingServices2010.ReportingService2010::SetCacheOptions

- ea: `0x80e0`
- end: `0x8104`
- name: `Microsoft.Crm.ReportingServices2010.ReportingService2010::SetCacheOptions`
- size: `36`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## string_xrefs

- `0x80e1`: `SetCacheOptions`

## pseudocode

```c

```

## disassembly

```asm
0x80e0  ldarg.0
0x80e1  ldstr    aSetcacheoption// "SetCacheOptions"
0x80e6  ldc.i4.3
0x80e7  newarr   [mscorlib]System.Object
0x80ec  dup
0x80ed  ldc.i4.0
0x80ee  ldarg.1
0x80ef  stelem.ref
0x80f0  dup
0x80f1  ldc.i4.1
0x80f2  ldarg.2
0x80f3  box      [mscorlib]System.Boolean
0x80f8  stelem.ref
0x80f9  dup
0x80fa  ldc.i4.2
0x80fb  ldarg.3
0x80fc  stelem.ref
0x80fd  call     instance object[] [System.Web.Services]System.Web.Services.Protocols.SoapHttpClientProtocol::Invoke(string, object[])
0x8102  pop
0x8103  ret
```
