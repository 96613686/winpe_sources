# Microsoft.Crm.ReportingServices2010.ReportingService2010::BeginListSecurityScopes

- ea: `0xa050`
- end: `0xa064`
- name: `Microsoft.Crm.ReportingServices2010.ReportingService2010::BeginListSecurityScopes`
- size: `20`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## string_xrefs

- `0xa051`: `ListSecurityScopes`

## pseudocode

```c

```

## disassembly

```asm
0xa050  ldarg.0
0xa051  ldstr    aListsecuritysc// "ListSecurityScopes"
0xa056  ldc.i4.0
0xa057  newarr   [mscorlib]System.Object
0xa05c  ldarg.1
0xa05d  ldarg.2
0xa05e  call     instance class [mscorlib]System.IAsyncResult [System.Web.Services]System.Web.Services.Protocols.SoapHttpClientProtocol::BeginInvoke(string, object[], class [mscorlib]System.AsyncCallback, object)
0xa063  ret
```
