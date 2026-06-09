# Microsoft.Crm.ReportingServices.ReportingService::BeginCreateRole

- ea: `0x12d50`
- end: `0x12d72`
- name: `Microsoft.Crm.ReportingServices.ReportingService::BeginCreateRole`
- size: `34`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## string_xrefs

- `0x12d51`: `CreateRole`

## pseudocode

```c

```

## disassembly

```asm
0x12d50  ldarg.0
0x12d51  ldstr    aCreaterole// "CreateRole"
0x12d56  ldc.i4.3
0x12d57  newarr   [mscorlib]System.Object
0x12d5c  dup
0x12d5d  ldc.i4.0
0x12d5e  ldarg.1
0x12d5f  stelem.ref
0x12d60  dup
0x12d61  ldc.i4.1
0x12d62  ldarg.2
0x12d63  stelem.ref
0x12d64  dup
0x12d65  ldc.i4.2
0x12d66  ldarg.3
0x12d67  stelem.ref
0x12d68  ldarg.s  4
0x12d6a  ldarg.s  5
0x12d6c  call     instance class [mscorlib]System.IAsyncResult [System.Web.Services]System.Web.Services.Protocols.SoapHttpClientProtocol::BeginInvoke(string, object[], class [mscorlib]System.AsyncCallback, object)
0x12d71  ret
```
