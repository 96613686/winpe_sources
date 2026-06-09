# Microsoft.Crm.SdkTypeProxy.CrmService::FetchAsync_0

- ea: `0x3e0`
- end: `0x419`
- name: `Microsoft.Crm.SdkTypeProxy.CrmService::FetchAsync_0`
- size: `57`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x3d0`

## callees

- `0x3e0`

## pseudocode

```c

```

## disassembly

```asm
0x3e0  ldarg.0
0x3e1  ldfld    class [mscorlib]System.Threading.SendOrPostCallback Microsoft.Crm.SdkTypeProxy.CrmService::FetchOperationCompleted
0x3e6  brtrue.s loc_3FA
0x3e8  ldarg.0
0x3e9  ldarg.0
0x3ea  ldftn    instance void Microsoft.Crm.SdkTypeProxy.CrmService::OnFetchOperationCompleted(object arg)
0x3f0  newobj   instance void [mscorlib]System.Threading.SendOrPostCallback::.ctor(object, native int)
0x3f5  stfld    class [mscorlib]System.Threading.SendOrPostCallback Microsoft.Crm.SdkTypeProxy.CrmService::FetchOperationCompleted
0x3fa  ldarg.0
0x3fb  ldstr    aFetch// "Fetch"
0x400  ldc.i4.1
0x401  newarr   [mscorlib]System.Object
0x406  stloc.0
0x407  ldloc.0
0x408  ldc.i4.0
0x409  ldarg.1
0x40a  stelem.ref
0x40b  ldloc.0
0x40c  ldarg.0
0x40d  ldfld    class [mscorlib]System.Threading.SendOrPostCallback Microsoft.Crm.SdkTypeProxy.CrmService::FetchOperationCompleted
0x412  ldarg.2
0x413  call     instance void [System.Web.Services]System.Web.Services.Protocols.SoapHttpClientProtocol::InvokeAsync(string, object[], class [mscorlib]System.Threading.SendOrPostCallback, object)
0x418  ret
```
