# Microsoft.Crm.Tools.Admin.LicenseController::get_LicenseService

- ea: `0x17a30`
- end: `0x17a4a`
- name: `Microsoft.Crm.Tools.Admin.LicenseController::get_LicenseService`
- size: `26`
- prototype: ``
- caller_count: `7`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x17a50`
- `0x17a70`
- `0x17ae0`
- `0x17af0`
- `0x17b10`
- `0x17b20`
- `0x17b80`

## callees

- `0x17a30`

## pseudocode

```c

```

## disassembly

```asm
0x17a30  ldarg.0
0x17a31  ldfld    class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.CrmLicenseService Microsoft.Crm.Tools.Admin.LicenseController::licenseService
0x17a36  brtrue.s loc_17A43
0x17a38  ldarg.0
0x17a39  newobj   instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.CrmLicenseService::.ctor()
0x17a3e  stfld    class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.CrmLicenseService Microsoft.Crm.Tools.Admin.LicenseController::licenseService
0x17a43  ldarg.0
0x17a44  ldfld    class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.CrmLicenseService Microsoft.Crm.Tools.Admin.LicenseController::licenseService
0x17a49  ret
```
