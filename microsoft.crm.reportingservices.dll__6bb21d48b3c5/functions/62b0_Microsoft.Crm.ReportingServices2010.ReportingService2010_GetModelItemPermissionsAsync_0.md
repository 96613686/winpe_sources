# Microsoft.Crm.ReportingServices2010.ReportingService2010::GetModelItemPermissionsAsync_0

- ea: `0x62b0`
- end: `0x62eb`
- name: `Microsoft.Crm.ReportingServices2010.ReportingService2010::GetModelItemPermissionsAsync_0`
- size: `59`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x62a0`

## callees

- `0x62b0`

## string_xrefs

- `0x62cb`: `GetModelItemPermissions`

## pseudocode

```c

```

## disassembly

```asm
0x62b0  ldarg.0
0x62b1  ldfld    class [mscorlib]System.Threading.SendOrPostCallback Microsoft.Crm.ReportingServices2010.ReportingService2010::GetModelItemPermissionsOperationCompleted
0x62b6  brtrue.s loc_62CA
0x62b8  ldarg.0
0x62b9  ldarg.0
0x62ba  ldftn    instance void Microsoft.Crm.ReportingServices2010.ReportingService2010::OnGetModelItemPermissionsOperationCompleted(object arg)
0x62c0  newobj   instance void [mscorlib]System.Threading.SendOrPostCallback::.ctor(object, native int)
0x62c5  stfld    class [mscorlib]System.Threading.SendOrPostCallback Microsoft.Crm.ReportingServices2010.ReportingService2010::GetModelItemPermissionsOperationCompleted
0x62ca  ldarg.0
0x62cb  ldstr    aGetmodelitempe// "GetModelItemPermissions"
0x62d0  ldc.i4.2
0x62d1  newarr   [mscorlib]System.Object
0x62d6  dup
0x62d7  ldc.i4.0
0x62d8  ldarg.1
0x62d9  stelem.ref
0x62da  dup
0x62db  ldc.i4.1
0x62dc  ldarg.2
0x62dd  stelem.ref
0x62de  ldarg.0
0x62df  ldfld    class [mscorlib]System.Threading.SendOrPostCallback Microsoft.Crm.ReportingServices2010.ReportingService2010::GetModelItemPermissionsOperationCompleted
0x62e4  ldarg.3
0x62e5  call     instance void [System.Web.Services]System.Web.Services.Protocols.SoapHttpClientProtocol::InvokeAsync(string, object[], class [mscorlib]System.Threading.SendOrPostCallback, object)
0x62ea  ret
```
