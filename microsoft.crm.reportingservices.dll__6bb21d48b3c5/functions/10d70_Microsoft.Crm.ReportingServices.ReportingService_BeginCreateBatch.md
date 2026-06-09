# Microsoft.Crm.ReportingServices.ReportingService::BeginCreateBatch

- ea: `0x10d70`
- end: `0x10d84`
- name: `Microsoft.Crm.ReportingServices.ReportingService::BeginCreateBatch`
- size: `20`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## string_xrefs

- `0x10d71`: `CreateBatch`

## pseudocode

```c

```

## disassembly

```asm
0x10d70  ldarg.0
0x10d71  ldstr    aCreatebatch// "CreateBatch"
0x10d76  ldc.i4.0
0x10d77  newarr   [mscorlib]System.Object
0x10d7c  ldarg.1
0x10d7d  ldarg.2
0x10d7e  call     instance class [mscorlib]System.IAsyncResult [System.Web.Services]System.Web.Services.Protocols.SoapHttpClientProtocol::BeginInvoke(string, object[], class [mscorlib]System.AsyncCallback, object)
0x10d83  ret
```
