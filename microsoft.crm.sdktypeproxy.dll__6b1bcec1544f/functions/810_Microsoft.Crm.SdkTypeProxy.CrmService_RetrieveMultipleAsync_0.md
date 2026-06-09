# Microsoft.Crm.SdkTypeProxy.CrmService::RetrieveMultipleAsync_0

- ea: `0x810`
- end: `0x849`
- name: `Microsoft.Crm.SdkTypeProxy.CrmService::RetrieveMultipleAsync_0`
- size: `57`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x800`

## callees

- `0x810`

## pseudocode

```c

```

## disassembly

```asm
0x810  ldarg.0
0x811  ldfld    class [mscorlib]System.Threading.SendOrPostCallback Microsoft.Crm.SdkTypeProxy.CrmService::RetrieveMultipleOperationCompleted
0x816  brtrue.s loc_82A
0x818  ldarg.0
0x819  ldarg.0
0x81a  ldftn    instance void Microsoft.Crm.SdkTypeProxy.CrmService::OnRetrieveMultipleOperationCompleted(object arg)
0x820  newobj   instance void [mscorlib]System.Threading.SendOrPostCallback::.ctor(object, native int)
0x825  stfld    class [mscorlib]System.Threading.SendOrPostCallback Microsoft.Crm.SdkTypeProxy.CrmService::RetrieveMultipleOperationCompleted
0x82a  ldarg.0
0x82b  ldstr    aRetrievemultip// "RetrieveMultiple"
0x830  ldc.i4.1
0x831  newarr   [mscorlib]System.Object
0x836  stloc.0
0x837  ldloc.0
0x838  ldc.i4.0
0x839  ldarg.1
0x83a  stelem.ref
0x83b  ldloc.0
0x83c  ldarg.0
0x83d  ldfld    class [mscorlib]System.Threading.SendOrPostCallback Microsoft.Crm.SdkTypeProxy.CrmService::RetrieveMultipleOperationCompleted
0x842  ldarg.2
0x843  call     instance void [System.Web.Services]System.Web.Services.Protocols.SoapHttpClientProtocol::InvokeAsync(string, object[], class [mscorlib]System.Threading.SendOrPostCallback, object)
0x848  ret
```
