# Microsoft.Crm.ReportingServices2010.ReportingService2010::UpdateItemExecutionSnapshotAsync_0

- ea: `0x8060`
- end: `0x8097`
- name: `Microsoft.Crm.ReportingServices2010.ReportingService2010::UpdateItemExecutionSnapshotAsync_0`
- size: `55`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x8050`

## callees

- `0x8060`

## string_xrefs

- `0x807b`: `UpdateItemExecutionSnapshot`

## pseudocode

```c

```

## disassembly

```asm
0x8060  ldarg.0
0x8061  ldfld    class [mscorlib]System.Threading.SendOrPostCallback Microsoft.Crm.ReportingServices2010.ReportingService2010::UpdateItemExecutionSnapshotOperationCompleted
0x8066  brtrue.s loc_807A
0x8068  ldarg.0
0x8069  ldarg.0
0x806a  ldftn    instance void Microsoft.Crm.ReportingServices2010.ReportingService2010::OnUpdateItemExecutionSnapshotOperationCompleted(object arg)
0x8070  newobj   instance void [mscorlib]System.Threading.SendOrPostCallback::.ctor(object, native int)
0x8075  stfld    class [mscorlib]System.Threading.SendOrPostCallback Microsoft.Crm.ReportingServices2010.ReportingService2010::UpdateItemExecutionSnapshotOperationCompleted
0x807a  ldarg.0
0x807b  ldstr    aUpdateitemexec// "UpdateItemExecutionSnapshot"
0x8080  ldc.i4.1
0x8081  newarr   [mscorlib]System.Object
0x8086  dup
0x8087  ldc.i4.0
0x8088  ldarg.1
0x8089  stelem.ref
0x808a  ldarg.0
0x808b  ldfld    class [mscorlib]System.Threading.SendOrPostCallback Microsoft.Crm.ReportingServices2010.ReportingService2010::UpdateItemExecutionSnapshotOperationCompleted
0x8090  ldarg.2
0x8091  call     instance void [System.Web.Services]System.Web.Services.Protocols.SoapHttpClientProtocol::InvokeAsync(string, object[], class [mscorlib]System.Threading.SendOrPostCallback, object)
0x8096  ret
```
