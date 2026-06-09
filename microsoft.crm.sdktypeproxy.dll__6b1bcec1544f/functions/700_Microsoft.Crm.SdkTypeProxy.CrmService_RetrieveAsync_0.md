# Microsoft.Crm.SdkTypeProxy.CrmService::RetrieveAsync_0

- ea: `0x700`
- end: `0x747`
- name: `Microsoft.Crm.SdkTypeProxy.CrmService::RetrieveAsync_0`
- size: `71`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x6f0`

## callees

- `0x700`

## pseudocode

```c

```

## disassembly

```asm
0x700  ldarg.0
0x701  ldfld    class [mscorlib]System.Threading.SendOrPostCallback Microsoft.Crm.SdkTypeProxy.CrmService::RetrieveOperationCompleted
0x706  brtrue.s loc_71A
0x708  ldarg.0
0x709  ldarg.0
0x70a  ldftn    instance void Microsoft.Crm.SdkTypeProxy.CrmService::OnRetrieveOperationCompleted(object arg)
0x710  newobj   instance void [mscorlib]System.Threading.SendOrPostCallback::.ctor(object, native int)
0x715  stfld    class [mscorlib]System.Threading.SendOrPostCallback Microsoft.Crm.SdkTypeProxy.CrmService::RetrieveOperationCompleted
0x71a  ldarg.0
0x71b  ldstr    aRetrieve// "Retrieve"
0x720  ldc.i4.3
0x721  newarr   [mscorlib]System.Object
0x726  stloc.0
0x727  ldloc.0
0x728  ldc.i4.0
0x729  ldarg.1
0x72a  stelem.ref
0x72b  ldloc.0
0x72c  ldc.i4.1
0x72d  ldarg.2
0x72e  box      [mscorlib]System.Guid
0x733  stelem.ref
0x734  ldloc.0
0x735  ldc.i4.2
0x736  ldarg.3
0x737  stelem.ref
0x738  ldloc.0
0x739  ldarg.0
0x73a  ldfld    class [mscorlib]System.Threading.SendOrPostCallback Microsoft.Crm.SdkTypeProxy.CrmService::RetrieveOperationCompleted
0x73f  ldarg.s  4
0x741  call     instance void [System.Web.Services]System.Web.Services.Protocols.SoapHttpClientProtocol::InvokeAsync(string, object[], class [mscorlib]System.Threading.SendOrPostCallback, object)
0x746  ret
```
