# Microsoft.Crm.ReportingServices2010.ReportingService2010::InheritModelItemParentSecurityAsync_0

- ea: `0x6670`
- end: `0x66ab`
- name: `Microsoft.Crm.ReportingServices2010.ReportingService2010::InheritModelItemParentSecurityAsync_0`
- size: `59`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x6660`

## callees

- `0x6670`

## string_xrefs

- `0x668b`: `InheritModelItemParentSecurity`

## pseudocode

```c

```

## disassembly

```asm
0x6670  ldarg.0
0x6671  ldfld    class [mscorlib]System.Threading.SendOrPostCallback Microsoft.Crm.ReportingServices2010.ReportingService2010::InheritModelItemParentSecurityOperationCompleted
0x6676  brtrue.s loc_668A
0x6678  ldarg.0
0x6679  ldarg.0
0x667a  ldftn    instance void Microsoft.Crm.ReportingServices2010.ReportingService2010::OnInheritModelItemParentSecurityOperationCompleted(object arg)
0x6680  newobj   instance void [mscorlib]System.Threading.SendOrPostCallback::.ctor(object, native int)
0x6685  stfld    class [mscorlib]System.Threading.SendOrPostCallback Microsoft.Crm.ReportingServices2010.ReportingService2010::InheritModelItemParentSecurityOperationCompleted
0x668a  ldarg.0
0x668b  ldstr    aInheritmodelit// "InheritModelItemParentSecurity"
0x6690  ldc.i4.2
0x6691  newarr   [mscorlib]System.Object
0x6696  dup
0x6697  ldc.i4.0
0x6698  ldarg.1
0x6699  stelem.ref
0x669a  dup
0x669b  ldc.i4.1
0x669c  ldarg.2
0x669d  stelem.ref
0x669e  ldarg.0
0x669f  ldfld    class [mscorlib]System.Threading.SendOrPostCallback Microsoft.Crm.ReportingServices2010.ReportingService2010::InheritModelItemParentSecurityOperationCompleted
0x66a4  ldarg.3
0x66a5  call     instance void [System.Web.Services]System.Web.Services.Protocols.SoapHttpClientProtocol::InvokeAsync(string, object[], class [mscorlib]System.Threading.SendOrPostCallback, object)
0x66aa  ret
```
