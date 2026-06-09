# Microsoft.Crm.ReportingServices2010.ReportingService2010::GetReportServerConfigInfoAsync_0

- ea: `0x8a90`
- end: `0x8acc`
- name: `Microsoft.Crm.ReportingServices2010.ReportingService2010::GetReportServerConfigInfoAsync_0`
- size: `60`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x8a80`

## callees

- `0x8a90`

## string_xrefs

- `0x8aab`: `GetReportServerConfigInfo`

## pseudocode

```c

```

## disassembly

```asm
0x8a90  ldarg.0
0x8a91  ldfld    class [mscorlib]System.Threading.SendOrPostCallback Microsoft.Crm.ReportingServices2010.ReportingService2010::GetReportServerConfigInfoOperationCompleted
0x8a96  brtrue.s loc_8AAA
0x8a98  ldarg.0
0x8a99  ldarg.0
0x8a9a  ldftn    instance void Microsoft.Crm.ReportingServices2010.ReportingService2010::OnGetReportServerConfigInfoOperationCompleted(object arg)
0x8aa0  newobj   instance void [mscorlib]System.Threading.SendOrPostCallback::.ctor(object, native int)
0x8aa5  stfld    class [mscorlib]System.Threading.SendOrPostCallback Microsoft.Crm.ReportingServices2010.ReportingService2010::GetReportServerConfigInfoOperationCompleted
0x8aaa  ldarg.0
0x8aab  ldstr    aGetreportserve// "GetReportServerConfigInfo"
0x8ab0  ldc.i4.1
0x8ab1  newarr   [mscorlib]System.Object
0x8ab6  dup
0x8ab7  ldc.i4.0
0x8ab8  ldarg.1
0x8ab9  box      [mscorlib]System.Boolean
0x8abe  stelem.ref
0x8abf  ldarg.0
0x8ac0  ldfld    class [mscorlib]System.Threading.SendOrPostCallback Microsoft.Crm.ReportingServices2010.ReportingService2010::GetReportServerConfigInfoOperationCompleted
0x8ac5  ldarg.2
0x8ac6  call     instance void [System.Web.Services]System.Web.Services.Protocols.SoapHttpClientProtocol::InvokeAsync(string, object[], class [mscorlib]System.Threading.SendOrPostCallback, object)
0x8acb  ret
```
