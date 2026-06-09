# Microsoft.Crm.ReportingServices2010.ReportingService2010::DeleteRole

- ea: `0x5ba0`
- end: `0x5bb7`
- name: `Microsoft.Crm.ReportingServices2010.ReportingService2010::DeleteRole`
- size: `23`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## string_xrefs

- `0x5ba1`: `DeleteRole`

## pseudocode

```c

```

## disassembly

```asm
0x5ba0  ldarg.0
0x5ba1  ldstr    aDeleterole// "DeleteRole"
0x5ba6  ldc.i4.1
0x5ba7  newarr   [mscorlib]System.Object
0x5bac  dup
0x5bad  ldc.i4.0
0x5bae  ldarg.1
0x5baf  stelem.ref
0x5bb0  call     instance object[] [System.Web.Services]System.Web.Services.Protocols.SoapHttpClientProtocol::Invoke(string, object[])
0x5bb5  pop
0x5bb6  ret
```
