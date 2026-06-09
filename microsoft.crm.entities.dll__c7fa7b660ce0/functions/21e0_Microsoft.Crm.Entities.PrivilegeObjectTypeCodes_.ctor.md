# Microsoft.Crm.Entities.PrivilegeObjectTypeCodes::.ctor

- ea: `0x21e0`
- end: `0x21ed`
- name: `Microsoft.Crm.Entities.PrivilegeObjectTypeCodes::.ctor`
- size: `13`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `authz_impersonation, broker_com_uri`

## string_xrefs

- `0x21e1`: `PrivilegeObjectTypeCodes`

## pseudocode

```c

```

## disassembly

```asm
0x21e0  ldarg.0
0x21e1  ldstr    aPrivilegeobjec// "PrivilegeObjectTypeCodes"
0x21e6  ldarg.1
0x21e7  call     instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::.ctor(string, valuetype [mscorlib]System.Guid)
0x21ec  ret
```
