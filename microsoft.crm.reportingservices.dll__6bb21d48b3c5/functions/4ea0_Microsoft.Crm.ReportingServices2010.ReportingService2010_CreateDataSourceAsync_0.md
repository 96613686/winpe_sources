# Microsoft.Crm.ReportingServices2010.ReportingService2010::CreateDataSourceAsync_0

- ea: `0x4ea0`
- end: `0x4eef`
- name: `Microsoft.Crm.ReportingServices2010.ReportingService2010::CreateDataSourceAsync_0`
- size: `79`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x4e90`

## callees

- `0x4ea0`

## string_xrefs

- `0x4ebb`: `CreateDataSource`

## pseudocode

```c

```

## disassembly

```asm
0x4ea0  ldarg.0
0x4ea1  ldfld    class [mscorlib]System.Threading.SendOrPostCallback Microsoft.Crm.ReportingServices2010.ReportingService2010::CreateDataSourceOperationCompleted
0x4ea6  brtrue.s loc_4EBA
0x4ea8  ldarg.0
0x4ea9  ldarg.0
0x4eaa  ldftn    instance void Microsoft.Crm.ReportingServices2010.ReportingService2010::OnCreateDataSourceOperationCompleted(object arg)
0x4eb0  newobj   instance void [mscorlib]System.Threading.SendOrPostCallback::.ctor(object, native int)
0x4eb5  stfld    class [mscorlib]System.Threading.SendOrPostCallback Microsoft.Crm.ReportingServices2010.ReportingService2010::CreateDataSourceOperationCompleted
0x4eba  ldarg.0
0x4ebb  ldstr    aCreatedatasour// "CreateDataSource"
0x4ec0  ldc.i4.5
0x4ec1  newarr   [mscorlib]System.Object
0x4ec6  dup
0x4ec7  ldc.i4.0
0x4ec8  ldarg.1
0x4ec9  stelem.ref
0x4eca  dup
0x4ecb  ldc.i4.1
0x4ecc  ldarg.2
0x4ecd  stelem.ref
0x4ece  dup
0x4ecf  ldc.i4.2
0x4ed0  ldarg.3
0x4ed1  box      [mscorlib]System.Boolean
0x4ed6  stelem.ref
0x4ed7  dup
0x4ed8  ldc.i4.3
0x4ed9  ldarg.s  4
0x4edb  stelem.ref
0x4edc  dup
0x4edd  ldc.i4.4
0x4ede  ldarg.s  5
0x4ee0  stelem.ref
0x4ee1  ldarg.0
0x4ee2  ldfld    class [mscorlib]System.Threading.SendOrPostCallback Microsoft.Crm.ReportingServices2010.ReportingService2010::CreateDataSourceOperationCompleted
0x4ee7  ldarg.s  6
0x4ee9  call     instance void [System.Web.Services]System.Web.Services.Protocols.SoapHttpClientProtocol::InvokeAsync(string, object[], class [mscorlib]System.Threading.SendOrPostCallback, object)
0x4eee  ret
```
