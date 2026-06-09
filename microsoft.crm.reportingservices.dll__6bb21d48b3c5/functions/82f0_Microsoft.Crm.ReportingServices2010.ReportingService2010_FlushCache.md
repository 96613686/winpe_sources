# Microsoft.Crm.ReportingServices2010.ReportingService2010::FlushCache

- ea: `0x82f0`
- end: `0x8307`
- name: `Microsoft.Crm.ReportingServices2010.ReportingService2010::FlushCache`
- size: `23`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## string_xrefs

- `0x82f1`: `FlushCache`

## pseudocode

```c

```

## disassembly

```asm
0x82f0  ldarg.0
0x82f1  ldstr    aFlushcache// "FlushCache"
0x82f6  ldc.i4.1
0x82f7  newarr   [mscorlib]System.Object
0x82fc  dup
0x82fd  ldc.i4.0
0x82fe  ldarg.1
0x82ff  stelem.ref
0x8300  call     instance object[] [System.Web.Services]System.Web.Services.Protocols.SoapHttpClientProtocol::Invoke(string, object[])
0x8305  pop
0x8306  ret
```
