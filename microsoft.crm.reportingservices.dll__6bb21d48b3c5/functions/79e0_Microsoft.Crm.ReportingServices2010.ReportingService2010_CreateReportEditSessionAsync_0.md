# Microsoft.Crm.ReportingServices2010.ReportingService2010::CreateReportEditSessionAsync_0

- ea: `0x79e0`
- end: `0x7a20`
- name: `Microsoft.Crm.ReportingServices2010.ReportingService2010::CreateReportEditSessionAsync_0`
- size: `64`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x79d0`

## callees

- `0x79e0`

## string_xrefs

- `0x79fb`: `CreateReportEditSession`

## pseudocode

```c

```

## disassembly

```asm
0x79e0  ldarg.0
0x79e1  ldfld    class [mscorlib]System.Threading.SendOrPostCallback Microsoft.Crm.ReportingServices2010.ReportingService2010::CreateReportEditSessionOperationCompleted
0x79e6  brtrue.s loc_79FA
0x79e8  ldarg.0
0x79e9  ldarg.0
0x79ea  ldftn    instance void Microsoft.Crm.ReportingServices2010.ReportingService2010::OnCreateReportEditSessionOperationCompleted(object arg)
0x79f0  newobj   instance void [mscorlib]System.Threading.SendOrPostCallback::.ctor(object, native int)
0x79f5  stfld    class [mscorlib]System.Threading.SendOrPostCallback Microsoft.Crm.ReportingServices2010.ReportingService2010::CreateReportEditSessionOperationCompleted
0x79fa  ldarg.0
0x79fb  ldstr    aCreatereported// "CreateReportEditSession"
0x7a00  ldc.i4.3
0x7a01  newarr   [mscorlib]System.Object
0x7a06  dup
0x7a07  ldc.i4.0
0x7a08  ldarg.1
0x7a09  stelem.ref
0x7a0a  dup
0x7a0b  ldc.i4.1
0x7a0c  ldarg.2
0x7a0d  stelem.ref
0x7a0e  dup
0x7a0f  ldc.i4.2
0x7a10  ldarg.3
0x7a11  stelem.ref
0x7a12  ldarg.0
0x7a13  ldfld    class [mscorlib]System.Threading.SendOrPostCallback Microsoft.Crm.ReportingServices2010.ReportingService2010::CreateReportEditSessionOperationCompleted
0x7a18  ldarg.s  4
0x7a1a  call     instance void [System.Web.Services]System.Web.Services.Protocols.SoapHttpClientProtocol::InvokeAsync(string, object[], class [mscorlib]System.Threading.SendOrPostCallback, object)
0x7a1f  ret
```
