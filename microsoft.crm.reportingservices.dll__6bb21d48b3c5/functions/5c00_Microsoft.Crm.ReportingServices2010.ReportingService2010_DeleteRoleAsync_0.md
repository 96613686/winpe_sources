# Microsoft.Crm.ReportingServices2010.ReportingService2010::DeleteRoleAsync_0

- ea: `0x5c00`
- end: `0x5c37`
- name: `Microsoft.Crm.ReportingServices2010.ReportingService2010::DeleteRoleAsync_0`
- size: `55`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x5bf0`

## callees

- `0x5c00`

## string_xrefs

- `0x5c1b`: `DeleteRole`

## pseudocode

```c

```

## disassembly

```asm
0x5c00  ldarg.0
0x5c01  ldfld    class [mscorlib]System.Threading.SendOrPostCallback Microsoft.Crm.ReportingServices2010.ReportingService2010::DeleteRoleOperationCompleted
0x5c06  brtrue.s loc_5C1A
0x5c08  ldarg.0
0x5c09  ldarg.0
0x5c0a  ldftn    instance void Microsoft.Crm.ReportingServices2010.ReportingService2010::OnDeleteRoleOperationCompleted(object arg)
0x5c10  newobj   instance void [mscorlib]System.Threading.SendOrPostCallback::.ctor(object, native int)
0x5c15  stfld    class [mscorlib]System.Threading.SendOrPostCallback Microsoft.Crm.ReportingServices2010.ReportingService2010::DeleteRoleOperationCompleted
0x5c1a  ldarg.0
0x5c1b  ldstr    aDeleterole// "DeleteRole"
0x5c20  ldc.i4.1
0x5c21  newarr   [mscorlib]System.Object
0x5c26  dup
0x5c27  ldc.i4.0
0x5c28  ldarg.1
0x5c29  stelem.ref
0x5c2a  ldarg.0
0x5c2b  ldfld    class [mscorlib]System.Threading.SendOrPostCallback Microsoft.Crm.ReportingServices2010.ReportingService2010::DeleteRoleOperationCompleted
0x5c30  ldarg.2
0x5c31  call     instance void [System.Web.Services]System.Web.Services.Protocols.SoapHttpClientProtocol::InvokeAsync(string, object[], class [mscorlib]System.Threading.SendOrPostCallback, object)
0x5c36  ret
```
