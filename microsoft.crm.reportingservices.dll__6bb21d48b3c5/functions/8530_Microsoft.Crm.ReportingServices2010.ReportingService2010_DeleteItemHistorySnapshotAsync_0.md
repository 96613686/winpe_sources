# Microsoft.Crm.ReportingServices2010.ReportingService2010::DeleteItemHistorySnapshotAsync_0

- ea: `0x8530`
- end: `0x856b`
- name: `Microsoft.Crm.ReportingServices2010.ReportingService2010::DeleteItemHistorySnapshotAsync_0`
- size: `59`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x8520`

## callees

- `0x8530`

## string_xrefs

- `0x854b`: `DeleteItemHistorySnapshot`

## pseudocode

```c

```

## disassembly

```asm
0x8530  ldarg.0
0x8531  ldfld    class [mscorlib]System.Threading.SendOrPostCallback Microsoft.Crm.ReportingServices2010.ReportingService2010::DeleteItemHistorySnapshotOperationCompleted
0x8536  brtrue.s loc_854A
0x8538  ldarg.0
0x8539  ldarg.0
0x853a  ldftn    instance void Microsoft.Crm.ReportingServices2010.ReportingService2010::OnDeleteItemHistorySnapshotOperationCompleted(object arg)
0x8540  newobj   instance void [mscorlib]System.Threading.SendOrPostCallback::.ctor(object, native int)
0x8545  stfld    class [mscorlib]System.Threading.SendOrPostCallback Microsoft.Crm.ReportingServices2010.ReportingService2010::DeleteItemHistorySnapshotOperationCompleted
0x854a  ldarg.0
0x854b  ldstr    aDeleteitemhist// "DeleteItemHistorySnapshot"
0x8550  ldc.i4.2
0x8551  newarr   [mscorlib]System.Object
0x8556  dup
0x8557  ldc.i4.0
0x8558  ldarg.1
0x8559  stelem.ref
0x855a  dup
0x855b  ldc.i4.1
0x855c  ldarg.2
0x855d  stelem.ref
0x855e  ldarg.0
0x855f  ldfld    class [mscorlib]System.Threading.SendOrPostCallback Microsoft.Crm.ReportingServices2010.ReportingService2010::DeleteItemHistorySnapshotOperationCompleted
0x8564  ldarg.3
0x8565  call     instance void [System.Web.Services]System.Web.Services.Protocols.SoapHttpClientProtocol::InvokeAsync(string, object[], class [mscorlib]System.Threading.SendOrPostCallback, object)
0x856a  ret
```
