# Microsoft.Crm.BusinessEntities.SecurityLibrary::VerifyUser

- ea: `0x616c0`
- end: `0x618bc`
- name: `Microsoft.Crm.BusinessEntities.SecurityLibrary::VerifyUser`
- size: `508`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x67810`

## callees

- `0x613c0`
- `0x616c0`
- `0x618c0`
- `0x61e40`
- `0x63200`
- `0x632b0`
- `0x63320`
- `0x63630`
- `0x63680`
- `0x63ce0`
- `0x63db0`
- `0x67970`

## string_xrefs

- `0x61854`: `AllowImpersonationOfOrganizationSystemUser`
- `0x61877`: `The caller {0} does not have privilege to impersonate the organization SystemUser`

## pseudocode

```c

```

## disassembly

```asm
0x616c0  call     bool [Microsoft.Crm.ADUtility]Microsoft.Crm.SecurityUtils::get_IsOffline()
0x616c5  brfalse.s loc_616C8
0x616c7  ret
0x616c8  call     bool [Microsoft.Crm.Core]Microsoft.Crm.RegControl::IsInCrmInternalToolContext()
0x616cd  brfalse.s loc_616D0
0x616cf  ret
0x616d0  ldarg.0
0x616d1  ldarg.1
0x616d2  call     valuetype [mscorlib]System.Guid Microsoft.Crm.BusinessEntities.SecurityLibrary::GetUserOrganizationId(valuetype [mscorlib]System.Guid user, class Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x616d7  stloc.0
0x616d8  ldarg.1
0x616d9  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x616de  ldloc.0
0x616df  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x616e4  brfalse.s loc_616F1
0x616e6  ldstr    aTheOrganizatio// "The organization id of the user being v"...
0x616eb  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmArgumentException::.ctor(string)
0x616f0  throw
0x616f1  ldc.i4.0
0x616f2  stloc.1
0x616f3  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x616f8  stloc.2
0x616f9  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x616fe  stloc.3
0x616ff  call     bool [Microsoft.Crm.Authentication]Microsoft.Crm.Authentication.UserIdentityContext::get_IsAvailable()
0x61704  brfalse.s loc_61732
0x61706  call     class [Microsoft.Crm.Authentication]Microsoft.Crm.Authentication.UserIdentityContext [Microsoft.Crm.Authentication]Microsoft.Crm.Authentication.UserIdentityContext::get_Current()
0x6170b  callvirt instance class [mscorlib]System.Security.Claims.ClaimsPrincipal [Microsoft.Crm.Authentication]Microsoft.Crm.Authentication.UserIdentityContext::get_Principal()
0x61710  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]IdentityExtensions::GetUserId(class [mscorlib]System.Security.Claims.ClaimsPrincipal)
0x61715  stloc.2
0x61716  call     class [Microsoft.Crm.Authentication]Microsoft.Crm.Authentication.UserIdentityContext [Microsoft.Crm.Authentication]Microsoft.Crm.Authentication.UserIdentityContext::get_Current()
0x6171b  callvirt instance class [mscorlib]System.Security.Claims.ClaimsPrincipal [Microsoft.Crm.Authentication]Microsoft.Crm.Authentication.UserIdentityContext::get_Principal()
0x61720  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]IdentityExtensions::GetOrganizationId(class [mscorlib]System.Security.Claims.ClaimsPrincipal)
0x61725  stloc.3
0x61726  ldloc.2
0x61727  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x6172c  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x61731  stloc.1
0x61732  ldarg.0
0x61733  ldarg.1
0x61734  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings Microsoft.Crm.BusinessEntities.ExecutionContext::get_OrganizationSettings()
0x61739  call     valuetype SpecialUser Microsoft.Crm.BusinessEntities.SecurityLibrary::IsOrganizationSpecialUser(valuetype [mscorlib]System.Guid userId, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings organizationSettings)
0x6173e  stloc.s  4
0x61740  ldloc.s  4
0x61742  brfalse.s loc_61749
0x61744  ldc.i4.2
0x61745  ldloc.s  4
0x61747  bne.un.s loc_617B2
0x61749  ldc.i4.2
0x6174a  ldloc.s  4
0x6174c  beq.s    loc_61760
0x6174e  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.UserDataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.UserDataCache::Instance()
0x61753  ldarg.0
0x61754  ldarg.1
0x61755  callvirt instance var<u1> class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.CrmMultiOrgCacheBase`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser>::LookupEntry(void, var<u1>)
0x6175a  ldarg.1
0x6175b  call     void Microsoft.Crm.BusinessEntities.SecurityLibrary::CheckDisabledStatus(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser user, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x61760  ldloc.1
0x61761  brfalse.s loc_6176D
0x61763  ldarg.0
0x61764  ldloc.2
0x61765  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x6176a  brfalse.s loc_617B2
0x6176c  ret
0x6176d  ldc.i4.1
0x6176e  call     class [mscorlib]System.Security.Principal.WindowsIdentity [mscorlib]System.Security.Principal.WindowsIdentity::GetCurrent(bool)
0x61773  stloc.s  6
0x61775  ldloc.s  6
0x61777  brfalse.s loc_617A4
0x61779  ldnull
0x6177a  stloc.s  7
0x6177c  ldloc.s  6
0x6177e  ldarg.1
0x6177f  ldloca.s 7
0x61781  call     int32 Microsoft.Crm.BusinessEntities.SecurityLibrary::GetUserInfoInternal(class [mscorlib]System.Security.Principal.WindowsIdentity identity, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context, [out] class Microsoft.Crm.BusinessEntities.UserAuth& userInfo)
0x61786  stloc.s  8
0x61788  ldloc.s  8
0x6178a  brtrue.s loc_617A4
0x6178c  ldloc.s  7
0x6178e  brfalse.s loc_617A4
0x61790  ldarg.0
0x61791  ldloc.s  7
0x61793  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.BusinessEntities.UserAuth::get_UserId()
0x61798  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x6179d  brfalse.s loc_617A4
0x6179f  leave    loc_618BB
0x617a4  leave.s  loc_617B2
0x617a6  ldloc.s  6
0x617a8  brfalse.s loc_617B1
0x617aa  ldloc.s  6
0x617ac  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x617b1  endfinally
0x617b2  ldarg.1
0x617b3  call     bool Microsoft.Crm.BusinessEntities.SecurityLibrary::IsInLiveWebServiceSecurityContext(class Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x617b8  stloc.s  5
0x617ba  ldloc.s  5
0x617bc  brtrue.s loc_617D4
0x617be  ldloc.1
0x617bf  brfalse  loc_618A2
0x617c4  ldarg.1
0x617c5  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x617ca  call     bool [Microsoft.Crm.Core]Microsoft.Crm.CrmAuthenticationContext::IsClaimsEnabled(valuetype [mscorlib]System.Guid)
0x617cf  brfalse  loc_618A2
0x617d4  call     class [Microsoft.Crm.Authentication]Microsoft.Crm.Authentication.UserIdentityContext [Microsoft.Crm.Authentication]Microsoft.Crm.Authentication.UserIdentityContext::get_Current()
0x617d9  callvirt instance class [mscorlib]System.Security.Claims.ClaimsPrincipal [Microsoft.Crm.Authentication]Microsoft.Crm.Authentication.UserIdentityContext::get_Principal()
0x617de  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]IdentityExtensions::GetCallerId(class [mscorlib]System.Security.Claims.ClaimsPrincipal)
0x617e3  stloc.s  9
0x617e5  ldloc.s  9
0x617e7  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x617ec  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x617f1  brfalse  loc_618A1
0x617f6  ldloc.s  9
0x617f8  ldloc.2
0x617f9  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x617fe  brfalse  loc_618A1
0x61803  ldloc.2
0x61804  ldarg.1
0x61805  call     bool Microsoft.Crm.BusinessEntities.SecurityLibrary::TryCheckImpersonatePrivilegeForCaller(valuetype [mscorlib]System.Guid userId, class Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x6180a  brtrue.s loc_6182C
0x6180c  ldloc.s  5
0x6180e  brtrue.s loc_6181B
0x61810  ldloc.2
0x61811  ldloc.3
0x61812  ldarg.1
0x61813  call     bool Microsoft.Crm.BusinessEntities.SecurityLibrary::IsMemberOfPrivUserGroup(valuetype [mscorlib]System.Guid userId, valuetype [mscorlib]System.Guid organizationId, class Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x61818  brfalse.s loc_6181B
0x6181a  ret
0x6181b  ldc.i4   0x8004A110
0x61820  ldc.i4.0
0x61821  newarr   [mscorlib]System.Object
0x61826  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0x6182b  throw
0x6182c  ldarg.1
0x6182d  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x61832  ldloc.s  9
0x61834  ldarg.1
0x61835  call     valuetype SpecialUser Microsoft.Crm.BusinessEntities.SecurityLibrary::IsOrganizationSpecialUser(valuetype [mscorlib]System.Guid organizationId, valuetype [mscorlib]System.Guid userId, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x6183a  ldc.i4.1
0x6183b  bne.un.s loc_618A1
0x6183d  ldloc.s  5
0x6183f  brtrue.s loc_6184C
0x61841  ldloc.2
0x61842  ldloc.3
0x61843  ldarg.1
0x61844  call     bool Microsoft.Crm.BusinessEntities.SecurityLibrary::IsMemberOfPrivUserGroup(valuetype [mscorlib]System.Guid userId, valuetype [mscorlib]System.Guid organizationId, class Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x61849  brfalse.s loc_6184C
0x6184b  ret
0x6184c  ldc.i4.0
0x6184d  stloc.s  0xA
0x6184f  call     class [Microsoft.Crm.Core]Microsoft.Crm.LocatorService [Microsoft.Crm.Core]Microsoft.Crm.LocatorService::get_Instance()
0x61854  ldstr    aAllowimpersona// "AllowImpersonationOfOrganizationSystemU"...
0x61859  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.LocatorService::GetDeploymentSetting(string)
0x6185e  unbox.any [mscorlib]System.Boolean
0x61863  stloc.s  0xA
0x61865  leave.s  loc_6186A
0x61867  pop
0x61868  leave.s  loc_6186A
0x6186a  ldloc.s  0xA
0x6186c  brtrue.s loc_618A1
0x6186e  ldnull
0x6186f  ldarg.1
0x61870  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x61875  ldc.i4.s 0x14
0x61877  ldstr    aTheCaller0Does// "The caller {0} does not have privilege "...
0x6187c  ldc.i4.1
0x6187d  newarr   [mscorlib]System.Object
0x61882  dup
0x61883  ldc.i4.0
0x61884  ldloc.2
0x61885  box      [mscorlib]System.Guid
0x6188a  stelem.ref
0x6188b  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x61890  ldc.i4   0x8004A110
0x61895  ldc.i4.0
0x61896  newarr   [mscorlib]System.Object
0x6189b  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0x618a0  throw
0x618a1  ret
0x618a2  ldarg.1
0x618a3  call     bool Microsoft.Crm.BusinessEntities.SecurityLibrary::TryCheckPrivilegeGroupForOrganization(class Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x618a8  brtrue.s loc_618BB
0x618aa  ldc.i4   0x80040204
0x618af  ldc.i4.0
0x618b0  newarr   [mscorlib]System.Object
0x618b5  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0x618ba  throw
0x618bb  ret
```
