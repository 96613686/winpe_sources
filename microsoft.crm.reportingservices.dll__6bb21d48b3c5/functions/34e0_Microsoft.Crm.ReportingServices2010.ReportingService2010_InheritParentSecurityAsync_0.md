# Microsoft.Crm.ReportingServices2010.ReportingService2010::InheritParentSecurityAsync_0

- ea: `0x34e0`
- end: `0x3517`
- name: `Microsoft.Crm.ReportingServices2010.ReportingService2010::InheritParentSecurityAsync_0`
- size: `55`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x34d0`

## callees

- `0x34e0`

## string_xrefs

- `0x34fb`: `InheritParentSecurity`

## pseudocode

```c

```

## disassembly

```asm
0x34e0  ldarg.0
0x34e1  ldfld    class [mscorlib]System.Threading.SendOrPostCallback Microsoft.Crm.ReportingServices2010.ReportingService2010::InheritParentSecurityOperationCompleted
0x34e6  brtrue.s loc_34FA
0x34e8  ldarg.0
0x34e9  ldarg.0
0x34ea  ldftn    instance void Microsoft.Crm.ReportingServices2010.ReportingService2010::OnInheritParentSecurityOperationCompleted(object arg)
0x34f0  newobj   instance void [mscorlib]System.Threading.SendOrPostCallback::.ctor(object, native int)
0x34f5  stfld    class [mscorlib]System.Threading.SendOrPostCallback Microsoft.Crm.ReportingServices2010.ReportingService2010::InheritParentSecurityOperationCompleted
0x34fa  ldarg.0
0x34fb  ldstr    aInheritparents// "InheritParentSecurity"
0x3500  ldc.i4.1
0x3501  newarr   [mscorlib]System.Object
0x3506  dup
0x3507  ldc.i4.0
0x3508  ldarg.1
0x3509  stelem.ref
0x350a  ldarg.0
0x350b  ldfld    class [mscorlib]System.Threading.SendOrPostCallback Microsoft.Crm.ReportingServices2010.ReportingService2010::InheritParentSecurityOperationCompleted
0x3510  ldarg.2
0x3511  call     instance void [System.Web.Services]System.Web.Services.Protocols.SoapHttpClientProtocol::InvokeAsync(string, object[], class [mscorlib]System.Threading.SendOrPostCallback, object)
0x3516  ret
```
