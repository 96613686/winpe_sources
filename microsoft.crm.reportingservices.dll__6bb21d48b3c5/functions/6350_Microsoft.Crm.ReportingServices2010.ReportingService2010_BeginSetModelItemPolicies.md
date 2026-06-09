# Microsoft.Crm.ReportingServices2010.ReportingService2010::BeginSetModelItemPolicies

- ea: `0x6350`
- end: `0x6372`
- name: `Microsoft.Crm.ReportingServices2010.ReportingService2010::BeginSetModelItemPolicies`
- size: `34`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## string_xrefs

- `0x6351`: `SetModelItemPolicies`

## pseudocode

```c

```

## disassembly

```asm
0x6350  ldarg.0
0x6351  ldstr    aSetmodelitempo// "SetModelItemPolicies"
0x6356  ldc.i4.3
0x6357  newarr   [mscorlib]System.Object
0x635c  dup
0x635d  ldc.i4.0
0x635e  ldarg.1
0x635f  stelem.ref
0x6360  dup
0x6361  ldc.i4.1
0x6362  ldarg.2
0x6363  stelem.ref
0x6364  dup
0x6365  ldc.i4.2
0x6366  ldarg.3
0x6367  stelem.ref
0x6368  ldarg.s  4
0x636a  ldarg.s  5
0x636c  call     instance class [mscorlib]System.IAsyncResult [System.Web.Services]System.Web.Services.Protocols.SoapHttpClientProtocol::BeginInvoke(string, object[], class [mscorlib]System.AsyncCallback, object)
0x6371  ret
```
