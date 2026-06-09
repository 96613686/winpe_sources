# Microsoft.Crm.ReportingServices.ReportingService::BeginSetSystemPolicies

- ea: `0x12f20`
- end: `0x12f38`
- name: `Microsoft.Crm.ReportingServices.ReportingService::BeginSetSystemPolicies`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## string_xrefs

- `0x12f21`: `SetSystemPolicies`

## pseudocode

```c

```

## disassembly

```asm
0x12f20  ldarg.0
0x12f21  ldstr    aSetsystempolic// "SetSystemPolicies"
0x12f26  ldc.i4.1
0x12f27  newarr   [mscorlib]System.Object
0x12f2c  dup
0x12f2d  ldc.i4.0
0x12f2e  ldarg.1
0x12f2f  stelem.ref
0x12f30  ldarg.2
0x12f31  ldarg.3
0x12f32  call     instance class [mscorlib]System.IAsyncResult [System.Web.Services]System.Web.Services.Protocols.SoapHttpClientProtocol::BeginInvoke(string, object[], class [mscorlib]System.AsyncCallback, object)
0x12f37  ret
```
