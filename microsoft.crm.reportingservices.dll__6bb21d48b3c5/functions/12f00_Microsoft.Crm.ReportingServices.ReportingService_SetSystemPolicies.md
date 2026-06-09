# Microsoft.Crm.ReportingServices.ReportingService::SetSystemPolicies

- ea: `0x12f00`
- end: `0x12f17`
- name: `Microsoft.Crm.ReportingServices.ReportingService::SetSystemPolicies`
- size: `23`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## string_xrefs

- `0x12f01`: `SetSystemPolicies`

## pseudocode

```c

```

## disassembly

```asm
0x12f00  ldarg.0
0x12f01  ldstr    aSetsystempolic// "SetSystemPolicies"
0x12f06  ldc.i4.1
0x12f07  newarr   [mscorlib]System.Object
0x12f0c  dup
0x12f0d  ldc.i4.0
0x12f0e  ldarg.1
0x12f0f  stelem.ref
0x12f10  call     instance object[] [System.Web.Services]System.Web.Services.Protocols.SoapHttpClientProtocol::Invoke(string, object[])
0x12f15  pop
0x12f16  ret
```
