# Microsoft.Crm.Tools.Admin.InstallDynamicsSolutionsAction::.ctor

- ea: `0x5e20`
- end: `0x5e7c`
- name: `Microsoft.Crm.Tools.Admin.InstallDynamicsSolutionsAction::.ctor`
- size: `92`
- prototype: ``
- caller_count: `5`
- callee_count: `10`
- tags: `installer_update, broker_com_uri`

## callers

- `0xad10`
- `0xadc0`
- `0x102b0`
- `0x102d0`
- `0x102f0`

## callees

- `0x5db0`
- `0x5dd0`
- `0x5df0`
- `0x5e10`
- `0x71a0`
- `0x7220`
- `0x8a30`
- `0x8e30`
- `0x9870`
- `0x16fe0`

## pseudocode

```c

```

## disassembly

```asm
0x5e20  ldarg.0
0x5e21  ldarg.1
0x5e22  ldarg.s  4
0x5e24  call     instance void Microsoft.Crm.Tools.Admin.OrganizationAction::.ctor(class Microsoft.Crm.Tools.Admin.OrganizationOperation operationBase, int32 nominalProgressWeighting)
0x5e29  ldarg.0
0x5e2a  ldarg.2
0x5e2b  call     instance void Microsoft.Crm.Tools.Admin.InstallDynamicsSolutionsAction::set_IsSystemConverted(bool value)
0x5e30  ldarg.0
0x5e31  ldarg.3
0x5e32  call     instance void Microsoft.Crm.Tools.Admin.InstallDynamicsSolutionsAction::set_SolutionFilter(valuetype [Microsoft.Crm.Setup.Server.SolutionsUtility]Microsoft.Crm.Setup.Server.SolutionsUtility.SolutionTypes value)
0x5e37  ldarg.0
0x5e38  ldarg.1
0x5e39  callvirt instance class Microsoft.Crm.Tools.Admin.OrganizationInfo Microsoft.Crm.Tools.Admin.OrganizationOperation::get_OrganizationInfo()
0x5e3e  callvirt instance valuetype [Microsoft.Crm.Setup.Database.Common]Microsoft.Crm.Setup.Database.Common.OrganizationOperationType Microsoft.Crm.Tools.Admin.OrganizationInfo::get_OperationType()
0x5e43  ldc.i4.4
0x5e44  ceq
0x5e46  call     instance void Microsoft.Crm.Tools.Admin.InstallDynamicsSolutionsAction::set_IsUpgrade(bool value)
0x5e4b  ldarg.0
0x5e4c  ldarg.1
0x5e4d  callvirt instance class Microsoft.Crm.Tools.Admin.OrganizationInfo Microsoft.Crm.Tools.Admin.OrganizationOperation::get_OrganizationInfo()
0x5e52  callvirt instance class [mscorlib]System.Version Microsoft.Crm.Tools.Admin.OrganizationInfo::get_ExistingDatabaseVersion()
0x5e57  call     instance void Microsoft.Crm.Tools.Admin.InstallDynamicsSolutionsAction::set_ExistingDatabaseVersion(class [mscorlib]System.Version value)
0x5e5c  ldarg.0
0x5e5d  ldarg.1
0x5e5e  callvirt instance class Microsoft.Crm.Tools.Admin.OrganizationInfo Microsoft.Crm.Tools.Admin.OrganizationOperation::get_OrganizationInfo()
0x5e63  callvirt instance valuetype [Microsoft.Crm.Setup.Database.Common]Microsoft.Crm.Setup.Database.Common.OrganizationOperationType Microsoft.Crm.Tools.Admin.OrganizationInfo::get_OperationType()
0x5e68  ldc.i4.5
0x5e69  ceq
0x5e6b  call     instance void Microsoft.Crm.Tools.Admin.OrganizationAction::set_DoNotThrowOnFailure(bool value)
0x5e70  ldarg.0
0x5e71  newobj   instance void Microsoft.Crm.Tools.Admin.OrgDbUpdateUtility::.ctor()
0x5e76  stfld    class Microsoft.Crm.Tools.Admin.OrgDbUpdateUtility Microsoft.Crm.Tools.Admin.InstallDynamicsSolutionsAction::OrgUpdateUtility
0x5e7b  ret
```
