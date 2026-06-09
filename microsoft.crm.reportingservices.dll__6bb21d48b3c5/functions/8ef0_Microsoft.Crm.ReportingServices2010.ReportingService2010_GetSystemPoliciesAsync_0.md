# Microsoft.Crm.ReportingServices2010.ReportingService2010::GetSystemPoliciesAsync_0

- ea: `0x8ef0`
- end: `0x8f23`
- name: `Microsoft.Crm.ReportingServices2010.ReportingService2010::GetSystemPoliciesAsync_0`
- size: `51`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x8ee0`

## callees

- `0x8ef0`

## string_xrefs

- `0x8f0b`: `GetSystemPolicies`

## pseudocode

```c

```

## disassembly

```asm
0x8ef0  ldarg.0
0x8ef1  ldfld    class [mscorlib]System.Threading.SendOrPostCallback Microsoft.Crm.ReportingServices2010.ReportingService2010::GetSystemPoliciesOperationCompleted
0x8ef6  brtrue.s loc_8F0A
0x8ef8  ldarg.0
0x8ef9  ldarg.0
0x8efa  ldftn    instance void Microsoft.Crm.ReportingServices2010.ReportingService2010::OnGetSystemPoliciesOperationCompleted(object arg)
0x8f00  newobj   instance void [mscorlib]System.Threading.SendOrPostCallback::.ctor(object, native int)
0x8f05  stfld    class [mscorlib]System.Threading.SendOrPostCallback Microsoft.Crm.ReportingServices2010.ReportingService2010::GetSystemPoliciesOperationCompleted
0x8f0a  ldarg.0
0x8f0b  ldstr    aGetsystempolic// "GetSystemPolicies"
0x8f10  ldc.i4.0
0x8f11  newarr   [mscorlib]System.Object
0x8f16  ldarg.0
0x8f17  ldfld    class [mscorlib]System.Threading.SendOrPostCallback Microsoft.Crm.ReportingServices2010.ReportingService2010::GetSystemPoliciesOperationCompleted
0x8f1c  ldarg.1
0x8f1d  call     instance void [System.Web.Services]System.Web.Services.Protocols.SoapHttpClientProtocol::InvokeAsync(string, object[], class [mscorlib]System.Threading.SendOrPostCallback, object)
0x8f22  ret
```
