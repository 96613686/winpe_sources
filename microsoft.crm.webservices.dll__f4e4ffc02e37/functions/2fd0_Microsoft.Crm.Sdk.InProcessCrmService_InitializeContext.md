# Microsoft.Crm.Sdk.InProcessCrmService::InitializeContext

- ea: `0x2fd0`
- end: `0x30d2`
- name: `Microsoft.Crm.Sdk.InProcessCrmService::InitializeContext`
- size: `258`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x2e20`
- `0x8180`

## callees

- `0x2fd0`

## string_xrefs

- `0x3004`: `Caller must be authenticated before using InProcessCrmService.`

## pseudocode

```c

```

## disassembly

```asm
0x2fd0  call     bool [Microsoft.Crm.Core]Microsoft.Crm.RegistryCache::get_IsOffline()
0x2fd5  brtrue.s loc_3043
0x2fd7  call     bool [Microsoft.Crm.Core]Microsoft.Crm.RegControl::IsInHosterContext()
0x2fdc  brtrue.s loc_3043
0x2fde  ldarg.0
0x2fdf  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Sdk.InProcessCrmService::_organizationId
0x2fe4  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x2fe9  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x2fee  brfalse.s loc_3023
0x2ff0  call     class [Microsoft.Crm.Authentication]Microsoft.Crm.Authentication.UserIdentityContext [Microsoft.Crm.Authentication]Microsoft.Crm.Authentication.UserIdentityContext::get_Current()
0x2ff5  callvirt instance class [mscorlib]System.Security.Claims.ClaimsPrincipal [Microsoft.Crm.Authentication]Microsoft.Crm.Authentication.UserIdentityContext::get_Principal()
0x2ffa  callvirt instance class [mscorlib]System.Security.Principal.IIdentity [mscorlib]System.Security.Claims.ClaimsPrincipal::get_Identity()
0x2fff  callvirt instance bool [mscorlib]System.Security.Principal.IIdentity::get_IsAuthenticated()
0x3004  ldstr    aCallerMustBeAu// "Caller must be authenticated before usi"...
0x3009  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x300e  ldarg.0
0x300f  call     class [Microsoft.Crm.Authentication]Microsoft.Crm.Authentication.UserIdentityContext [Microsoft.Crm.Authentication]Microsoft.Crm.Authentication.UserIdentityContext::get_Current()
0x3014  callvirt instance class [mscorlib]System.Security.Claims.ClaimsPrincipal [Microsoft.Crm.Authentication]Microsoft.Crm.Authentication.UserIdentityContext::get_Principal()
0x3019  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]IdentityExtensions::GetOrganizationId(class [mscorlib]System.Security.Claims.ClaimsPrincipal)
0x301e  stfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Sdk.InProcessCrmService::_organizationId
0x3023  call     class [mscorlib]System.Security.Principal.WindowsIdentity [mscorlib]System.Security.Principal.WindowsIdentity::GetCurrent()
0x3028  stloc.1
0x3029  ldarg.2
0x302a  ldloc.1
0x302b  ldarg.0
0x302c  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Sdk.InProcessCrmService::_organizationId
0x3031  call     class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.UserAuth [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SecurityLibrary::GetCallerAndBusinessGuidsFromThread(class [mscorlib]System.Security.Principal.WindowsIdentity, valuetype [mscorlib]System.Guid)
0x3036  stind.ref
0x3037  leave.s  loc_3064
0x3039  ldloc.1
0x303a  brfalse.s loc_3042
0x303c  ldloc.1
0x303d  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x3042  endfinally
0x3043  ldarg.0
0x3044  ldstr    aOrgid// "OrgId"
0x3049  call     object [Microsoft.Crm.Core]Microsoft.Crm.RegistryCache::GetValue(string)
0x304e  callvirt instance string [mscorlib]System.Object::ToString()
0x3053  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x3058  stfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Sdk.InProcessCrmService::_organizationId
0x305d  ldarg.2
0x305e  call     class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.UserAuth [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SecurityLibrary::GetCallerAndBusinessGuids()
0x3063  stind.ref
0x3064  ldarg.3
0x3065  ldarg.2
0x3066  ldind.ref
0x3067  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.UserAuth::get_UserId()
0x306c  stobj    [mscorlib]System.Guid
0x3071  ldarg.0
0x3072  ldfld    class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmAuthenticationToken Microsoft.Crm.Sdk.InProcessCrmService::_authenticationToken
0x3077  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmAuthenticationToken::get_CallerId()
0x307c  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x3081  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x3086  brfalse.s loc_3099
0x3088  ldarg.3
0x3089  ldarg.0
0x308a  ldfld    class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmAuthenticationToken Microsoft.Crm.Sdk.InProcessCrmService::_authenticationToken
0x308f  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmAuthenticationToken::get_CallerId()
0x3094  stobj    [mscorlib]System.Guid
0x3099  ldnull
0x309a  stloc.0
0x309b  call     class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.OpenExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.OpenExecutionContext::get_Instance()
0x30a0  ldarg.0
0x30a1  ldfld    class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CorrelationToken Microsoft.Crm.Sdk.InProcessCrmService::_correlationToken
0x30a6  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CorrelationToken::get_TransactionContextId()
0x30ab  ldloca.s 0
0x30ad  callvirt instance bool [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.OpenExecutionContext::TryGetContext(valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext&)
0x30b2  pop
0x30b3  ldarg.2
0x30b4  ldind.ref
0x30b5  ldarg.3
0x30b6  ldobj    [mscorlib]System.Guid
0x30bb  ldc.i4.0
0x30bc  ldarg.1
0x30bd  ldloc.0
0x30be  call     void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SoapContext::InitializeSoapAndSerializationContexts(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.UserAuth, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.Core.Security.Identity.UserType, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SoapContext, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x30c3  ldarg.s  4
0x30c5  call     class [Microsoft.Crm.Core]Microsoft.Crm.Performance.WebServicePerformanceCountersFactory [Microsoft.Crm.Core]Microsoft.Crm.Performance.WebServicePerformanceCountersFactory::get_Instance()
0x30ca  ldc.i4.3
0x30cb  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Performance.IWebServicePerformanceCounters [Microsoft.Crm.Core]Microsoft.Crm.Performance.WebServicePerformanceCountersFactory::GetCounters(valuetype [Microsoft.Crm.Core]Microsoft.Crm.Performance.WebServiceType)
0x30d0  stind.ref
0x30d1  ret
```
