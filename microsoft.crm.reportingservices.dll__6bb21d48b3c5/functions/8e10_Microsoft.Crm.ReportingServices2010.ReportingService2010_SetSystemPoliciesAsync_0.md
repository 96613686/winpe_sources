# Microsoft.Crm.ReportingServices2010.ReportingService2010::SetSystemPoliciesAsync_0

- ea: `0x8e10`
- end: `0x8e47`
- name: `Microsoft.Crm.ReportingServices2010.ReportingService2010::SetSystemPoliciesAsync_0`
- size: `55`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x8e00`

## callees

- `0x8e10`

## string_xrefs

- `0x8e2b`: `SetSystemPolicies`

## pseudocode

```c

```

## disassembly

```asm
0x8e10  ldarg.0
0x8e11  ldfld    class [mscorlib]System.Threading.SendOrPostCallback Microsoft.Crm.ReportingServices2010.ReportingService2010::SetSystemPoliciesOperationCompleted
0x8e16  brtrue.s loc_8E2A
0x8e18  ldarg.0
0x8e19  ldarg.0
0x8e1a  ldftn    instance void Microsoft.Crm.ReportingServices2010.ReportingService2010::OnSetSystemPoliciesOperationCompleted(object arg)
0x8e20  newobj   instance void [mscorlib]System.Threading.SendOrPostCallback::.ctor(object, native int)
0x8e25  stfld    class [mscorlib]System.Threading.SendOrPostCallback Microsoft.Crm.ReportingServices2010.ReportingService2010::SetSystemPoliciesOperationCompleted
0x8e2a  ldarg.0
0x8e2b  ldstr    aSetsystempolic// "SetSystemPolicies"
0x8e30  ldc.i4.1
0x8e31  newarr   [mscorlib]System.Object
0x8e36  dup
0x8e37  ldc.i4.0
0x8e38  ldarg.1
0x8e39  stelem.ref
0x8e3a  ldarg.0
0x8e3b  ldfld    class [mscorlib]System.Threading.SendOrPostCallback Microsoft.Crm.ReportingServices2010.ReportingService2010::SetSystemPoliciesOperationCompleted
0x8e40  ldarg.2
0x8e41  call     instance void [System.Web.Services]System.Web.Services.Protocols.SoapHttpClientProtocol::InvokeAsync(string, object[], class [mscorlib]System.Threading.SendOrPostCallback, object)
0x8e46  ret
```
