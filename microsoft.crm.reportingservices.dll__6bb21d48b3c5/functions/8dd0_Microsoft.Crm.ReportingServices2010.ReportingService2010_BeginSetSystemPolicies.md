# Microsoft.Crm.ReportingServices2010.ReportingService2010::BeginSetSystemPolicies

- ea: `0x8dd0`
- end: `0x8de8`
- name: `Microsoft.Crm.ReportingServices2010.ReportingService2010::BeginSetSystemPolicies`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## string_xrefs

- `0x8dd1`: `SetSystemPolicies`

## pseudocode

```c

```

## disassembly

```asm
0x8dd0  ldarg.0
0x8dd1  ldstr    aSetsystempolic// "SetSystemPolicies"
0x8dd6  ldc.i4.1
0x8dd7  newarr   [mscorlib]System.Object
0x8ddc  dup
0x8ddd  ldc.i4.0
0x8dde  ldarg.1
0x8ddf  stelem.ref
0x8de0  ldarg.2
0x8de1  ldarg.3
0x8de2  call     instance class [mscorlib]System.IAsyncResult [System.Web.Services]System.Web.Services.Protocols.SoapHttpClientProtocol::BeginInvoke(string, object[], class [mscorlib]System.AsyncCallback, object)
0x8de7  ret
```
