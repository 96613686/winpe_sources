# Microsoft.Crm.ReportingServices2010.ReportingService2010::CreateLinkedItemAsync_0

- ea: `0x7ae0`
- end: `0x7b25`
- name: `Microsoft.Crm.ReportingServices2010.ReportingService2010::CreateLinkedItemAsync_0`
- size: `69`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x7ad0`

## callees

- `0x7ae0`

## string_xrefs

- `0x7afb`: `CreateLinkedItem`

## pseudocode

```c

```

## disassembly

```asm
0x7ae0  ldarg.0
0x7ae1  ldfld    class [mscorlib]System.Threading.SendOrPostCallback Microsoft.Crm.ReportingServices2010.ReportingService2010::CreateLinkedItemOperationCompleted
0x7ae6  brtrue.s loc_7AFA
0x7ae8  ldarg.0
0x7ae9  ldarg.0
0x7aea  ldftn    instance void Microsoft.Crm.ReportingServices2010.ReportingService2010::OnCreateLinkedItemOperationCompleted(object arg)
0x7af0  newobj   instance void [mscorlib]System.Threading.SendOrPostCallback::.ctor(object, native int)
0x7af5  stfld    class [mscorlib]System.Threading.SendOrPostCallback Microsoft.Crm.ReportingServices2010.ReportingService2010::CreateLinkedItemOperationCompleted
0x7afa  ldarg.0
0x7afb  ldstr    aCreatelinkedit// "CreateLinkedItem"
0x7b00  ldc.i4.4
0x7b01  newarr   [mscorlib]System.Object
0x7b06  dup
0x7b07  ldc.i4.0
0x7b08  ldarg.1
0x7b09  stelem.ref
0x7b0a  dup
0x7b0b  ldc.i4.1
0x7b0c  ldarg.2
0x7b0d  stelem.ref
0x7b0e  dup
0x7b0f  ldc.i4.2
0x7b10  ldarg.3
0x7b11  stelem.ref
0x7b12  dup
0x7b13  ldc.i4.3
0x7b14  ldarg.s  4
0x7b16  stelem.ref
0x7b17  ldarg.0
0x7b18  ldfld    class [mscorlib]System.Threading.SendOrPostCallback Microsoft.Crm.ReportingServices2010.ReportingService2010::CreateLinkedItemOperationCompleted
0x7b1d  ldarg.s  5
0x7b1f  call     instance void [System.Web.Services]System.Web.Services.Protocols.SoapHttpClientProtocol::InvokeAsync(string, object[], class [mscorlib]System.Threading.SendOrPostCallback, object)
0x7b24  ret
```
