# Microsoft.Crm.ReportingServices2010.ReportingService2010::GetItemParameters

- ea: `0x7650`
- end: `0x7684`
- name: `Microsoft.Crm.ReportingServices2010.ReportingService2010::GetItemParameters`
- size: `52`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## string_xrefs

- `0x7651`: `GetItemParameters`

## pseudocode

```c

```

## disassembly

```asm
0x7650  ldarg.0
0x7651  ldstr    aGetitemparamet// "GetItemParameters"
0x7656  ldc.i4.5
0x7657  newarr   [mscorlib]System.Object
0x765c  dup
0x765d  ldc.i4.0
0x765e  ldarg.1
0x765f  stelem.ref
0x7660  dup
0x7661  ldc.i4.1
0x7662  ldarg.2
0x7663  stelem.ref
0x7664  dup
0x7665  ldc.i4.2
0x7666  ldarg.3
0x7667  box      [mscorlib]System.Boolean
0x766c  stelem.ref
0x766d  dup
0x766e  ldc.i4.3
0x766f  ldarg.s  4
0x7671  stelem.ref
0x7672  dup
0x7673  ldc.i4.4
0x7674  ldarg.s  5
0x7676  stelem.ref
0x7677  call     instance object[] [System.Web.Services]System.Web.Services.Protocols.SoapHttpClientProtocol::Invoke(string, object[])
0x767c  ldc.i4.0
0x767d  ldelem.ref
0x767e  castclass class Microsoft.Crm.ReportingServices2010.ItemParameter[]
0x7683  ret
```
