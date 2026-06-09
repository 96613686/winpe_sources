# Microsoft.Crm.ReportingServices2010.ReportingService2010::GetSystemPermissions

- ea: `0x9f50`
- end: `0x9f69`
- name: `Microsoft.Crm.ReportingServices2010.ReportingService2010::GetSystemPermissions`
- size: `25`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## string_xrefs

- `0x9f51`: `GetSystemPermissions`

## pseudocode

```c

```

## disassembly

```asm
0x9f50  ldarg.0
0x9f51  ldstr    aGetsystempermi// "GetSystemPermissions"
0x9f56  ldc.i4.0
0x9f57  newarr   [mscorlib]System.Object
0x9f5c  call     instance object[] [System.Web.Services]System.Web.Services.Protocols.SoapHttpClientProtocol::Invoke(string, object[])
0x9f61  ldc.i4.0
0x9f62  ldelem.ref
0x9f63  castclass string[]
0x9f68  ret
```
