# Microsoft.Crm.ReportingServices2010.ReportingService2010::BeginDeleteRole

- ea: `0x5bc0`
- end: `0x5bd8`
- name: `Microsoft.Crm.ReportingServices2010.ReportingService2010::BeginDeleteRole`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## string_xrefs

- `0x5bc1`: `DeleteRole`

## pseudocode

```c

```

## disassembly

```asm
0x5bc0  ldarg.0
0x5bc1  ldstr    aDeleterole// "DeleteRole"
0x5bc6  ldc.i4.1
0x5bc7  newarr   [mscorlib]System.Object
0x5bcc  dup
0x5bcd  ldc.i4.0
0x5bce  ldarg.1
0x5bcf  stelem.ref
0x5bd0  ldarg.2
0x5bd1  ldarg.3
0x5bd2  call     instance class [mscorlib]System.IAsyncResult [System.Web.Services]System.Web.Services.Protocols.SoapHttpClientProtocol::BeginInvoke(string, object[], class [mscorlib]System.AsyncCallback, object)
0x5bd7  ret
```
