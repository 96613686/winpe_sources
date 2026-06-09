# Microsoft.Crm.ReportingServices2010.ReportingService2010::GetModelItemPermissions

- ea: `0x6240`
- end: `0x6261`
- name: `Microsoft.Crm.ReportingServices2010.ReportingService2010::GetModelItemPermissions`
- size: `33`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## string_xrefs

- `0x6241`: `GetModelItemPermissions`

## pseudocode

```c

```

## disassembly

```asm
0x6240  ldarg.0
0x6241  ldstr    aGetmodelitempe// "GetModelItemPermissions"
0x6246  ldc.i4.2
0x6247  newarr   [mscorlib]System.Object
0x624c  dup
0x624d  ldc.i4.0
0x624e  ldarg.1
0x624f  stelem.ref
0x6250  dup
0x6251  ldc.i4.1
0x6252  ldarg.2
0x6253  stelem.ref
0x6254  call     instance object[] [System.Web.Services]System.Web.Services.Protocols.SoapHttpClientProtocol::Invoke(string, object[])
0x6259  ldc.i4.0
0x625a  ldelem.ref
0x625b  castclass string[]
0x6260  ret
```
