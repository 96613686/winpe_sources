# Microsoft.Crm.Entities.WizardAccessPrivilege::.ctor

- ea: `0x4410`
- end: `0x441d`
- name: `Microsoft.Crm.Entities.WizardAccessPrivilege::.ctor`
- size: `13`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `authz_impersonation, broker_com_uri`

## string_xrefs

- `0x4411`: `WizardAccessPrivilege`

## pseudocode

```c

```

## disassembly

```asm
0x4410  ldarg.0
0x4411  ldstr    aWizardaccesspr// "WizardAccessPrivilege"
0x4416  ldarg.1
0x4417  call     instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::.ctor(string, valuetype [mscorlib]System.Guid)
0x441c  ret
```
