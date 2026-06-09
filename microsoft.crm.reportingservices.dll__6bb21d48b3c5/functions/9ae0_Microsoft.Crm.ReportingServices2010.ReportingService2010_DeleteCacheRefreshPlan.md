# Microsoft.Crm.ReportingServices2010.ReportingService2010::DeleteCacheRefreshPlan

- ea: `0x9ae0`
- end: `0x9af7`
- name: `Microsoft.Crm.ReportingServices2010.ReportingService2010::DeleteCacheRefreshPlan`
- size: `23`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## string_xrefs

- `0x9ae1`: `DeleteCacheRefreshPlan`

## pseudocode

```c

```

## disassembly

```asm
0x9ae0  ldarg.0
0x9ae1  ldstr    aDeletecacheref// "DeleteCacheRefreshPlan"
0x9ae6  ldc.i4.1
0x9ae7  newarr   [mscorlib]System.Object
0x9aec  dup
0x9aed  ldc.i4.0
0x9aee  ldarg.1
0x9aef  stelem.ref
0x9af0  call     instance object[] [System.Web.Services]System.Web.Services.Protocols.SoapHttpClientProtocol::Invoke(string, object[])
0x9af5  pop
0x9af6  ret
```
