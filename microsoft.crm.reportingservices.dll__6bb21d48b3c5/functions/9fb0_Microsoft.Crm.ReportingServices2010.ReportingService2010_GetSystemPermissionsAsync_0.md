# Microsoft.Crm.ReportingServices2010.ReportingService2010::GetSystemPermissionsAsync_0

- ea: `0x9fb0`
- end: `0x9fe3`
- name: `Microsoft.Crm.ReportingServices2010.ReportingService2010::GetSystemPermissionsAsync_0`
- size: `51`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x9fa0`

## callees

- `0x9fb0`

## string_xrefs

- `0x9fcb`: `GetSystemPermissions`

## pseudocode

```c

```

## disassembly

```asm
0x9fb0  ldarg.0
0x9fb1  ldfld    class [mscorlib]System.Threading.SendOrPostCallback Microsoft.Crm.ReportingServices2010.ReportingService2010::GetSystemPermissionsOperationCompleted
0x9fb6  brtrue.s loc_9FCA
0x9fb8  ldarg.0
0x9fb9  ldarg.0
0x9fba  ldftn    instance void Microsoft.Crm.ReportingServices2010.ReportingService2010::OnGetSystemPermissionsOperationCompleted(object arg)
0x9fc0  newobj   instance void [mscorlib]System.Threading.SendOrPostCallback::.ctor(object, native int)
0x9fc5  stfld    class [mscorlib]System.Threading.SendOrPostCallback Microsoft.Crm.ReportingServices2010.ReportingService2010::GetSystemPermissionsOperationCompleted
0x9fca  ldarg.0
0x9fcb  ldstr    aGetsystempermi// "GetSystemPermissions"
0x9fd0  ldc.i4.0
0x9fd1  newarr   [mscorlib]System.Object
0x9fd6  ldarg.0
0x9fd7  ldfld    class [mscorlib]System.Threading.SendOrPostCallback Microsoft.Crm.ReportingServices2010.ReportingService2010::GetSystemPermissionsOperationCompleted
0x9fdc  ldarg.1
0x9fdd  call     instance void [System.Web.Services]System.Web.Services.Protocols.SoapHttpClientProtocol::InvokeAsync(string, object[], class [mscorlib]System.Threading.SendOrPostCallback, object)
0x9fe2  ret
```
