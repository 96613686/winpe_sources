# Microsoft.Crm.ReportingServices.ReportingService::GetSystemPolicies

- ea: `0x12eb0`
- end: `0x12ec9`
- name: `Microsoft.Crm.ReportingServices.ReportingService::GetSystemPolicies`
- size: `25`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## string_xrefs

- `0x12eb1`: `GetSystemPolicies`

## pseudocode

```c

```

## disassembly

```asm
0x12eb0  ldarg.0
0x12eb1  ldstr    aGetsystempolic// "GetSystemPolicies"
0x12eb6  ldc.i4.0
0x12eb7  newarr   [mscorlib]System.Object
0x12ebc  call     instance object[] [System.Web.Services]System.Web.Services.Protocols.SoapHttpClientProtocol::Invoke(string, object[])
0x12ec1  ldc.i4.0
0x12ec2  ldelem.ref
0x12ec3  castclass class Microsoft.Crm.ReportingServices.Policy[]
0x12ec8  ret
```
