# Microsoft.Crm.SdkTypeProxy.CrmService::ExecuteAsync_0

- ea: `0x2e0`
- end: `0x319`
- name: `Microsoft.Crm.SdkTypeProxy.CrmService::ExecuteAsync_0`
- size: `57`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x2d0`

## callees

- `0x2e0`

## pseudocode

```c

```

## disassembly

```asm
0x2e0  ldarg.0
0x2e1  ldfld    class [mscorlib]System.Threading.SendOrPostCallback Microsoft.Crm.SdkTypeProxy.CrmService::ExecuteOperationCompleted
0x2e6  brtrue.s loc_2FA
0x2e8  ldarg.0
0x2e9  ldarg.0
0x2ea  ldftn    instance void Microsoft.Crm.SdkTypeProxy.CrmService::OnExecuteOperationCompleted(object arg)
0x2f0  newobj   instance void [mscorlib]System.Threading.SendOrPostCallback::.ctor(object, native int)
0x2f5  stfld    class [mscorlib]System.Threading.SendOrPostCallback Microsoft.Crm.SdkTypeProxy.CrmService::ExecuteOperationCompleted
0x2fa  ldarg.0
0x2fb  ldstr    aExecute// "Execute"
0x300  ldc.i4.1
0x301  newarr   [mscorlib]System.Object
0x306  stloc.0
0x307  ldloc.0
0x308  ldc.i4.0
0x309  ldarg.1
0x30a  stelem.ref
0x30b  ldloc.0
0x30c  ldarg.0
0x30d  ldfld    class [mscorlib]System.Threading.SendOrPostCallback Microsoft.Crm.SdkTypeProxy.CrmService::ExecuteOperationCompleted
0x312  ldarg.2
0x313  call     instance void [System.Web.Services]System.Web.Services.Protocols.SoapHttpClientProtocol::InvokeAsync(string, object[], class [mscorlib]System.Threading.SendOrPostCallback, object)
0x318  ret
```
