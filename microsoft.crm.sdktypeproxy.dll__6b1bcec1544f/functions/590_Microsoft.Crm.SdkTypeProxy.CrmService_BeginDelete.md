# Microsoft.Crm.SdkTypeProxy.CrmService::BeginDelete

- ea: `0x590`
- end: `0x5b4`
- name: `Microsoft.Crm.SdkTypeProxy.CrmService::BeginDelete`
- size: `36`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `file_ops, service_task, broker_com_uri`

## string_xrefs

- `0x591`: `Delete`

## pseudocode

```c

```

## disassembly

```asm
0x590  ldarg.0
0x591  ldstr    aDelete// "Delete"
0x596  ldc.i4.2
0x597  newarr   [mscorlib]System.Object
0x59c  stloc.0
0x59d  ldloc.0
0x59e  ldc.i4.0
0x59f  ldarg.1
0x5a0  stelem.ref
0x5a1  ldloc.0
0x5a2  ldc.i4.1
0x5a3  ldarg.2
0x5a4  box      [mscorlib]System.Guid
0x5a9  stelem.ref
0x5aa  ldloc.0
0x5ab  ldarg.3
0x5ac  ldarg.s  4
0x5ae  call     instance class [mscorlib]System.IAsyncResult [System.Web.Services]System.Web.Services.Protocols.SoapHttpClientProtocol::BeginInvoke(string, object[], class [mscorlib]System.AsyncCallback, object)
0x5b3  ret
```
