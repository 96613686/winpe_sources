# Microsoft.Crm.SdkTypeProxy.CrmService::Delete

- ea: `0x560`
- end: `0x582`
- name: `Microsoft.Crm.SdkTypeProxy.CrmService::Delete`
- size: `34`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `file_ops, service_task, broker_com_uri`

## string_xrefs

- `0x561`: `Delete`

## pseudocode

```c

```

## disassembly

```asm
0x560  ldarg.0
0x561  ldstr    aDelete// "Delete"
0x566  ldc.i4.2
0x567  newarr   [mscorlib]System.Object
0x56c  stloc.0
0x56d  ldloc.0
0x56e  ldc.i4.0
0x56f  ldarg.1
0x570  stelem.ref
0x571  ldloc.0
0x572  ldc.i4.1
0x573  ldarg.2
0x574  box      [mscorlib]System.Guid
0x579  stelem.ref
0x57a  ldloc.0
0x57b  call     instance object[] [System.Web.Services]System.Web.Services.Protocols.SoapHttpClientProtocol::Invoke(string, object[])
0x580  pop
0x581  ret
```
