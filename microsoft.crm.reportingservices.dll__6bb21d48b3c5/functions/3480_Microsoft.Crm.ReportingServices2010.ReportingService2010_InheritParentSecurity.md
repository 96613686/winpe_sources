# Microsoft.Crm.ReportingServices2010.ReportingService2010::InheritParentSecurity

- ea: `0x3480`
- end: `0x3497`
- name: `Microsoft.Crm.ReportingServices2010.ReportingService2010::InheritParentSecurity`
- size: `23`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## string_xrefs

- `0x3481`: `InheritParentSecurity`

## pseudocode

```c

```

## disassembly

```asm
0x3480  ldarg.0
0x3481  ldstr    aInheritparents// "InheritParentSecurity"
0x3486  ldc.i4.1
0x3487  newarr   [mscorlib]System.Object
0x348c  dup
0x348d  ldc.i4.0
0x348e  ldarg.1
0x348f  stelem.ref
0x3490  call     instance object[] [System.Web.Services]System.Web.Services.Protocols.SoapHttpClientProtocol::Invoke(string, object[])
0x3495  pop
0x3496  ret
```
