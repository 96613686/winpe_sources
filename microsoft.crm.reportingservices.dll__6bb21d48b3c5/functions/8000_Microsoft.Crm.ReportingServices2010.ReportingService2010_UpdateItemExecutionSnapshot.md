# Microsoft.Crm.ReportingServices2010.ReportingService2010::UpdateItemExecutionSnapshot

- ea: `0x8000`
- end: `0x8017`
- name: `Microsoft.Crm.ReportingServices2010.ReportingService2010::UpdateItemExecutionSnapshot`
- size: `23`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, installer_update, broker_com_uri`

## string_xrefs

- `0x8001`: `UpdateItemExecutionSnapshot`

## pseudocode

```c

```

## disassembly

```asm
0x8000  ldarg.0
0x8001  ldstr    aUpdateitemexec// "UpdateItemExecutionSnapshot"
0x8006  ldc.i4.1
0x8007  newarr   [mscorlib]System.Object
0x800c  dup
0x800d  ldc.i4.0
0x800e  ldarg.1
0x800f  stelem.ref
0x8010  call     instance object[] [System.Web.Services]System.Web.Services.Protocols.SoapHttpClientProtocol::Invoke(string, object[])
0x8015  pop
0x8016  ret
```
