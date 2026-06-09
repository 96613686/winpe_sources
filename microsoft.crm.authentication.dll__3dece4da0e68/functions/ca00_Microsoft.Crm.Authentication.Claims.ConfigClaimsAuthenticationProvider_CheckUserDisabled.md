# Microsoft.Crm.Authentication.Claims.ConfigClaimsAuthenticationProvider::CheckUserDisabled

- ea: `0xca00`
- end: `0xca86`
- name: `Microsoft.Crm.Authentication.Claims.ConfigClaimsAuthenticationProvider::CheckUserDisabled`
- size: `134`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0xc910`

## callees

- `0x5dd0`
- `0x5f30`
- `0x6400`
- `0xca00`

## pseudocode

```c

```

## disassembly

```asm
0xca00  ldarg.2
0xca01  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xca06  brfalse.s loc_CA0A
0xca08  ldc.i4.1
0xca09  ret
0xca0a  ldarg.2
0xca0b  call     string Microsoft.Crm.Authentication.FederatedUserInformation::GetUserToken(string userPrincipalName)
0xca10  stloc.0
0xca11  newobj   instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.ConfigDBSecurity.SystemUserService::.ctor()
0xca16  stloc.1
0xca17  ldloc.1
0xca18  ldloc.0
0xca19  ldc.i4.1
0xca1a  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.ConfigDBSecurity.SystemUserData[] [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.ConfigDBSecurity.SystemUserService::RetrieveByPuid(string, bool)
0xca1f  stloc.2
0xca20  ldloc.2
0xca21  brfalse.s loc_CA27
0xca23  ldloc.2
0xca24  ldlen
0xca25  brtrue.s loc_CA51
0xca27  call     class [Microsoft.Crm.Core]Microsoft.Crm.ISkuInfoProvider [Microsoft.Crm.Core]Microsoft.Crm.SkuInfoProvider::get_Instance()
0xca2c  callvirt instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.ConfigSku [Microsoft.Crm.Core]Microsoft.Crm.ISkuInfoProvider::GetSku()
0xca31  ldc.i4.2
0xca32  bne.un.s loc_CA3D
0xca34  ldloc.0
0xca35  call     bool Microsoft.Crm.Authentication.PassportUserInformation::MatchExistingUser(string userAuth)
0xca3a  stloc.3
0xca3b  br.s     loc_CA45
0xca3d  ldarg.1
0xca3e  ldloc.0
0xca3f  call     bool Microsoft.Crm.Authentication.ActiveDirectoryUserInformation::MatchExistingUser(class [mscorlib]System.Security.Claims.ClaimsPrincipal principal, string userAuth)
0xca44  stloc.3
0xca45  ldloc.3
0xca46  brfalse.s loc_CA51
0xca48  ldloc.1
0xca49  ldloc.0
0xca4a  ldc.i4.1
0xca4b  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.ConfigDBSecurity.SystemUserData[] [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.ConfigDBSecurity.SystemUserService::RetrieveByPuid(string, bool)
0xca50  stloc.2
0xca51  ldloc.2
0xca52  brfalse.s loc_CA84
0xca54  ldloc.2
0xca55  ldlen
0xca56  brfalse.s loc_CA84
0xca58  ldloc.2
0xca59  stloc.s  4
0xca5b  ldc.i4.0
0xca5c  stloc.s  5
0xca5e  br.s     loc_CA7C
0xca60  ldloc.s  4
0xca62  ldloc.s  5
0xca64  ldelem.ref
0xca65  stloc.s  6
0xca67  ldloc.s  6
0xca69  brfalse.s loc_CA76
0xca6b  ldloc.s  6
0xca6d  callvirt instance bool [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.ConfigDBSecurity.SystemUserData::get_IsDisabled()
0xca72  brfalse.s loc_CA76
0xca74  ldc.i4.1
0xca75  ret
0xca76  ldloc.s  5
0xca78  ldc.i4.1
0xca79  add
0xca7a  stloc.s  5
0xca7c  ldloc.s  5
0xca7e  ldloc.s  4
0xca80  ldlen
0xca81  conv.i4
0xca82  blt.s    loc_CA60
0xca84  ldc.i4.0
0xca85  ret
```
