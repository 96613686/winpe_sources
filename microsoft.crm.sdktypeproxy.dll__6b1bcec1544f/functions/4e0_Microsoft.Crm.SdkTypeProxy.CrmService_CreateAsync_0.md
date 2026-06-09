# Microsoft.Crm.SdkTypeProxy.CrmService::CreateAsync_0

- ea: `0x4e0`
- end: `0x519`
- name: `Microsoft.Crm.SdkTypeProxy.CrmService::CreateAsync_0`
- size: `57`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x4d0`

## callees

- `0x4e0`

## string_xrefs

- `0x4fb`: `Create`

## pseudocode

```c

```

## disassembly

```asm
0x4e0  ldarg.0
0x4e1  ldfld    class [mscorlib]System.Threading.SendOrPostCallback Microsoft.Crm.SdkTypeProxy.CrmService::CreateOperationCompleted
0x4e6  brtrue.s loc_4FA
0x4e8  ldarg.0
0x4e9  ldarg.0
0x4ea  ldftn    instance void Microsoft.Crm.SdkTypeProxy.CrmService::OnCreateOperationCompleted(object arg)
0x4f0  newobj   instance void [mscorlib]System.Threading.SendOrPostCallback::.ctor(object, native int)
0x4f5  stfld    class [mscorlib]System.Threading.SendOrPostCallback Microsoft.Crm.SdkTypeProxy.CrmService::CreateOperationCompleted
0x4fa  ldarg.0
0x4fb  ldstr    aCreate// "Create"
0x500  ldc.i4.1
0x501  newarr   [mscorlib]System.Object
0x506  stloc.0
0x507  ldloc.0
0x508  ldc.i4.0
0x509  ldarg.1
0x50a  stelem.ref
0x50b  ldloc.0
0x50c  ldarg.0
0x50d  ldfld    class [mscorlib]System.Threading.SendOrPostCallback Microsoft.Crm.SdkTypeProxy.CrmService::CreateOperationCompleted
0x512  ldarg.2
0x513  call     instance void [System.Web.Services]System.Web.Services.Protocols.SoapHttpClientProtocol::InvokeAsync(string, object[], class [mscorlib]System.Threading.SendOrPostCallback, object)
0x518  ret
```
