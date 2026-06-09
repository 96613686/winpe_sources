# Microsoft.Crm.ReportingServices.ReportingService::BeginGetSystemPolicies

- ea: `0x12ed0`
- end: `0x12ee4`
- name: `Microsoft.Crm.ReportingServices.ReportingService::BeginGetSystemPolicies`
- size: `20`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## string_xrefs

- `0x12ed1`: `GetSystemPolicies`

## pseudocode

```c

```

## disassembly

```asm
0x12ed0  ldarg.0
0x12ed1  ldstr    aGetsystempolic// "GetSystemPolicies"
0x12ed6  ldc.i4.0
0x12ed7  newarr   [mscorlib]System.Object
0x12edc  ldarg.1
0x12edd  ldarg.2
0x12ede  call     instance class [mscorlib]System.IAsyncResult [System.Web.Services]System.Web.Services.Protocols.SoapHttpClientProtocol::BeginInvoke(string, object[], class [mscorlib]System.AsyncCallback, object)
0x12ee3  ret
```
