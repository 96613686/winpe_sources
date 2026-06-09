# Microsoft.Crm.ReportingServices2010.ReportingService2010::BeginGetModelItemPolicies

- ea: `0x6450`
- end: `0x646d`
- name: `Microsoft.Crm.ReportingServices2010.ReportingService2010::BeginGetModelItemPolicies`
- size: `29`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## string_xrefs

- `0x6451`: `GetModelItemPolicies`

## pseudocode

```c

```

## disassembly

```asm
0x6450  ldarg.0
0x6451  ldstr    aGetmodelitempo// "GetModelItemPolicies"
0x6456  ldc.i4.2
0x6457  newarr   [mscorlib]System.Object
0x645c  dup
0x645d  ldc.i4.0
0x645e  ldarg.1
0x645f  stelem.ref
0x6460  dup
0x6461  ldc.i4.1
0x6462  ldarg.2
0x6463  stelem.ref
0x6464  ldarg.3
0x6465  ldarg.s  4
0x6467  call     instance class [mscorlib]System.IAsyncResult [System.Web.Services]System.Web.Services.Protocols.SoapHttpClientProtocol::BeginInvoke(string, object[], class [mscorlib]System.AsyncCallback, object)
0x646c  ret
```
