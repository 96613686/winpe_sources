# Microsoft.Crm.ReportingServices.ReportingService::BeginCreateDataSource

- ea: `0x11ba0`
- end: `0x11bd1`
- name: `Microsoft.Crm.ReportingServices.ReportingService::BeginCreateDataSource`
- size: `49`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## string_xrefs

- `0x11ba1`: `CreateDataSource`

## pseudocode

```c

```

## disassembly

```asm
0x11ba0  ldarg.0
0x11ba1  ldstr    aCreatedatasour// "CreateDataSource"
0x11ba6  ldc.i4.5
0x11ba7  newarr   [mscorlib]System.Object
0x11bac  dup
0x11bad  ldc.i4.0
0x11bae  ldarg.1
0x11baf  stelem.ref
0x11bb0  dup
0x11bb1  ldc.i4.1
0x11bb2  ldarg.2
0x11bb3  stelem.ref
0x11bb4  dup
0x11bb5  ldc.i4.2
0x11bb6  ldarg.3
0x11bb7  box      [mscorlib]System.Boolean
0x11bbc  stelem.ref
0x11bbd  dup
0x11bbe  ldc.i4.3
0x11bbf  ldarg.s  4
0x11bc1  stelem.ref
0x11bc2  dup
0x11bc3  ldc.i4.4
0x11bc4  ldarg.s  5
0x11bc6  stelem.ref
0x11bc7  ldarg.s  6
0x11bc9  ldarg.s  7
0x11bcb  call     instance class [mscorlib]System.IAsyncResult [System.Web.Services]System.Web.Services.Protocols.SoapHttpClientProtocol::BeginInvoke(string, object[], class [mscorlib]System.AsyncCallback, object)
0x11bd0  ret
```
