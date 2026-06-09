# Microsoft.Crm.ReportingServices2010.ReportingService2010::CreateItemHistorySnapshotAsync_0

- ea: `0x8450`
- end: `0x8487`
- name: `Microsoft.Crm.ReportingServices2010.ReportingService2010::CreateItemHistorySnapshotAsync_0`
- size: `55`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x8440`

## callees

- `0x8450`

## string_xrefs

- `0x846b`: `CreateItemHistorySnapshot`

## pseudocode

```c

```

## disassembly

```asm
0x8450  ldarg.0
0x8451  ldfld    class [mscorlib]System.Threading.SendOrPostCallback Microsoft.Crm.ReportingServices2010.ReportingService2010::CreateItemHistorySnapshotOperationCompleted
0x8456  brtrue.s loc_846A
0x8458  ldarg.0
0x8459  ldarg.0
0x845a  ldftn    instance void Microsoft.Crm.ReportingServices2010.ReportingService2010::OnCreateItemHistorySnapshotOperationCompleted(object arg)
0x8460  newobj   instance void [mscorlib]System.Threading.SendOrPostCallback::.ctor(object, native int)
0x8465  stfld    class [mscorlib]System.Threading.SendOrPostCallback Microsoft.Crm.ReportingServices2010.ReportingService2010::CreateItemHistorySnapshotOperationCompleted
0x846a  ldarg.0
0x846b  ldstr    aCreateitemhist// "CreateItemHistorySnapshot"
0x8470  ldc.i4.1
0x8471  newarr   [mscorlib]System.Object
0x8476  dup
0x8477  ldc.i4.0
0x8478  ldarg.1
0x8479  stelem.ref
0x847a  ldarg.0
0x847b  ldfld    class [mscorlib]System.Threading.SendOrPostCallback Microsoft.Crm.ReportingServices2010.ReportingService2010::CreateItemHistorySnapshotOperationCompleted
0x8480  ldarg.2
0x8481  call     instance void [System.Web.Services]System.Web.Services.Protocols.SoapHttpClientProtocol::InvokeAsync(string, object[], class [mscorlib]System.Threading.SendOrPostCallback, object)
0x8486  ret
```
