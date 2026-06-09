# Microsoft.Crm.SdkTypeProxy.CrmTypes::CreateCrmDateTime

- ea: `0x37480`
- end: `0x3748f`
- name: `Microsoft.Crm.SdkTypeProxy.CrmTypes::CreateCrmDateTime`
- size: `15`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x377b0`
- `0x377e0`

## pseudocode

```c

```

## disassembly

```asm
0x37480  newobj   instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime::.ctor()
0x37485  stloc.0
0x37486  ldloc.0
0x37487  ldarg.0
0x37488  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime::set_Value(string)
0x3748d  ldloc.0
0x3748e  ret
```
