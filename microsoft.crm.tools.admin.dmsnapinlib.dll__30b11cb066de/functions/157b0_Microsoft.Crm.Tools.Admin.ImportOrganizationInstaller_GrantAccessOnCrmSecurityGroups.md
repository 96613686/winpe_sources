# Microsoft.Crm.Tools.Admin.ImportOrganizationInstaller::GrantAccessOnCrmSecurityGroups

- ea: `0x157b0`
- end: `0x157e4`
- name: `Microsoft.Crm.Tools.Admin.ImportOrganizationInstaller::GrantAccessOnCrmSecurityGroups`
- size: `52`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callers

- `0x15350`
- `0x155c0`

## callees

- `0x157b0`

## string_xrefs

- `0x157b7`: `Granting access to CRM security groups for the deployment`

## pseudocode

```c

```

## disassembly

```asm
0x157b0  ldarg.1
0x157b1  newobj   instance void [Microsoft.Crm.Setup.DatabaseInstaller]Microsoft.Crm.Setup.Database.DatabaseUtility::.ctor(valuetype [mscorlib]System.Guid)
0x157b6  stloc.0
0x157b7  ldstr    aGrantingAccess// "Granting access to CRM security groups "...
0x157bc  ldc.i4.0
0x157bd  newarr   [mscorlib]System.Object
0x157c2  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteInfo(string, object[])
0x157c7  ldloc.0
0x157c8  callvirt instance void [Microsoft.Crm.Setup.DatabaseInstaller]Microsoft.Crm.Setup.Database.DatabaseUtility::Open()
0x157cd  ldloc.0
0x157ce  ldarg.2
0x157cf  ldarg.3
0x157d0  ldarg.s  4
0x157d2  callvirt instance void [Microsoft.Crm.Setup.DatabaseInstaller]Microsoft.Crm.Setup.Database.DatabaseUtility::GrantAccess(string, string, string)
0x157d7  leave.s  loc_157E3
0x157d9  ldloc.0
0x157da  brfalse.s loc_157E2
0x157dc  ldloc.0
0x157dd  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x157e2  endfinally
0x157e3  ret
```
