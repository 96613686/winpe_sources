# Microsoft.Crm.SdkTypeProxy.CrmService::DeleteAsync_0

- ea: `0x5e0`
- end: `0x622`
- name: `Microsoft.Crm.SdkTypeProxy.CrmService::DeleteAsync_0`
- size: `66`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x5d0`

## callees

- `0x5e0`

## string_xrefs

- `0x5fb`: `Delete`

## pseudocode

```c

```

## disassembly

```asm
0x5e0  ldarg.0
0x5e1  ldfld    class [mscorlib]System.Threading.SendOrPostCallback Microsoft.Crm.SdkTypeProxy.CrmService::DeleteOperationCompleted
0x5e6  brtrue.s loc_5FA
0x5e8  ldarg.0
0x5e9  ldarg.0
0x5ea  ldftn    instance void Microsoft.Crm.SdkTypeProxy.CrmService::OnDeleteOperationCompleted(object arg)
0x5f0  newobj   instance void [mscorlib]System.Threading.SendOrPostCallback::.ctor(object, native int)
0x5f5  stfld    class [mscorlib]System.Threading.SendOrPostCallback Microsoft.Crm.SdkTypeProxy.CrmService::DeleteOperationCompleted
0x5fa  ldarg.0
0x5fb  ldstr    aDelete// "Delete"
0x600  ldc.i4.2
0x601  newarr   [mscorlib]System.Object
0x606  stloc.0
0x607  ldloc.0
0x608  ldc.i4.0
0x609  ldarg.1
0x60a  stelem.ref
0x60b  ldloc.0
0x60c  ldc.i4.1
0x60d  ldarg.2
0x60e  box      [mscorlib]System.Guid
0x613  stelem.ref
0x614  ldloc.0
0x615  ldarg.0
0x616  ldfld    class [mscorlib]System.Threading.SendOrPostCallback Microsoft.Crm.SdkTypeProxy.CrmService::DeleteOperationCompleted
0x61b  ldarg.3
0x61c  call     instance void [System.Web.Services]System.Web.Services.Protocols.SoapHttpClientProtocol::InvokeAsync(string, object[], class [mscorlib]System.Threading.SendOrPostCallback, object)
0x621  ret
```
