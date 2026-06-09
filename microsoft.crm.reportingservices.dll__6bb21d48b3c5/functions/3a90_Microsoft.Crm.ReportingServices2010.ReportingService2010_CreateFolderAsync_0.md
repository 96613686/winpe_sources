# Microsoft.Crm.ReportingServices2010.ReportingService2010::CreateFolderAsync_0

- ea: `0x3a90`
- end: `0x3ad0`
- name: `Microsoft.Crm.ReportingServices2010.ReportingService2010::CreateFolderAsync_0`
- size: `64`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x3a80`

## callees

- `0x3a90`

## string_xrefs

- `0x3aab`: `CreateFolder`

## pseudocode

```c

```

## disassembly

```asm
0x3a90  ldarg.0
0x3a91  ldfld    class [mscorlib]System.Threading.SendOrPostCallback Microsoft.Crm.ReportingServices2010.ReportingService2010::CreateFolderOperationCompleted
0x3a96  brtrue.s loc_3AAA
0x3a98  ldarg.0
0x3a99  ldarg.0
0x3a9a  ldftn    instance void Microsoft.Crm.ReportingServices2010.ReportingService2010::OnCreateFolderOperationCompleted(object arg)
0x3aa0  newobj   instance void [mscorlib]System.Threading.SendOrPostCallback::.ctor(object, native int)
0x3aa5  stfld    class [mscorlib]System.Threading.SendOrPostCallback Microsoft.Crm.ReportingServices2010.ReportingService2010::CreateFolderOperationCompleted
0x3aaa  ldarg.0
0x3aab  ldstr    aCreatefolder// "CreateFolder"
0x3ab0  ldc.i4.3
0x3ab1  newarr   [mscorlib]System.Object
0x3ab6  dup
0x3ab7  ldc.i4.0
0x3ab8  ldarg.1
0x3ab9  stelem.ref
0x3aba  dup
0x3abb  ldc.i4.1
0x3abc  ldarg.2
0x3abd  stelem.ref
0x3abe  dup
0x3abf  ldc.i4.2
0x3ac0  ldarg.3
0x3ac1  stelem.ref
0x3ac2  ldarg.0
0x3ac3  ldfld    class [mscorlib]System.Threading.SendOrPostCallback Microsoft.Crm.ReportingServices2010.ReportingService2010::CreateFolderOperationCompleted
0x3ac8  ldarg.s  4
0x3aca  call     instance void [System.Web.Services]System.Web.Services.Protocols.SoapHttpClientProtocol::InvokeAsync(string, object[], class [mscorlib]System.Threading.SendOrPostCallback, object)
0x3acf  ret
```
