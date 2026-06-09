# Microsoft.Crm.Entities.Privilege::.ctor

- ea: `0x1360`
- end: `0x136d`
- name: `Microsoft.Crm.Entities.Privilege::.ctor`
- size: `13`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `authz_impersonation, broker_com_uri`

## string_xrefs

- `0x1361`: `Privilege`

## pseudocode

```c

```

## disassembly

```asm
0x1360  ldarg.0
0x1361  ldstr    aPrivilege// "Privilege"
0x1366  ldarg.1
0x1367  call     instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::.ctor(string, valuetype [mscorlib]System.Guid)
0x136c  ret
```
