# Microsoft.Crm.ReportingServices2010.ReportingService2010::GetSystemPolicies

- ea: `0x8e90`
- end: `0x8ea9`
- name: `Microsoft.Crm.ReportingServices2010.ReportingService2010::GetSystemPolicies`
- size: `25`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## string_xrefs

- `0x8e91`: `GetSystemPolicies`

## pseudocode

```c

```

## disassembly

```asm
0x8e90  ldarg.0
0x8e91  ldstr    aGetsystempolic// "GetSystemPolicies"
0x8e96  ldc.i4.0
0x8e97  newarr   [mscorlib]System.Object
0x8e9c  call     instance object[] [System.Web.Services]System.Web.Services.Protocols.SoapHttpClientProtocol::Invoke(string, object[])
0x8ea1  ldc.i4.0
0x8ea2  ldelem.ref
0x8ea3  castclass class Microsoft.Crm.ReportingServices2010.Policy[]
0x8ea8  ret
```
