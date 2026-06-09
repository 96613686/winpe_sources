# Microsoft.Crm.ReportingServices.ReportingService::DeleteSubscription

- ea: `0x128d0`
- end: `0x128e7`
- name: `Microsoft.Crm.ReportingServices.ReportingService::DeleteSubscription`
- size: `23`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## string_xrefs

- `0x128d1`: `DeleteSubscription`

## pseudocode

```c

```

## disassembly

```asm
0x128d0  ldarg.0
0x128d1  ldstr    aDeletesubscrip// "DeleteSubscription"
0x128d6  ldc.i4.1
0x128d7  newarr   [mscorlib]System.Object
0x128dc  dup
0x128dd  ldc.i4.0
0x128de  ldarg.1
0x128df  stelem.ref
0x128e0  call     instance object[] [System.Web.Services]System.Web.Services.Protocols.SoapHttpClientProtocol::Invoke(string, object[])
0x128e5  pop
0x128e6  ret
```
