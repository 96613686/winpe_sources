# Microsoft.Crm.ReportingServices2010.ReportingService2010::BeginGetSystemPolicies

- ea: `0x8eb0`
- end: `0x8ec4`
- name: `Microsoft.Crm.ReportingServices2010.ReportingService2010::BeginGetSystemPolicies`
- size: `20`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## string_xrefs

- `0x8eb1`: `GetSystemPolicies`

## pseudocode

```c

```

## disassembly

```asm
0x8eb0  ldarg.0
0x8eb1  ldstr    aGetsystempolic// "GetSystemPolicies"
0x8eb6  ldc.i4.0
0x8eb7  newarr   [mscorlib]System.Object
0x8ebc  ldarg.1
0x8ebd  ldarg.2
0x8ebe  call     instance class [mscorlib]System.IAsyncResult [System.Web.Services]System.Web.Services.Protocols.SoapHttpClientProtocol::BeginInvoke(string, object[], class [mscorlib]System.AsyncCallback, object)
0x8ec3  ret
```
