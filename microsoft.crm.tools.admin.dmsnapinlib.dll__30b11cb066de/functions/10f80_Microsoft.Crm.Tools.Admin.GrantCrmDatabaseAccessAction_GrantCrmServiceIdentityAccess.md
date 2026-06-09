# Microsoft.Crm.Tools.Admin.GrantCrmDatabaseAccessAction::GrantCrmServiceIdentityAccess

- ea: `0x10f80`
- end: `0x11071`
- name: `Microsoft.Crm.Tools.Admin.GrantCrmDatabaseAccessAction::GrantCrmServiceIdentityAccess`
- size: `241`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x10f60`

## callees

- `0x10f80`

## string_xrefs

- `0x10f88`: `GrantCrmServiceIdentityAccess does not apply for XDB org`
- `0x10f99`: `MSCRMAsyncService`
- `0x1102c`: `Machine does not have AppServer or ApiServer roles installed.`
- `0x1104e`: `Grant access for ServiceAccount: {0}, WebAppAccount: {1}.`

## pseudocode

```c

```

## disassembly

```asm
0x10f80  ldarg.0
0x10f81  call     bool [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.CrmOrganizationService::IsBackedByXdb(valuetype [mscorlib]System.Guid)
0x10f86  brfalse.s loc_10F99
0x10f88  ldstr    aGrantcrmservic// "GrantCrmServiceIdentityAccess does not "...
0x10f8d  ldc.i4.0
0x10f8e  newarr   [mscorlib]System.Object
0x10f93  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteInfoFormat(string, object[])
0x10f98  ret
0x10f99  ldstr    aMscrmasyncserv// "MSCRMAsyncService"
0x10f9e  call     string [Microsoft.Crm.Setup.Server.Utility]Microsoft.Crm.Setup.Server.Utility.CrmServerUtility::GetServiceAccount(string)
0x10fa3  stloc.0
0x10fa4  ldnull
0x10fa5  stloc.1
0x10fa6  newobj   instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.CrmServerService::.ctor()
0x10fab  newobj   instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.ServerFilter::.ctor()
0x10fb0  dup
0x10fb1  ldarg.1
0x10fb2  callvirt instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.ServerFilter::set_Name(string)
0x10fb7  stloc.2
0x10fb8  ldloc.2
0x10fb9  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.ServerData[] [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.CrmServerService::RetrieveMultiple(class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.ServerFilter)
0x10fbe  stloc.3
0x10fbf  ldloc.3
0x10fc0  ldlen
0x10fc1  brfalse.s loc_1103E
0x10fc3  ldloc.3
0x10fc4  ldc.i4.0
0x10fc5  ldelem.ref
0x10fc6  stloc.s  4
0x10fc8  ldloc.s  4
0x10fca  callvirt instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.ServerRoles [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.ServerData::get_Roles()
0x10fcf  box      [Microsoft.Crm.Core]Microsoft.Crm.ServerRoles
0x10fd4  ldc.i4.1
0x10fd5  box      [Microsoft.Crm.Core]Microsoft.Crm.ServerRoles
0x10fda  call     instance bool [mscorlib]System.Enum::HasFlag(class [mscorlib]System.Enum)
0x10fdf  brtrue.s loc_10FFE
0x10fe1  ldloc.s  4
0x10fe3  callvirt instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.ServerRoles [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.ServerData::get_Roles()
0x10fe8  box      [Microsoft.Crm.Core]Microsoft.Crm.ServerRoles
0x10fed  ldc.i4   0x8000
0x10ff2  box      [Microsoft.Crm.Core]Microsoft.Crm.ServerRoles
0x10ff7  call     instance bool [mscorlib]System.Enum::HasFlag(class [mscorlib]System.Enum)
0x10ffc  br.s     loc_10FFF
0x10ffe  ldc.i4.1
0x10fff  brfalse.s loc_1102C
0x11001  ldstr    aCrmapppool// "CRMAppPool"
0x11006  call     bool [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.IIsUtility::AppPoolExists(string)
0x1100b  brfalse.s loc_1101A
0x1100d  ldstr    aCrmapppool// "CRMAppPool"
0x11012  call     string [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.IIsUtility::GetAspNetServiceAccountName(string)
0x11017  stloc.1
0x11018  br.s     loc_1104E
0x1101a  ldstr    aUnableToFindAp// "Unable to find application pool for App"...
0x1101f  ldc.i4.0
0x11020  newarr   [mscorlib]System.Object
0x11025  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteWarning(string, object[])
0x1102a  br.s     loc_1104E
0x1102c  ldstr    aMachineDoesNot// "Machine does not have AppServer or ApiS"...
0x11031  ldc.i4.0
0x11032  newarr   [mscorlib]System.Object
0x11037  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteInfo(string, object[])
0x1103c  br.s     loc_1104E
0x1103e  ldstr    aServerDataForT// "Server data for the local machine was n"...
0x11043  ldc.i4.0
0x11044  newarr   [mscorlib]System.Object
0x11049  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteError(string, object[])
0x1104e  ldstr    aGrantAccessFor// "Grant access for ServiceAccount: {0}, W"...
0x11053  ldc.i4.2
0x11054  newarr   [mscorlib]System.Object
0x11059  dup
0x1105a  ldc.i4.0
0x1105b  ldloc.0
0x1105c  stelem.ref
0x1105d  dup
0x1105e  ldc.i4.1
0x1105f  ldloc.1
0x11060  stelem.ref
0x11061  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteInfoFormat(string, object[])
0x11066  ldarg.1
0x11067  ldarg.2
0x11068  ldloc.0
0x11069  ldloc.1
0x1106a  ldarg.0
0x1106b  call     void [Microsoft.Crm.Setup.Server.Utility]Microsoft.Crm.Setup.Server.Utility.SqlUtility::GrantServiceAccountAccess(string, string, string, string, valuetype [mscorlib]System.Guid)
0x11070  ret
```
