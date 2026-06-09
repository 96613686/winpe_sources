# Microsoft.Crm.ReportingServices2010.ReportingService2010::BeginInheritParentSecurity

- ea: `0x34a0`
- end: `0x34b8`
- name: `Microsoft.Crm.ReportingServices2010.ReportingService2010::BeginInheritParentSecurity`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## string_xrefs

- `0x34a1`: `InheritParentSecurity`

## pseudocode

```c

```

## disassembly

```asm
0x34a0  ldarg.0
0x34a1  ldstr    aInheritparents// "InheritParentSecurity"
0x34a6  ldc.i4.1
0x34a7  newarr   [mscorlib]System.Object
0x34ac  dup
0x34ad  ldc.i4.0
0x34ae  ldarg.1
0x34af  stelem.ref
0x34b0  ldarg.2
0x34b1  ldarg.3
0x34b2  call     instance class [mscorlib]System.IAsyncResult [System.Web.Services]System.Web.Services.Protocols.SoapHttpClientProtocol::BeginInvoke(string, object[], class [mscorlib]System.AsyncCallback, object)
0x34b7  ret
```
