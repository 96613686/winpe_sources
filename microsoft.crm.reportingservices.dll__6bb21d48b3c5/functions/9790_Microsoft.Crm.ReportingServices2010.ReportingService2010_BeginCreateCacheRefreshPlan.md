# Microsoft.Crm.ReportingServices2010.ReportingService2010::BeginCreateCacheRefreshPlan

- ea: `0x9790`
- end: `0x97bc`
- name: `Microsoft.Crm.ReportingServices2010.ReportingService2010::BeginCreateCacheRefreshPlan`
- size: `44`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## string_xrefs

- `0x9791`: `CreateCacheRefreshPlan`

## pseudocode

```c

```

## disassembly

```asm
0x9790  ldarg.0
0x9791  ldstr    aCreatecacheref// "CreateCacheRefreshPlan"
0x9796  ldc.i4.5
0x9797  newarr   [mscorlib]System.Object
0x979c  dup
0x979d  ldc.i4.0
0x979e  ldarg.1
0x979f  stelem.ref
0x97a0  dup
0x97a1  ldc.i4.1
0x97a2  ldarg.2
0x97a3  stelem.ref
0x97a4  dup
0x97a5  ldc.i4.2
0x97a6  ldarg.3
0x97a7  stelem.ref
0x97a8  dup
0x97a9  ldc.i4.3
0x97aa  ldarg.s  4
0x97ac  stelem.ref
0x97ad  dup
0x97ae  ldc.i4.4
0x97af  ldarg.s  5
0x97b1  stelem.ref
0x97b2  ldarg.s  6
0x97b4  ldarg.s  7
0x97b6  call     instance class [mscorlib]System.IAsyncResult [System.Web.Services]System.Web.Services.Protocols.SoapHttpClientProtocol::BeginInvoke(string, object[], class [mscorlib]System.AsyncCallback, object)
0x97bb  ret
```
