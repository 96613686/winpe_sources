# Microsoft.Crm.SdkTypeProxy.Metadata.MetadataService::ExecuteAsync_0

- ea: `0x36240`
- end: `0x36279`
- name: `Microsoft.Crm.SdkTypeProxy.Metadata.MetadataService::ExecuteAsync_0`
- size: `57`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x36230`

## callees

- `0x36240`

## pseudocode

```c

```

## disassembly

```asm
0x36240  ldarg.0
0x36241  ldfld    class [mscorlib]System.Threading.SendOrPostCallback Microsoft.Crm.SdkTypeProxy.Metadata.MetadataService::ExecuteOperationCompleted
0x36246  brtrue.s loc_3625A
0x36248  ldarg.0
0x36249  ldarg.0
0x3624a  ldftn    instance void Microsoft.Crm.SdkTypeProxy.Metadata.MetadataService::OnExecuteOperationCompleted(object arg)
0x36250  newobj   instance void [mscorlib]System.Threading.SendOrPostCallback::.ctor(object, native int)
0x36255  stfld    class [mscorlib]System.Threading.SendOrPostCallback Microsoft.Crm.SdkTypeProxy.Metadata.MetadataService::ExecuteOperationCompleted
0x3625a  ldarg.0
0x3625b  ldstr    aExecute// "Execute"
0x36260  ldc.i4.1
0x36261  newarr   [mscorlib]System.Object
0x36266  stloc.0
0x36267  ldloc.0
0x36268  ldc.i4.0
0x36269  ldarg.1
0x3626a  stelem.ref
0x3626b  ldloc.0
0x3626c  ldarg.0
0x3626d  ldfld    class [mscorlib]System.Threading.SendOrPostCallback Microsoft.Crm.SdkTypeProxy.Metadata.MetadataService::ExecuteOperationCompleted
0x36272  ldarg.2
0x36273  call     instance void [System.Web.Services]System.Web.Services.Protocols.SoapHttpClientProtocol::InvokeAsync(string, object[], class [mscorlib]System.Threading.SendOrPostCallback, object)
0x36278  ret
```
