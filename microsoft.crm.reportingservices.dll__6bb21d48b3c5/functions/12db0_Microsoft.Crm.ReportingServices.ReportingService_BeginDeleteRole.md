# Microsoft.Crm.ReportingServices.ReportingService::BeginDeleteRole

- ea: `0x12db0`
- end: `0x12dc8`
- name: `Microsoft.Crm.ReportingServices.ReportingService::BeginDeleteRole`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## string_xrefs

- `0x12db1`: `DeleteRole`

## pseudocode

```c

```

## disassembly

```asm
0x12db0  ldarg.0
0x12db1  ldstr    aDeleterole// "DeleteRole"
0x12db6  ldc.i4.1
0x12db7  newarr   [mscorlib]System.Object
0x12dbc  dup
0x12dbd  ldc.i4.0
0x12dbe  ldarg.1
0x12dbf  stelem.ref
0x12dc0  ldarg.2
0x12dc1  ldarg.3
0x12dc2  call     instance class [mscorlib]System.IAsyncResult [System.Web.Services]System.Web.Services.Protocols.SoapHttpClientProtocol::BeginInvoke(string, object[], class [mscorlib]System.AsyncCallback, object)
0x12dc7  ret
```
