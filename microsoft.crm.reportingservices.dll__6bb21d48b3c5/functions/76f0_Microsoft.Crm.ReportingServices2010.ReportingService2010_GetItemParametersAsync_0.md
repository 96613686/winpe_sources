# Microsoft.Crm.ReportingServices2010.ReportingService2010::GetItemParametersAsync_0

- ea: `0x76f0`
- end: `0x773f`
- name: `Microsoft.Crm.ReportingServices2010.ReportingService2010::GetItemParametersAsync_0`
- size: `79`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x76e0`

## callees

- `0x76f0`

## string_xrefs

- `0x770b`: `GetItemParameters`

## pseudocode

```c

```

## disassembly

```asm
0x76f0  ldarg.0
0x76f1  ldfld    class [mscorlib]System.Threading.SendOrPostCallback Microsoft.Crm.ReportingServices2010.ReportingService2010::GetItemParametersOperationCompleted
0x76f6  brtrue.s loc_770A
0x76f8  ldarg.0
0x76f9  ldarg.0
0x76fa  ldftn    instance void Microsoft.Crm.ReportingServices2010.ReportingService2010::OnGetItemParametersOperationCompleted(object arg)
0x7700  newobj   instance void [mscorlib]System.Threading.SendOrPostCallback::.ctor(object, native int)
0x7705  stfld    class [mscorlib]System.Threading.SendOrPostCallback Microsoft.Crm.ReportingServices2010.ReportingService2010::GetItemParametersOperationCompleted
0x770a  ldarg.0
0x770b  ldstr    aGetitemparamet// "GetItemParameters"
0x7710  ldc.i4.5
0x7711  newarr   [mscorlib]System.Object
0x7716  dup
0x7717  ldc.i4.0
0x7718  ldarg.1
0x7719  stelem.ref
0x771a  dup
0x771b  ldc.i4.1
0x771c  ldarg.2
0x771d  stelem.ref
0x771e  dup
0x771f  ldc.i4.2
0x7720  ldarg.3
0x7721  box      [mscorlib]System.Boolean
0x7726  stelem.ref
0x7727  dup
0x7728  ldc.i4.3
0x7729  ldarg.s  4
0x772b  stelem.ref
0x772c  dup
0x772d  ldc.i4.4
0x772e  ldarg.s  5
0x7730  stelem.ref
0x7731  ldarg.0
0x7732  ldfld    class [mscorlib]System.Threading.SendOrPostCallback Microsoft.Crm.ReportingServices2010.ReportingService2010::GetItemParametersOperationCompleted
0x7737  ldarg.s  6
0x7739  call     instance void [System.Web.Services]System.Web.Services.Protocols.SoapHttpClientProtocol::InvokeAsync(string, object[], class [mscorlib]System.Threading.SendOrPostCallback, object)
0x773e  ret
```
