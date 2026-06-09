# Microsoft.Crm.ReportingServices2010.ReportingService2010::CreateCatalogItemAsync_0

- ea: `0x2f60`
- end: `0x2fb4`
- name: `Microsoft.Crm.ReportingServices2010.ReportingService2010::CreateCatalogItemAsync_0`
- size: `84`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x2f40`

## callees

- `0x2f60`

## string_xrefs

- `0x2f7b`: `CreateCatalogItem`

## pseudocode

```c

```

## disassembly

```asm
0x2f60  ldarg.0
0x2f61  ldfld    class [mscorlib]System.Threading.SendOrPostCallback Microsoft.Crm.ReportingServices2010.ReportingService2010::CreateCatalogItemOperationCompleted
0x2f66  brtrue.s loc_2F7A
0x2f68  ldarg.0
0x2f69  ldarg.0
0x2f6a  ldftn    instance void Microsoft.Crm.ReportingServices2010.ReportingService2010::OnCreateCatalogItemOperationCompleted(object arg)
0x2f70  newobj   instance void [mscorlib]System.Threading.SendOrPostCallback::.ctor(object, native int)
0x2f75  stfld    class [mscorlib]System.Threading.SendOrPostCallback Microsoft.Crm.ReportingServices2010.ReportingService2010::CreateCatalogItemOperationCompleted
0x2f7a  ldarg.0
0x2f7b  ldstr    aCreatecatalogi// "CreateCatalogItem"
0x2f80  ldc.i4.6
0x2f81  newarr   [mscorlib]System.Object
0x2f86  dup
0x2f87  ldc.i4.0
0x2f88  ldarg.1
0x2f89  stelem.ref
0x2f8a  dup
0x2f8b  ldc.i4.1
0x2f8c  ldarg.2
0x2f8d  stelem.ref
0x2f8e  dup
0x2f8f  ldc.i4.2
0x2f90  ldarg.3
0x2f91  stelem.ref
0x2f92  dup
0x2f93  ldc.i4.3
0x2f94  ldarg.s  4
0x2f96  box      [mscorlib]System.Boolean
0x2f9b  stelem.ref
0x2f9c  dup
0x2f9d  ldc.i4.4
0x2f9e  ldarg.s  5
0x2fa0  stelem.ref
0x2fa1  dup
0x2fa2  ldc.i4.5
0x2fa3  ldarg.s  6
0x2fa5  stelem.ref
0x2fa6  ldarg.0
0x2fa7  ldfld    class [mscorlib]System.Threading.SendOrPostCallback Microsoft.Crm.ReportingServices2010.ReportingService2010::CreateCatalogItemOperationCompleted
0x2fac  ldarg.s  7
0x2fae  call     instance void [System.Web.Services]System.Web.Services.Protocols.SoapHttpClientProtocol::InvokeAsync(string, object[], class [mscorlib]System.Threading.SendOrPostCallback, object)
0x2fb3  ret
```
