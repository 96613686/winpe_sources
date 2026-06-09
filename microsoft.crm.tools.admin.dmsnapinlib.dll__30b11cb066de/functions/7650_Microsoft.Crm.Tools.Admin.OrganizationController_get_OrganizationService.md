# Microsoft.Crm.Tools.Admin.OrganizationController::get_OrganizationService

- ea: `0x7650`
- end: `0x766a`
- name: `Microsoft.Crm.Tools.Admin.OrganizationController::get_OrganizationService`
- size: `26`
- prototype: ``
- caller_count: `7`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x76c0`
- `0x76d0`
- `0x7720`
- `0x7870`
- `0x7ca0`
- `0x7d30`
- `0x8320`

## callees

- `0x7650`

## pseudocode

```c

```

## disassembly

```asm
0x7650  ldarg.0
0x7651  ldfld    class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.CrmOrganizationService Microsoft.Crm.Tools.Admin.OrganizationController::organizationService
0x7656  brtrue.s loc_7663
0x7658  ldarg.0
0x7659  newobj   instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.CrmOrganizationService::.ctor()
0x765e  stfld    class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.CrmOrganizationService Microsoft.Crm.Tools.Admin.OrganizationController::organizationService
0x7663  ldarg.0
0x7664  ldfld    class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.CrmOrganizationService Microsoft.Crm.Tools.Admin.OrganizationController::organizationService
0x7669  ret
```
