# Microsoft.Crm.ReportingServices.ReportingService::InheritParentSecurity

- ea: `0x13010`
- end: `0x13027`
- name: `Microsoft.Crm.ReportingServices.ReportingService::InheritParentSecurity`
- size: `23`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## string_xrefs

- `0x13011`: `InheritParentSecurity`

## pseudocode

```c

```

## disassembly

```asm
0x13010  ldarg.0
0x13011  ldstr    aInheritparents// "InheritParentSecurity"
0x13016  ldc.i4.1
0x13017  newarr   [mscorlib]System.Object
0x1301c  dup
0x1301d  ldc.i4.0
0x1301e  ldarg.1
0x1301f  stelem.ref
0x13020  call     instance object[] [System.Web.Services]System.Web.Services.Protocols.SoapHttpClientProtocol::Invoke(string, object[])
0x13025  pop
0x13026  ret
```
