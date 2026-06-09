# Microsoft.Crm.Authentication.Claims.ResourceAccessErrorResponseHandler::BuildStandardAuthRequiredResponse

- ea: `0xfa80`
- end: `0xfb4d`
- name: `Microsoft.Crm.Authentication.Claims.ResourceAccessErrorResponseHandler::BuildStandardAuthRequiredResponse`
- size: `205`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0xf780`

## callees

- `0xfa80`

## string_xrefs

- `0xfa98`: `common`
- `0xfa85`: `/common`
- `0xfb3c`: `authorization_uri`

## pseudocode

```c

```

## disassembly

```asm
0xfa80  ldc.i4.2
0xfa81  ldarg.3
0xfa82  bne.un.s loc_FAF6
0xfa84  ldarg.1
0xfa85  ldstr    aCommon_0// "/common"
0xfa8a  ldc.i4.5
0xfa8b  callvirt instance int32 [mscorlib]System.String::IndexOf(string, valuetype [mscorlib]System.StringComparison)
0xfa90  stloc.0
0xfa91  ldc.i4.m1
0xfa92  ldloc.0
0xfa93  beq      loc_FB29
0xfa98  ldstr    aCommon// "common"
0xfa9d  stloc.1
0xfa9e  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0xfaa3  ldarg.2
0xfaa4  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0xfaa9  brfalse.s loc_FACE
0xfaab  newobj   instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.CrmLive.Services.OrganizationLifecycleService::.ctor()
0xfab0  ldarg.2
0xfab1  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.CrmLive.Services.OrganizationLifecycleService::RetrieveOrganizationContextId(valuetype [mscorlib]System.Guid)
0xfab6  stloc.2
0xfab7  ldloca.s 2
0xfab9  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::get_HasValue()
0xfabe  brfalse.s loc_FACE
0xfac0  ldloca.s 2
0xfac2  constrained. valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>
0xfac8  callvirt instance string [mscorlib]System.Object::ToString()
0xfacd  stloc.1
0xface  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xfad3  ldstr    a01Oauth2Author// "{0}/{1}/oauth2/authorize"
0xfad8  ldc.i4.2
0xfad9  newarr   [mscorlib]System.Object
0xfade  dup
0xfadf  ldc.i4.0
0xfae0  ldarg.1
0xfae1  ldc.i4.0
0xfae2  ldloc.0
0xfae3  callvirt instance string [mscorlib]System.String::Substring(int32, int32)
0xfae8  stelem.ref
0xfae9  dup
0xfaea  ldc.i4.1
0xfaeb  ldloc.1
0xfaec  stelem.ref
0xfaed  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xfaf2  starg.s  1
0xfaf4  br.s     loc_FB29
0xfaf6  ldarg.1
0xfaf7  ldstr    aLs// "/ls/"
0xfafc  ldc.i4.5
0xfafd  callvirt instance int32 [mscorlib]System.String::IndexOf(string, valuetype [mscorlib]System.StringComparison)
0xfb02  stloc.3
0xfb03  ldc.i4.m1
0xfb04  ldloc.3
0xfb05  beq.s    loc_FB29
0xfb07  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xfb0c  ldstr    a0Oauth2Authori// "{0}/oauth2/authorize"
0xfb11  ldc.i4.1
0xfb12  newarr   [mscorlib]System.Object
0xfb17  dup
0xfb18  ldc.i4.0
0xfb19  ldarg.1
0xfb1a  ldc.i4.0
0xfb1b  ldloc.3
0xfb1c  callvirt instance string [mscorlib]System.String::Substring(int32, int32)
0xfb21  stelem.ref
0xfb22  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xfb27  starg.s  1
0xfb29  ldarg.0
0xfb2a  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xfb2f  ldstr    a01_1// "{0}={1}"
0xfb34  ldc.i4.2
0xfb35  newarr   [mscorlib]System.Object
0xfb3a  dup
0xfb3b  ldc.i4.0
0xfb3c  ldstr    aAuthorizationU// "authorization_uri"
0xfb41  stelem.ref
0xfb42  dup
0xfb43  ldc.i4.1
0xfb44  ldarg.1
0xfb45  stelem.ref
0xfb46  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(class [mscorlib]System.IFormatProvider, string, object[])
0xfb4b  pop
0xfb4c  ret
```
