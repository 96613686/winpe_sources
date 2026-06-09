# Microsoft.Crm.ReportingServices2010.ReportingService2010::ListSecurityScopesAsync_0

- ea: `0xa090`
- end: `0xa0c3`
- name: `Microsoft.Crm.ReportingServices2010.ReportingService2010::ListSecurityScopesAsync_0`
- size: `51`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0xa080`

## callees

- `0xa090`

## string_xrefs

- `0xa0ab`: `ListSecurityScopes`

## pseudocode

```c

```

## disassembly

```asm
0xa090  ldarg.0
0xa091  ldfld    class [mscorlib]System.Threading.SendOrPostCallback Microsoft.Crm.ReportingServices2010.ReportingService2010::ListSecurityScopesOperationCompleted
0xa096  brtrue.s loc_A0AA
0xa098  ldarg.0
0xa099  ldarg.0
0xa09a  ldftn    instance void Microsoft.Crm.ReportingServices2010.ReportingService2010::OnListSecurityScopesOperationCompleted(object arg)
0xa0a0  newobj   instance void [mscorlib]System.Threading.SendOrPostCallback::.ctor(object, native int)
0xa0a5  stfld    class [mscorlib]System.Threading.SendOrPostCallback Microsoft.Crm.ReportingServices2010.ReportingService2010::ListSecurityScopesOperationCompleted
0xa0aa  ldarg.0
0xa0ab  ldstr    aListsecuritysc// "ListSecurityScopes"
0xa0b0  ldc.i4.0
0xa0b1  newarr   [mscorlib]System.Object
0xa0b6  ldarg.0
0xa0b7  ldfld    class [mscorlib]System.Threading.SendOrPostCallback Microsoft.Crm.ReportingServices2010.ReportingService2010::ListSecurityScopesOperationCompleted
0xa0bc  ldarg.1
0xa0bd  call     instance void [System.Web.Services]System.Web.Services.Protocols.SoapHttpClientProtocol::InvokeAsync(string, object[], class [mscorlib]System.Threading.SendOrPostCallback, object)
0xa0c2  ret
```
