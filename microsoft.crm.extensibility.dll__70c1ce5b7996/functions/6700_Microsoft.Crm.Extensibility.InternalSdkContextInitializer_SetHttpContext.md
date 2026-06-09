# Microsoft.Crm.Extensibility.InternalSdkContextInitializer::SetHttpContext

- ea: `0x6700`
- end: `0x67da`
- name: `Microsoft.Crm.Extensibility.InternalSdkContextInitializer::SetHttpContext`
- size: `218`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x66d0`

## callees

- `0x6700`

## string_xrefs

- `0x6784`: `CRM Service Identity`

## pseudocode

```c

```

## disassembly

```asm
0x6700  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x6705  brtrue.s loc_674E
0x6707  call     bool [System.Web]System.Web.Hosting.HostingEnvironment::get_IsHosted()
0x670c  brfalse.s loc_672A
0x670e  ldsfld   string [mscorlib]System.String::Empty
0x6713  ldsfld   string [mscorlib]System.String::Empty
0x6718  ldnull
0x6719  newobj   instance void [System.Web]System.Web.Hosting.SimpleWorkerRequest::.ctor(string, string, class [mscorlib]System.IO.TextWriter)
0x671e  newobj   instance void [System.Web]System.Web.HttpContext::.ctor(class [System.Web]System.Web.HttpWorkerRequest)
0x6723  call     void [System.Web]System.Web.HttpContext::set_Current(class [System.Web]System.Web.HttpContext)
0x6728  br.s     loc_674E
0x672a  ldsfld   string [mscorlib]System.String::Empty
0x672f  ldsfld   string [mscorlib]System.String::Empty
0x6734  ldsfld   string [mscorlib]System.String::Empty
0x6739  ldsfld   string [mscorlib]System.String::Empty
0x673e  ldnull
0x673f  newobj   instance void [System.Web]System.Web.Hosting.SimpleWorkerRequest::.ctor(string, string, string, string, class [mscorlib]System.IO.TextWriter)
0x6744  newobj   instance void [System.Web]System.Web.HttpContext::.ctor(class [System.Web]System.Web.HttpWorkerRequest)
0x6749  call     void [System.Web]System.Web.HttpContext::set_Current(class [System.Web]System.Web.HttpContext)
0x674e  call     bool [Microsoft.Crm.Authentication]Microsoft.Crm.Authentication.UserIdentityContext::get_IsAvailable()
0x6753  brfalse.s loc_6765
0x6755  ldarg.0
0x6756  call     class [Microsoft.Crm.Authentication]Microsoft.Crm.Authentication.UserIdentityContext [Microsoft.Crm.Authentication]Microsoft.Crm.Authentication.UserIdentityContext::get_Current()
0x675b  callvirt instance class [mscorlib]System.Security.Claims.ClaimsPrincipal [Microsoft.Crm.Authentication]Microsoft.Crm.Authentication.UserIdentityContext::get_Principal()
0x6760  stfld    class [mscorlib]System.Security.Principal.IPrincipal Microsoft.Crm.Extensibility.InternalSdkContextInitializer::_originalPrincipal
0x6765  ldarg.0
0x6766  ldfld    class [mscorlib]System.Security.Principal.IPrincipal Microsoft.Crm.Extensibility.InternalSdkContextInitializer::_originalPrincipal
0x676b  brtrue.s loc_677D
0x676d  ldarg.0
0x676e  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x6773  callvirt instance class [mscorlib]System.Security.Principal.IPrincipal [System.Web]System.Web.HttpContext::get_User()
0x6778  stfld    class [mscorlib]System.Security.Principal.IPrincipal Microsoft.Crm.Extensibility.InternalSdkContextInitializer::_originalPrincipal
0x677d  ldarg.1
0x677e  call     class [Microsoft.Crm.Core]Microsoft.Crm.Core.Security.Identity.UserIdentity [Microsoft.Crm.Core]Microsoft.Crm.Core.Security.Identity.UserIdentity::Get(class [mscorlib]System.Security.Claims.ClaimsIdentity)
0x6783  dup
0x6784  ldstr    aCrmServiceIden// "CRM Service Identity"
0x6789  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.Security.Identity.CrmIdentity::SetName(string)
0x678e  newobj   instance void [mscorlib]System.Security.Claims.ClaimsPrincipal::.ctor(class [mscorlib]System.Security.Principal.IIdentity)
0x6793  stloc.0
0x6794  ldloc.0
0x6795  ldarg.2
0x6796  call     void [Microsoft.Crm.Core]IdentityExtensions::SetOrganizationId(class [mscorlib]System.Security.Claims.ClaimsPrincipal, valuetype [mscorlib]System.Guid)
0x679b  ldarg.1
0x679c  ldarg.2
0x679d  call     class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.UserAuth [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SecurityLibrary::GetCallerAndBusinessGuidsFromThread(class [mscorlib]System.Security.Principal.WindowsIdentity, valuetype [mscorlib]System.Guid)
0x67a2  stloc.1
0x67a3  ldloc.1
0x67a4  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.UserAuth::get_UserId()
0x67a9  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x67ae  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x67b3  brfalse.s loc_67C1
0x67b5  ldloc.0
0x67b6  ldloc.1
0x67b7  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.UserAuth::get_UserId()
0x67bc  call     void [Microsoft.Crm.Core]IdentityExtensions::SetUserId(class [mscorlib]System.Security.Claims.ClaimsPrincipal, valuetype [mscorlib]System.Guid)
0x67c1  ldloc.0
0x67c2  ldarg.3
0x67c3  call     void [Microsoft.Crm.Core]IdentityExtensions::SetCallerId(class [mscorlib]System.Security.Claims.ClaimsPrincipal, valuetype [mscorlib]System.Guid)
0x67c8  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x67cd  ldloc.0
0x67ce  callvirt instance void [System.Web]System.Web.HttpContext::set_User(class [mscorlib]System.Security.Principal.IPrincipal)
0x67d3  ldloc.0
0x67d4  call     void [mscorlib]System.Threading.Thread::set_CurrentPrincipal(class [mscorlib]System.Security.Principal.IPrincipal)
0x67d9  ret
```
