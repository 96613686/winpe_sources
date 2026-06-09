# Microsoft.Crm.ReportingServices2010.ReportingService2010::SetModelItemPolicies

- ea: `0x6330`
- end: `0x634f`
- name: `Microsoft.Crm.ReportingServices2010.ReportingService2010::SetModelItemPolicies`
- size: `31`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## string_xrefs

- `0x6331`: `SetModelItemPolicies`

## pseudocode

```c

```

## disassembly

```asm
0x6330  ldarg.0
0x6331  ldstr    aSetmodelitempo// "SetModelItemPolicies"
0x6336  ldc.i4.3
0x6337  newarr   [mscorlib]System.Object
0x633c  dup
0x633d  ldc.i4.0
0x633e  ldarg.1
0x633f  stelem.ref
0x6340  dup
0x6341  ldc.i4.1
0x6342  ldarg.2
0x6343  stelem.ref
0x6344  dup
0x6345  ldc.i4.2
0x6346  ldarg.3
0x6347  stelem.ref
0x6348  call     instance object[] [System.Web.Services]System.Web.Services.Protocols.SoapHttpClientProtocol::Invoke(string, object[])
0x634d  pop
0x634e  ret
```
