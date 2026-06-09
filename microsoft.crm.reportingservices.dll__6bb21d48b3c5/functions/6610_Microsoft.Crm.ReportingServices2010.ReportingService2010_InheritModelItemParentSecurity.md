# Microsoft.Crm.ReportingServices2010.ReportingService2010::InheritModelItemParentSecurity

- ea: `0x6610`
- end: `0x662b`
- name: `Microsoft.Crm.ReportingServices2010.ReportingService2010::InheritModelItemParentSecurity`
- size: `27`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## string_xrefs

- `0x6611`: `InheritModelItemParentSecurity`

## pseudocode

```c

```

## disassembly

```asm
0x6610  ldarg.0
0x6611  ldstr    aInheritmodelit// "InheritModelItemParentSecurity"
0x6616  ldc.i4.2
0x6617  newarr   [mscorlib]System.Object
0x661c  dup
0x661d  ldc.i4.0
0x661e  ldarg.1
0x661f  stelem.ref
0x6620  dup
0x6621  ldc.i4.1
0x6622  ldarg.2
0x6623  stelem.ref
0x6624  call     instance object[] [System.Web.Services]System.Web.Services.Protocols.SoapHttpClientProtocol::Invoke(string, object[])
0x6629  pop
0x662a  ret
```
