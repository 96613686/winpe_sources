# Microsoft.Crm.Entities.RolePrivileges::.ctor

- ea: `0x13e0`
- end: `0x13ed`
- name: `Microsoft.Crm.Entities.RolePrivileges::.ctor`
- size: `13`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `authz_impersonation, broker_com_uri`

## string_xrefs

- `0x13e1`: `RolePrivileges`

## pseudocode

```c

```

## disassembly

```asm
0x13e0  ldarg.0
0x13e1  ldstr    aRoleprivileges// "RolePrivileges"
0x13e6  ldarg.1
0x13e7  call     instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::.ctor(string, valuetype [mscorlib]System.Guid)
0x13ec  ret
```
