# Microsoft.Crm.Extensibility.OData.EntityController::CreateExceptionDataMethodNotAllowed

- ea: `0x11770`
- end: `0x11793`
- name: `Microsoft.Crm.Extensibility.OData.EntityController::CreateExceptionDataMethodNotAllowed`
- size: `35`
- prototype: ``
- caller_count: `12`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x11490`
- `0x11c90`
- `0x11e10`
- `0x123d0`
- `0x12490`
- `0x12570`
- `0x128a0`
- `0x12bb0`
- `0x12c10`
- `0x12d50`
- `0x12df0`
- `0x12e90`

## pseudocode

```c

```

## disassembly

```asm
0x11770  ldc.i4   0x195
0x11775  ldarg.1
0x11776  ldc.i4.0
0x11777  newarr   [mscorlib]System.Object
0x1177c  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmHttpException::.ctor(valuetype [System]System.Net.HttpStatusCode, string, object[])
0x11781  dup
0x11782  callvirt instance class [mscorlib]System.Collections.IDictionary [mscorlib]System.Exception::get_Data()
0x11787  ldstr    aAllow// "Allow"
0x1178c  ldarg.2
0x1178d  callvirt instance void [mscorlib]System.Collections.IDictionary::Add(object, object)
0x11792  ret
```
