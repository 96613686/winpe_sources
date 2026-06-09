# Microsoft.Crm.ReportingServices2010.ReportingService2010::BeginGetItemParameters

- ea: `0x7690`
- end: `0x76c1`
- name: `Microsoft.Crm.ReportingServices2010.ReportingService2010::BeginGetItemParameters`
- size: `49`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## string_xrefs

- `0x7691`: `GetItemParameters`

## pseudocode

```c

```

## disassembly

```asm
0x7690  ldarg.0
0x7691  ldstr    aGetitemparamet// "GetItemParameters"
0x7696  ldc.i4.5
0x7697  newarr   [mscorlib]System.Object
0x769c  dup
0x769d  ldc.i4.0
0x769e  ldarg.1
0x769f  stelem.ref
0x76a0  dup
0x76a1  ldc.i4.1
0x76a2  ldarg.2
0x76a3  stelem.ref
0x76a4  dup
0x76a5  ldc.i4.2
0x76a6  ldarg.3
0x76a7  box      [mscorlib]System.Boolean
0x76ac  stelem.ref
0x76ad  dup
0x76ae  ldc.i4.3
0x76af  ldarg.s  4
0x76b1  stelem.ref
0x76b2  dup
0x76b3  ldc.i4.4
0x76b4  ldarg.s  5
0x76b6  stelem.ref
0x76b7  ldarg.s  6
0x76b9  ldarg.s  7
0x76bb  call     instance class [mscorlib]System.IAsyncResult [System.Web.Services]System.Web.Services.Protocols.SoapHttpClientProtocol::BeginInvoke(string, object[], class [mscorlib]System.AsyncCallback, object)
0x76c0  ret
```
