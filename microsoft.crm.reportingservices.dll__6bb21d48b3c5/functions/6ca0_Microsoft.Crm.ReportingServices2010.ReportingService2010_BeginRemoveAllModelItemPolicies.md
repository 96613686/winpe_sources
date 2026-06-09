# Microsoft.Crm.ReportingServices2010.ReportingService2010::BeginRemoveAllModelItemPolicies

- ea: `0x6ca0`
- end: `0x6cb8`
- name: `Microsoft.Crm.ReportingServices2010.ReportingService2010::BeginRemoveAllModelItemPolicies`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## string_xrefs

- `0x6ca1`: `RemoveAllModelItemPolicies`

## pseudocode

```c

```

## disassembly

```asm
0x6ca0  ldarg.0
0x6ca1  ldstr    aRemoveallmodel// "RemoveAllModelItemPolicies"
0x6ca6  ldc.i4.1
0x6ca7  newarr   [mscorlib]System.Object
0x6cac  dup
0x6cad  ldc.i4.0
0x6cae  ldarg.1
0x6caf  stelem.ref
0x6cb0  ldarg.2
0x6cb1  ldarg.3
0x6cb2  call     instance class [mscorlib]System.IAsyncResult [System.Web.Services]System.Web.Services.Protocols.SoapHttpClientProtocol::BeginInvoke(string, object[], class [mscorlib]System.AsyncCallback, object)
0x6cb7  ret
```
