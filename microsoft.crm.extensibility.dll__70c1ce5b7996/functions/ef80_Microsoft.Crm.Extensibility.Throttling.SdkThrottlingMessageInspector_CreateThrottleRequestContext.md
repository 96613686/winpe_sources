# Microsoft.Crm.Extensibility.Throttling.SdkThrottlingMessageInspector::CreateThrottleRequestContext

- ea: `0xef80`
- end: `0xf06f`
- name: `Microsoft.Crm.Extensibility.Throttling.SdkThrottlingMessageInspector::CreateThrottleRequestContext`
- size: `239`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0xeeb0`

## callees

- `0xef80`
- `0xf070`
- `0xf3b0`
- `0x314e0`

## string_xrefs

- `0xeff9`: `Ignore Error - Throttling message inspector: failed to get userId: {0}, orgId: {1}, Path: {2}`

## pseudocode

```c

```

## disassembly

```asm
0xef80  ldnull
0xef81  stloc.0
0xef82  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0xef87  stloc.1
0xef88  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0xef8d  stloc.2
0xef8e  ldarg.0
0xef8f  call     instance class [Microsoft.Crm.Core]Microsoft.Crm.Core.Security.Identity.UserIdentity Microsoft.Crm.Extensibility.Throttling.SdkThrottlingMessageInspector::GetUserIdentity()
0xef94  stloc.3
0xef95  ldloc.3
0xef96  brfalse.s loc_EFA8
0xef98  ldloc.3
0xef99  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.Core.Security.Identity.CrmIdentity::get_Id()
0xef9e  stloc.1
0xef9f  ldloc.3
0xefa0  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.Core.Security.Identity.CrmIdentity::get_OrganizationId()
0xefa5  stloc.2
0xefa6  br.s     loc_EFD7
0xefa8  call     class [Microsoft.Crm.Authentication]Microsoft.Crm.Authentication.UserIdentityContext [Microsoft.Crm.Authentication]Microsoft.Crm.Authentication.UserIdentityContext::get_Current()
0xefad  stloc.s  4
0xefaf  ldloc.s  4
0xefb1  callvirt instance class [mscorlib]System.Security.Claims.ClaimsPrincipal [Microsoft.Crm.Authentication]Microsoft.Crm.Authentication.UserIdentityContext::get_Principal()
0xefb6  call     bool [Microsoft.Crm.Core]IdentityExtensions::GetIsUserAuthenticated(class [mscorlib]System.Security.Claims.ClaimsPrincipal)
0xefbb  brfalse.s loc_EFD7
0xefbd  ldloc.s  4
0xefbf  callvirt instance class [mscorlib]System.Security.Claims.ClaimsPrincipal [Microsoft.Crm.Authentication]Microsoft.Crm.Authentication.UserIdentityContext::get_Principal()
0xefc4  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]IdentityExtensions::GetUserId(class [mscorlib]System.Security.Claims.ClaimsPrincipal)
0xefc9  stloc.1
0xefca  ldloc.s  4
0xefcc  callvirt instance class [mscorlib]System.Security.Claims.ClaimsPrincipal [Microsoft.Crm.Authentication]Microsoft.Crm.Authentication.UserIdentityContext::get_Principal()
0xefd1  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]IdentityExtensions::GetOrganizationId(class [mscorlib]System.Security.Claims.ClaimsPrincipal)
0xefd6  stloc.2
0xefd7  ldloc.1
0xefd8  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0xefdd  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0xefe2  brtrue.s loc_EFF1
0xefe4  ldloc.2
0xefe5  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0xefea  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0xefef  brfalse.s loc_F04F
0xeff1  ldnull
0xeff2  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0xeff7  ldc.i4.s 0x14
0xeff9  ldstr    aIgnoreErrorThr// "Ignore Error - Throttling message inspe"...
0xeffe  ldc.i4.3
0xefff  newarr   [mscorlib]System.Object
0xf004  dup
0xf005  ldc.i4.0
0xf006  ldloc.1
0xf007  box      [mscorlib]System.Guid
0xf00c  stelem.ref
0xf00d  dup
0xf00e  ldc.i4.1
0xf00f  ldloc.2
0xf010  box      [mscorlib]System.Guid
0xf015  stelem.ref
0xf016  dup
0xf017  ldc.i4.2
0xf018  ldarg.1
0xf019  ldind.ref
0xf01a  dup
0xf01b  brtrue.s loc_F021
0xf01d  pop
0xf01e  ldnull
0xf01f  br.s     loc_F03E
0xf021  callvirt instance class [System.ServiceModel]System.ServiceModel.Channels.MessageProperties [System.ServiceModel]System.ServiceModel.Channels.Message::get_Properties()
0xf026  dup
0xf027  brtrue.s loc_F02D
0xf029  pop
0xf02a  ldnull
0xf02b  br.s     loc_F03E
0xf02d  call     instance class [System]System.Uri [System.ServiceModel]System.ServiceModel.Channels.MessageProperties::get_Via()
0xf032  dup
0xf033  brtrue.s loc_F039
0xf035  pop
0xf036  ldnull
0xf037  br.s     loc_F03E
0xf039  call     instance string [System]System.Uri::get_AbsolutePath()
0xf03e  dup
0xf03f  brtrue.s loc_F047
0xf041  pop
0xf042  ldsfld   string [mscorlib]System.String::Empty
0xf047  stelem.ref
0xf048  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0xf04d  br.s     loc_F06D
0xf04f  ldloc.1
0xf050  ldloc.2
0xf051  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.UserAndOrganizationContext::.ctor(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0xf056  stloc.s  5
0xf058  ldloc.2
0xf059  ldloc.1
0xf05a  ldarg.0
0xf05b  ldloc.s  5
0xf05d  call     instance bool Microsoft.Crm.Extensibility.Throttling.SdkThrottlingMessageInspector::IsFcbEnabled(class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext context)
0xf062  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0xf067  newobj   instance void ThrottleRequestContext::.ctor(valuetype [mscorlib]System.Guid orgId, valuetype [mscorlib]System.Guid userId, bool fcbOn, valuetype [mscorlib]System.DateTime startTime)
0xf06c  stloc.0
0xf06d  ldloc.0
0xf06e  ret
```
