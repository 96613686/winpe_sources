# Microsoft.Crm.ReportingServices2010.ReportingService2010::SetCacheRefreshPlanProperties

- ea: `0x9870`
- end: `0x9899`
- name: `Microsoft.Crm.ReportingServices2010.ReportingService2010::SetCacheRefreshPlanProperties`
- size: `41`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## string_xrefs

- `0x9871`: `SetCacheRefreshPlanProperties`

## pseudocode

```c

```

## disassembly

```asm
0x9870  ldarg.0
0x9871  ldstr    aSetcacherefres// "SetCacheRefreshPlanProperties"
0x9876  ldc.i4.5
0x9877  newarr   [mscorlib]System.Object
0x987c  dup
0x987d  ldc.i4.0
0x987e  ldarg.1
0x987f  stelem.ref
0x9880  dup
0x9881  ldc.i4.1
0x9882  ldarg.2
0x9883  stelem.ref
0x9884  dup
0x9885  ldc.i4.2
0x9886  ldarg.3
0x9887  stelem.ref
0x9888  dup
0x9889  ldc.i4.3
0x988a  ldarg.s  4
0x988c  stelem.ref
0x988d  dup
0x988e  ldc.i4.4
0x988f  ldarg.s  5
0x9891  stelem.ref
0x9892  call     instance object[] [System.Web.Services]System.Web.Services.Protocols.SoapHttpClientProtocol::Invoke(string, object[])
0x9897  pop
0x9898  ret
```
