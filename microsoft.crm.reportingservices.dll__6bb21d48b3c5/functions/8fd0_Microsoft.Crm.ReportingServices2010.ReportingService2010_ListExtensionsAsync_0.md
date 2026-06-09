# Microsoft.Crm.ReportingServices2010.ReportingService2010::ListExtensionsAsync_0

- ea: `0x8fd0`
- end: `0x9007`
- name: `Microsoft.Crm.ReportingServices2010.ReportingService2010::ListExtensionsAsync_0`
- size: `55`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x8fc0`

## callees

- `0x8fd0`

## string_xrefs

- `0x8feb`: `ListExtensions`

## pseudocode

```c

```

## disassembly

```asm
0x8fd0  ldarg.0
0x8fd1  ldfld    class [mscorlib]System.Threading.SendOrPostCallback Microsoft.Crm.ReportingServices2010.ReportingService2010::ListExtensionsOperationCompleted
0x8fd6  brtrue.s loc_8FEA
0x8fd8  ldarg.0
0x8fd9  ldarg.0
0x8fda  ldftn    instance void Microsoft.Crm.ReportingServices2010.ReportingService2010::OnListExtensionsOperationCompleted(object arg)
0x8fe0  newobj   instance void [mscorlib]System.Threading.SendOrPostCallback::.ctor(object, native int)
0x8fe5  stfld    class [mscorlib]System.Threading.SendOrPostCallback Microsoft.Crm.ReportingServices2010.ReportingService2010::ListExtensionsOperationCompleted
0x8fea  ldarg.0
0x8feb  ldstr    aListextensions// "ListExtensions"
0x8ff0  ldc.i4.1
0x8ff1  newarr   [mscorlib]System.Object
0x8ff6  dup
0x8ff7  ldc.i4.0
0x8ff8  ldarg.1
0x8ff9  stelem.ref
0x8ffa  ldarg.0
0x8ffb  ldfld    class [mscorlib]System.Threading.SendOrPostCallback Microsoft.Crm.ReportingServices2010.ReportingService2010::ListExtensionsOperationCompleted
0x9000  ldarg.2
0x9001  call     instance void [System.Web.Services]System.Web.Services.Protocols.SoapHttpClientProtocol::InvokeAsync(string, object[], class [mscorlib]System.Threading.SendOrPostCallback, object)
0x9006  ret
```
