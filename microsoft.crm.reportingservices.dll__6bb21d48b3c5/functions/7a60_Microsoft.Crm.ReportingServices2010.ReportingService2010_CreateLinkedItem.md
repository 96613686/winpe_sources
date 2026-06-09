# Microsoft.Crm.ReportingServices2010.ReportingService2010::CreateLinkedItem

- ea: `0x7a60`
- end: `0x7a84`
- name: `Microsoft.Crm.ReportingServices2010.ReportingService2010::CreateLinkedItem`
- size: `36`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## string_xrefs

- `0x7a61`: `CreateLinkedItem`

## pseudocode

```c

```

## disassembly

```asm
0x7a60  ldarg.0
0x7a61  ldstr    aCreatelinkedit// "CreateLinkedItem"
0x7a66  ldc.i4.4
0x7a67  newarr   [mscorlib]System.Object
0x7a6c  dup
0x7a6d  ldc.i4.0
0x7a6e  ldarg.1
0x7a6f  stelem.ref
0x7a70  dup
0x7a71  ldc.i4.1
0x7a72  ldarg.2
0x7a73  stelem.ref
0x7a74  dup
0x7a75  ldc.i4.2
0x7a76  ldarg.3
0x7a77  stelem.ref
0x7a78  dup
0x7a79  ldc.i4.3
0x7a7a  ldarg.s  4
0x7a7c  stelem.ref
0x7a7d  call     instance object[] [System.Web.Services]System.Web.Services.Protocols.SoapHttpClientProtocol::Invoke(string, object[])
0x7a82  pop
0x7a83  ret
```
