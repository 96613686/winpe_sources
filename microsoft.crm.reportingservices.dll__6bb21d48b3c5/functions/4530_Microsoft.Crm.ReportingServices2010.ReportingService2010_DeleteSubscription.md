# Microsoft.Crm.ReportingServices2010.ReportingService2010::DeleteSubscription

- ea: `0x4530`
- end: `0x4547`
- name: `Microsoft.Crm.ReportingServices2010.ReportingService2010::DeleteSubscription`
- size: `23`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## string_xrefs

- `0x4531`: `DeleteSubscription`

## pseudocode

```c

```

## disassembly

```asm
0x4530  ldarg.0
0x4531  ldstr    aDeletesubscrip// "DeleteSubscription"
0x4536  ldc.i4.1
0x4537  newarr   [mscorlib]System.Object
0x453c  dup
0x453d  ldc.i4.0
0x453e  ldarg.1
0x453f  stelem.ref
0x4540  call     instance object[] [System.Web.Services]System.Web.Services.Protocols.SoapHttpClientProtocol::Invoke(string, object[])
0x4545  pop
0x4546  ret
```
