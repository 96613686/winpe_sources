# Microsoft.Crm.Extensibility.Throttling.SdkThrottlingMessageInspector::GetUserIdentity

- ea: `0xf070`
- end: `0xf18c`
- name: `Microsoft.Crm.Extensibility.Throttling.SdkThrottlingMessageInspector::GetUserIdentity`
- size: `284`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0xef80`

## callees

- `0xf070`

## string_xrefs

- `0xf16e`: `Throttling message inspector failed during GetUserIdentity: {0}`

## pseudocode

```c

```

## disassembly

```asm
0xf070  ldnull
0xf071  stloc.0
0xf072  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0xf077  brfalse.s loc_F0C8
0xf079  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0xf07e  callvirt instance class [mscorlib]System.Security.Principal.IPrincipal [System.Web]System.Web.HttpContext::get_User()
0xf083  brfalse.s loc_F0C8
0xf085  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0xf08a  callvirt instance class [mscorlib]System.Security.Principal.IPrincipal [System.Web]System.Web.HttpContext::get_User()
0xf08f  isinst   [mscorlib]System.Security.Claims.ClaimsPrincipal
0xf094  stloc.1
0xf095  ldloc.1
0xf096  brfalse.s loc_F0C8
0xf098  ldloc.1
0xf099  callvirt instance class [mscorlib]System.Security.Principal.IIdentity [mscorlib]System.Security.Claims.ClaimsPrincipal::get_Identity()
0xf09e  callvirt instance bool [mscorlib]System.Security.Principal.IIdentity::get_IsAuthenticated()
0xf0a3  brfalse.s loc_F0C8
0xf0a5  ldloc.1
0xf0a6  callvirt instance class [mscorlib]System.Security.Principal.IIdentity [mscorlib]System.Security.Claims.ClaimsPrincipal::get_Identity()
0xf0ab  isinst   [Microsoft.Crm.Core]Microsoft.Crm.Core.Security.Identity.UserIdentity
0xf0b0  stloc.2
0xf0b1  ldloc.2
0xf0b2  brfalse.s loc_F0C8
0xf0b4  ldloc.2
0xf0b5  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.Core.Security.Identity.CrmIdentity::get_Id()
0xf0ba  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0xf0bf  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0xf0c4  brfalse.s loc_F0C8
0xf0c6  ldloc.2
0xf0c7  stloc.0
0xf0c8  ldloc.0
0xf0c9  brtrue   loc_F161
0xf0ce  ldnull
0xf0cf  stloc.3
0xf0d0  call     class [System.ServiceModel]System.ServiceModel.ServiceSecurityContext [System.ServiceModel]System.ServiceModel.ServiceSecurityContext::get_Current()
0xf0d5  dup
0xf0d6  brtrue.s loc_F0DC
0xf0d8  pop
0xf0d9  ldnull
0xf0da  br.s     loc_F0E1
0xf0dc  call     instance class [System.IdentityModel]System.IdentityModel.Policy.AuthorizationContext [System.ServiceModel]System.ServiceModel.ServiceSecurityContext::get_AuthorizationContext()
0xf0e1  stloc.s  4
0xf0e3  ldloc.s  4
0xf0e5  brfalse.s loc_F11A
0xf0e7  ldloc.s  4
0xf0e9  callvirt instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, object> [System.IdentityModel]System.IdentityModel.Policy.AuthorizationContext::get_Properties()
0xf0ee  brfalse.s loc_F11A
0xf0f0  ldloc.s  4
0xf0f2  callvirt instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, object> [System.IdentityModel]System.IdentityModel.Policy.AuthorizationContext::get_Properties()
0xf0f7  ldstr    aClaimsprincipa// "ClaimsPrincipal"
0xf0fc  callvirt instance bool class [mscorlib]System.Collections.Generic.IDictionary`2<string, object>::ContainsKey(var<u1>)
0xf101  brfalse.s loc_F11A
0xf103  ldloc.s  4
0xf105  callvirt instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, object> [System.IdentityModel]System.IdentityModel.Policy.AuthorizationContext::get_Properties()
0xf10a  ldstr    aClaimsprincipa// "ClaimsPrincipal"
0xf10f  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IDictionary`2<string, object>::get_Item(void)
0xf114  isinst   [mscorlib]System.Security.Claims.ClaimsPrincipal
0xf119  stloc.3
0xf11a  ldloc.3
0xf11b  brtrue.s loc_F120
0xf11d  ldnull
0xf11e  br.s     loc_F126
0xf120  ldloc.3
0xf121  callvirt instance class [mscorlib]System.Security.Principal.IIdentity [mscorlib]System.Security.Claims.ClaimsPrincipal::get_Identity()
0xf126  brfalse.s loc_F161
0xf128  ldloc.3
0xf129  callvirt instance class [mscorlib]System.Security.Principal.IIdentity [mscorlib]System.Security.Claims.ClaimsPrincipal::get_Identity()
0xf12e  isinst   [Microsoft.Crm.Core]Microsoft.Crm.Core.Security.Identity.UserIdentity
0xf133  brfalse.s loc_F143
0xf135  ldloc.3
0xf136  callvirt instance class [mscorlib]System.Security.Principal.IIdentity [mscorlib]System.Security.Claims.ClaimsPrincipal::get_Identity()
0xf13b  castclass [Microsoft.Crm.Core]Microsoft.Crm.Core.Security.Identity.UserIdentity
0xf140  stloc.0
0xf141  br.s     loc_F161
0xf143  ldloc.3
0xf144  callvirt instance class [mscorlib]System.Security.Principal.IIdentity [mscorlib]System.Security.Claims.ClaimsPrincipal::get_Identity()
0xf149  isinst   [mscorlib]System.Security.Claims.ClaimsIdentity
0xf14e  brfalse.s loc_F161
0xf150  ldloc.3
0xf151  callvirt instance class [mscorlib]System.Security.Principal.IIdentity [mscorlib]System.Security.Claims.ClaimsPrincipal::get_Identity()
0xf156  castclass [mscorlib]System.Security.Claims.ClaimsIdentity
0xf15b  call     class [Microsoft.Crm.Core]Microsoft.Crm.Core.Security.Identity.UserIdentity [Microsoft.Crm.Core]Microsoft.Crm.Core.Security.Identity.UserIdentity::Get(class [mscorlib]System.Security.Claims.ClaimsIdentity)
0xf160  stloc.0
0xf161  leave.s  loc_F18A
0xf163  stloc.s  5
0xf165  ldloc.s  5
0xf167  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0xf16c  ldc.i4.s 0x14
0xf16e  ldstr    aThrottlingMess_0// "Throttling message inspector failed dur"...
0xf173  ldc.i4.1
0xf174  newarr   [mscorlib]System.Object
0xf179  dup
0xf17a  ldc.i4.0
0xf17b  ldloc.s  5
0xf17d  callvirt instance string [mscorlib]System.Object::ToString()
0xf182  stelem.ref
0xf183  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0xf188  leave.s  loc_F18A
0xf18a  ldloc.0
0xf18b  ret
```
