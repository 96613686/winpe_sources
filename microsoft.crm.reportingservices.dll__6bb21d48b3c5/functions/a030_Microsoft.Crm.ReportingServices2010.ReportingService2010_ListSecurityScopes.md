# Microsoft.Crm.ReportingServices2010.ReportingService2010::ListSecurityScopes

- ea: `0xa030`
- end: `0xa049`
- name: `Microsoft.Crm.ReportingServices2010.ReportingService2010::ListSecurityScopes`
- size: `25`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## string_xrefs

- `0xa031`: `ListSecurityScopes`

## pseudocode

```c

```

## disassembly

```asm
0xa030  ldarg.0
0xa031  ldstr    aListsecuritysc// "ListSecurityScopes"
0xa036  ldc.i4.0
0xa037  newarr   [mscorlib]System.Object
0xa03c  call     instance object[] [System.Web.Services]System.Web.Services.Protocols.SoapHttpClientProtocol::Invoke(string, object[])
0xa041  ldc.i4.0
0xa042  ldelem.ref
0xa043  castclass string[]
0xa048  ret
```
