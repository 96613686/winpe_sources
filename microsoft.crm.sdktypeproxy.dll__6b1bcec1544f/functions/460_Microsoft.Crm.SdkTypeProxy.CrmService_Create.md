# Microsoft.Crm.SdkTypeProxy.CrmService::Create

- ea: `0x460`
- end: `0x481`
- name: `Microsoft.Crm.SdkTypeProxy.CrmService::Create`
- size: `33`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## string_xrefs

- `0x461`: `Create`

## pseudocode

```c

```

## disassembly

```asm
0x460  ldarg.0
0x461  ldstr    aCreate// "Create"
0x466  ldc.i4.1
0x467  newarr   [mscorlib]System.Object
0x46c  stloc.1
0x46d  ldloc.1
0x46e  ldc.i4.0
0x46f  ldarg.1
0x470  stelem.ref
0x471  ldloc.1
0x472  call     instance object[] [System.Web.Services]System.Web.Services.Protocols.SoapHttpClientProtocol::Invoke(string, object[])
0x477  stloc.0
0x478  ldloc.0
0x479  ldc.i4.0
0x47a  ldelem.ref
0x47b  unbox.any [mscorlib]System.Guid
0x480  ret
```
