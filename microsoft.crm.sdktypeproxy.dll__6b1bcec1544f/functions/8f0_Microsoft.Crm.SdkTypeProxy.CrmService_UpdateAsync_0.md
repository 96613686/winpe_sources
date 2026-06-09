# Microsoft.Crm.SdkTypeProxy.CrmService::UpdateAsync_0

- ea: `0x8f0`
- end: `0x929`
- name: `Microsoft.Crm.SdkTypeProxy.CrmService::UpdateAsync_0`
- size: `57`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x8e0`

## callees

- `0x8f0`

## string_xrefs

- `0x90b`: `Update`

## pseudocode

```c

```

## disassembly

```asm
0x8f0  ldarg.0
0x8f1  ldfld    class [mscorlib]System.Threading.SendOrPostCallback Microsoft.Crm.SdkTypeProxy.CrmService::UpdateOperationCompleted
0x8f6  brtrue.s loc_90A
0x8f8  ldarg.0
0x8f9  ldarg.0
0x8fa  ldftn    instance void Microsoft.Crm.SdkTypeProxy.CrmService::OnUpdateOperationCompleted(object arg)
0x900  newobj   instance void [mscorlib]System.Threading.SendOrPostCallback::.ctor(object, native int)
0x905  stfld    class [mscorlib]System.Threading.SendOrPostCallback Microsoft.Crm.SdkTypeProxy.CrmService::UpdateOperationCompleted
0x90a  ldarg.0
0x90b  ldstr    aUpdate// "Update"
0x910  ldc.i4.1
0x911  newarr   [mscorlib]System.Object
0x916  stloc.0
0x917  ldloc.0
0x918  ldc.i4.0
0x919  ldarg.1
0x91a  stelem.ref
0x91b  ldloc.0
0x91c  ldarg.0
0x91d  ldfld    class [mscorlib]System.Threading.SendOrPostCallback Microsoft.Crm.SdkTypeProxy.CrmService::UpdateOperationCompleted
0x922  ldarg.2
0x923  call     instance void [System.Web.Services]System.Web.Services.Protocols.SoapHttpClientProtocol::InvokeAsync(string, object[], class [mscorlib]System.Threading.SendOrPostCallback, object)
0x928  ret
```
