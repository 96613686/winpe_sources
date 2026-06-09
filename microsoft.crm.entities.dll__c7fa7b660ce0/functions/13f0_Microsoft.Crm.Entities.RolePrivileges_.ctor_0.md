# Microsoft.Crm.Entities.RolePrivileges::.ctor_0

- ea: `0x13f0`
- end: `0x13fd`
- name: `Microsoft.Crm.Entities.RolePrivileges::.ctor_0`
- size: `13`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `authz_impersonation, broker_com_uri`

## string_xrefs

- `0x13f1`: `RolePrivileges`

## pseudocode

```c

```

## disassembly

```asm
0x13f0  ldarg.0
0x13f1  ldstr    aRoleprivileges// "RolePrivileges"
0x13f6  ldarg.1
0x13f7  call     instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x13fc  ret
```
