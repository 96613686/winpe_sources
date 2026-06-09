# Microsoft.Crm.ReportingServices2010.ReportingService2010::RemoveAllModelItemPolicies

- ea: `0x6c80`
- end: `0x6c97`
- name: `Microsoft.Crm.ReportingServices2010.ReportingService2010::RemoveAllModelItemPolicies`
- size: `23`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## string_xrefs

- `0x6c81`: `RemoveAllModelItemPolicies`

## pseudocode

```c

```

## disassembly

```asm
0x6c80  ldarg.0
0x6c81  ldstr    aRemoveallmodel// "RemoveAllModelItemPolicies"
0x6c86  ldc.i4.1
0x6c87  newarr   [mscorlib]System.Object
0x6c8c  dup
0x6c8d  ldc.i4.0
0x6c8e  ldarg.1
0x6c8f  stelem.ref
0x6c90  call     instance object[] [System.Web.Services]System.Web.Services.Protocols.SoapHttpClientProtocol::Invoke(string, object[])
0x6c95  pop
0x6c96  ret
```
