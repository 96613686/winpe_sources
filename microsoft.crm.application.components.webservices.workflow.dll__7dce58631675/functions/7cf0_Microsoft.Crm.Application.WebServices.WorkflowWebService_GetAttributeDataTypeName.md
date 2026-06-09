# Microsoft.Crm.Application.WebServices.WorkflowWebService::GetAttributeDataTypeName

- ea: `0x7cf0`
- end: `0x7d13`
- name: `Microsoft.Crm.Application.WebServices.WorkflowWebService::GetAttributeDataTypeName`
- size: `35`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x7bb0`

## callees

- `0x7cf0`

## pseudocode

```c

```

## disassembly

```asm
0x7cf0  ldarg.1
0x7cf1  ldc.i4.8
0x7cf2  bne.un.s loc_7D05
0x7cf4  ldc.i4.s 0x10
0x7cf6  stloc.0
0x7cf7  ldloca.s 0
0x7cf9  constrained. [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeType
0x7cff  callvirt instance string [mscorlib]System.Object::ToString()
0x7d04  ret
0x7d05  ldarga.s 1
0x7d07  constrained. [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeType
0x7d0d  callvirt instance string [mscorlib]System.Object::ToString()
0x7d12  ret
```
