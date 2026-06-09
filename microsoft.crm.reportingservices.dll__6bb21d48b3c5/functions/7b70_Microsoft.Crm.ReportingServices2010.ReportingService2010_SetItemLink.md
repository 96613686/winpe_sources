# Microsoft.Crm.ReportingServices2010.ReportingService2010::SetItemLink

- ea: `0x7b70`
- end: `0x7b8b`
- name: `Microsoft.Crm.ReportingServices2010.ReportingService2010::SetItemLink`
- size: `27`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## string_xrefs

- `0x7b71`: `SetItemLink`

## pseudocode

```c

```

## disassembly

```asm
0x7b70  ldarg.0
0x7b71  ldstr    aSetitemlink// "SetItemLink"
0x7b76  ldc.i4.2
0x7b77  newarr   [mscorlib]System.Object
0x7b7c  dup
0x7b7d  ldc.i4.0
0x7b7e  ldarg.1
0x7b7f  stelem.ref
0x7b80  dup
0x7b81  ldc.i4.1
0x7b82  ldarg.2
0x7b83  stelem.ref
0x7b84  call     instance object[] [System.Web.Services]System.Web.Services.Protocols.SoapHttpClientProtocol::Invoke(string, object[])
0x7b89  pop
0x7b8a  ret
```
