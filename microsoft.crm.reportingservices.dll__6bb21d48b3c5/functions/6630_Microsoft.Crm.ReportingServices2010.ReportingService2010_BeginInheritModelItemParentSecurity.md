# Microsoft.Crm.ReportingServices2010.ReportingService2010::BeginInheritModelItemParentSecurity

- ea: `0x6630`
- end: `0x664d`
- name: `Microsoft.Crm.ReportingServices2010.ReportingService2010::BeginInheritModelItemParentSecurity`
- size: `29`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## string_xrefs

- `0x6631`: `InheritModelItemParentSecurity`

## pseudocode

```c

```

## disassembly

```asm
0x6630  ldarg.0
0x6631  ldstr    aInheritmodelit// "InheritModelItemParentSecurity"
0x6636  ldc.i4.2
0x6637  newarr   [mscorlib]System.Object
0x663c  dup
0x663d  ldc.i4.0
0x663e  ldarg.1
0x663f  stelem.ref
0x6640  dup
0x6641  ldc.i4.1
0x6642  ldarg.2
0x6643  stelem.ref
0x6644  ldarg.3
0x6645  ldarg.s  4
0x6647  call     instance class [mscorlib]System.IAsyncResult [System.Web.Services]System.Web.Services.Protocols.SoapHttpClientProtocol::BeginInvoke(string, object[], class [mscorlib]System.AsyncCallback, object)
0x664c  ret
```
