# Microsoft.Crm.ReportingServices2010.ReportingService2010::SetSystemPolicies

- ea: `0x8db0`
- end: `0x8dc7`
- name: `Microsoft.Crm.ReportingServices2010.ReportingService2010::SetSystemPolicies`
- size: `23`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## string_xrefs

- `0x8db1`: `SetSystemPolicies`

## pseudocode

```c

```

## disassembly

```asm
0x8db0  ldarg.0
0x8db1  ldstr    aSetsystempolic// "SetSystemPolicies"
0x8db6  ldc.i4.1
0x8db7  newarr   [mscorlib]System.Object
0x8dbc  dup
0x8dbd  ldc.i4.0
0x8dbe  ldarg.1
0x8dbf  stelem.ref
0x8dc0  call     instance object[] [System.Web.Services]System.Web.Services.Protocols.SoapHttpClientProtocol::Invoke(string, object[])
0x8dc5  pop
0x8dc6  ret
```
