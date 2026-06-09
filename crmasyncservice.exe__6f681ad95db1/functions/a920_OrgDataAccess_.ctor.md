# OrgDataAccess::.ctor

- ea: `0xa920`
- end: `0xa92f`
- name: `OrgDataAccess::.ctor`
- size: `15`
- prototype: ``
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0xaa20`
- `0xaa60`
- `0xaaa0`
- `0xaae0`
- `0xab20`

## pseudocode

```c

```

## disassembly

```asm
0xa920  ldarg.0
0xa921  ldarg.1
0xa922  call     instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase::.ctor(class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration)
0xa927  ldarg.0
0xa928  ldarg.2
0xa929  stfld    class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IConfiguration OrgDataAccess::serverConfiguration
0xa92e  ret
```
