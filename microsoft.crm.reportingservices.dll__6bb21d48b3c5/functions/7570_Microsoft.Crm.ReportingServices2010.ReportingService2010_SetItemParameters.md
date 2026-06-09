# Microsoft.Crm.ReportingServices2010.ReportingService2010::SetItemParameters

- ea: `0x7570`
- end: `0x758b`
- name: `Microsoft.Crm.ReportingServices2010.ReportingService2010::SetItemParameters`
- size: `27`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## string_xrefs

- `0x7571`: `SetItemParameters`

## pseudocode

```c

```

## disassembly

```asm
0x7570  ldarg.0
0x7571  ldstr    aSetitemparamet// "SetItemParameters"
0x7576  ldc.i4.2
0x7577  newarr   [mscorlib]System.Object
0x757c  dup
0x757d  ldc.i4.0
0x757e  ldarg.1
0x757f  stelem.ref
0x7580  dup
0x7581  ldc.i4.1
0x7582  ldarg.2
0x7583  stelem.ref
0x7584  call     instance object[] [System.Web.Services]System.Web.Services.Protocols.SoapHttpClientProtocol::Invoke(string, object[])
0x7589  pop
0x758a  ret
```
