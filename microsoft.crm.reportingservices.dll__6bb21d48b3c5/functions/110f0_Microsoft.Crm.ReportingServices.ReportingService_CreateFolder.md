# Microsoft.Crm.ReportingServices.ReportingService::CreateFolder

- ea: `0x110f0`
- end: `0x1110f`
- name: `Microsoft.Crm.ReportingServices.ReportingService::CreateFolder`
- size: `31`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## string_xrefs

- `0x110f1`: `CreateFolder`

## pseudocode

```c

```

## disassembly

```asm
0x110f0  ldarg.0
0x110f1  ldstr    aCreatefolder// "CreateFolder"
0x110f6  ldc.i4.3
0x110f7  newarr   [mscorlib]System.Object
0x110fc  dup
0x110fd  ldc.i4.0
0x110fe  ldarg.1
0x110ff  stelem.ref
0x11100  dup
0x11101  ldc.i4.1
0x11102  ldarg.2
0x11103  stelem.ref
0x11104  dup
0x11105  ldc.i4.2
0x11106  ldarg.3
0x11107  stelem.ref
0x11108  call     instance object[] [System.Web.Services]System.Web.Services.Protocols.SoapHttpClientProtocol::Invoke(string, object[])
0x1110d  pop
0x1110e  ret
```
