# Microsoft.Crm.ReportingServices.ReportingService::BeginInheritParentSecurity

- ea: `0x13030`
- end: `0x13048`
- name: `Microsoft.Crm.ReportingServices.ReportingService::BeginInheritParentSecurity`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## string_xrefs

- `0x13031`: `InheritParentSecurity`

## pseudocode

```c

```

## disassembly

```asm
0x13030  ldarg.0
0x13031  ldstr    aInheritparents// "InheritParentSecurity"
0x13036  ldc.i4.1
0x13037  newarr   [mscorlib]System.Object
0x1303c  dup
0x1303d  ldc.i4.0
0x1303e  ldarg.1
0x1303f  stelem.ref
0x13040  ldarg.2
0x13041  ldarg.3
0x13042  call     instance class [mscorlib]System.IAsyncResult [System.Web.Services]System.Web.Services.Protocols.SoapHttpClientProtocol::BeginInvoke(string, object[], class [mscorlib]System.AsyncCallback, object)
0x13047  ret
```
