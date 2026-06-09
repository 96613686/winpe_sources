# Microsoft.Crm.ReportingServices.ReportingService::CreateBatch

- ea: `0x10d50`
- end: `0x10d69`
- name: `Microsoft.Crm.ReportingServices.ReportingService::CreateBatch`
- size: `25`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## string_xrefs

- `0x10d51`: `CreateBatch`

## pseudocode

```c

```

## disassembly

```asm
0x10d50  ldarg.0
0x10d51  ldstr    aCreatebatch// "CreateBatch"
0x10d56  ldc.i4.0
0x10d57  newarr   [mscorlib]System.Object
0x10d5c  call     instance object[] [System.Web.Services]System.Web.Services.Protocols.SoapHttpClientProtocol::Invoke(string, object[])
0x10d61  ldc.i4.0
0x10d62  ldelem.ref
0x10d63  castclass [mscorlib]System.String
0x10d68  ret
```
