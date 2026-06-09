# Microsoft.Crm.Authentication.CrmPostAuthenticationHelper::get_TokenExpirationReminderTime

- ea: `0x2660`
- end: `0x26c0`
- name: `Microsoft.Crm.Authentication.CrmPostAuthenticationHelper::get_TokenExpirationReminderTime`
- size: `96`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x2530`
- `0x2a90`

## callees

- `0x1320`
- `0x2660`
- `0x2c10`

## pseudocode

```c

```

## disassembly

```asm
0x2660  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x2665  stloc.0
0x2666  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x266b  brfalse.s loc_26B9
0x266d  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x2672  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.HttpContext::get_Request()
0x2677  brfalse.s loc_26B9
0x2679  ldloca.s 1
0x267b  initobj  valuetype [mscorlib]System.Nullable`1<int32>
0x2681  call     bool [Microsoft.Crm.Core]Microsoft.Crm.CrmAuthenticationContext::get_ClaimsEnabled()
0x2686  brfalse.s loc_269D
0x2688  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x268d  callvirt instance class [mscorlib]System.Security.Principal.IPrincipal [System.Web]System.Web.HttpContext::get_User()
0x2692  isinst   [mscorlib]System.Security.Claims.ClaimsPrincipal
0x2697  call     valuetype [mscorlib]System.Nullable`1<int32> [Microsoft.Crm.Core]IdentityExtensions::GetCustomSessionTokenReminderInMins(class [mscorlib]System.Security.Claims.ClaimsPrincipal)
0x269c  stloc.1
0x269d  ldloca.s 1
0x269f  call     instance bool valuetype [mscorlib]System.Nullable`1<int32>::get_HasValue()
0x26a4  brfalse.s loc_26AE
0x26a6  ldloca.s 1
0x26a8  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<int32>::get_Value()
0x26ad  ret
0x26ae  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x26b3  call     valuetype [mscorlib]System.Guid Microsoft.Crm.Authentication.CrmPostAuthenticationHelper::GetRequestedOrganizationId(class [System.Web]System.Web.HttpContext context)
0x26b8  stloc.0
0x26b9  ldloc.0
0x26ba  call     int32 Microsoft.Crm.Authentication.CrmAuthorizationUtility::GetExpirationReminderTimeForOrganization(valuetype [mscorlib]System.Guid orgId)
0x26bf  ret
```
