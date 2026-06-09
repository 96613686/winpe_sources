# Microsoft.Crm.Authentication.Claims.ExchangeJwtSecurityTokenHandler::ValidateIssuedLatteOrganization

- ea: `0x85b0`
- end: `0x86be`
- name: `Microsoft.Crm.Authentication.Claims.ExchangeJwtSecurityTokenHandler::ValidateIssuedLatteOrganization`
- size: `270`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0xef20`

## callees

- `0x85b0`
- `0x8820`

## string_xrefs

- `0x85cf`: `The token passed was NOT an Exchange Security Token!`
- `0x8620`: `The appctxsender claim was not contained within the requested token!`
- `0x8661`: `The tenant id was not contained within the requested token!`
- `0x869e`: `The organization id was not contained within the requested token!`

## pseudocode

```c

```

## disassembly

```asm
0x85b0  ldarg.1
0x85b1  ldstr    aTenantid// "tenantId"
0x85b6  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfGuidEmpty(valuetype [mscorlib]System.Guid, string)
0x85bb  ldarg.2
0x85bc  ldstr    aOrganizationid// "organizationId"
0x85c1  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfGuidEmpty(valuetype [mscorlib]System.Guid, string)
0x85c6  ldarg.0
0x85c7  isinst   Microsoft.Crm.Authentication.Claims.ExchangeSecurityToken
0x85cc  dup
0x85cd  brtrue.s loc_85DA
0x85cf  ldstr    aTheTokenPassed// "The token passed was NOT an Exchange Se"...
0x85d4  newobj   instance void [System.IdentityModel]System.IdentityModel.Tokens.SecurityTokenValidationException::.ctor(string)
0x85d9  throw
0x85da  callvirt instance int32 Microsoft.Crm.Authentication.Claims.ExchangeSecurityToken::get_Version()
0x85df  ldc.i4.1
0x85e0  bne.un   loc_86BD
0x85e5  ldarg.0
0x85e6  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [mscorlib]System.Security.Claims.Claim> [System.IdentityModel.Tokens.Jwt]System.IdentityModel.Tokens.JwtSecurityToken::get_Claims()
0x85eb  ldsfld   class [mscorlib]System.Func`2<class [mscorlib]System.Security.Claims.Claim, bool> <>c::<>9__7_0
0x85f0  dup
0x85f1  brtrue.s loc_860A
0x85f3  pop
0x85f4  ldsfld   class <>c <>c::<>9
0x85f9  ldftn    instance bool <>c::<ValidateIssuedLatteOrganization>b__7_0(class [mscorlib]System.Security.Claims.Claim c)
0x85ff  newobj   instance void class [mscorlib]System.Func`2<class [mscorlib]System.Security.Claims.Claim, bool>::.ctor(object, native int)
0x8604  dup
0x8605  stsfld   class [mscorlib]System.Func`2<class [mscorlib]System.Security.Claims.Claim, bool> <>c::<>9__7_0
0x860a  call     T0x2B00000D
0x860f  stloc.0
0x8610  ldloc.0
0x8611  brfalse.s loc_8620
0x8613  ldloc.0
0x8614  callvirt instance string [mscorlib]System.Security.Claims.Claim::get_Value()
0x8619  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x861e  brfalse.s loc_862B
0x8620  ldstr    aTheAppctxsende// "The appctxsender claim was not containe"...
0x8625  newobj   instance void [System.IdentityModel]System.IdentityModel.Tokens.SecurityTokenValidationException::.ctor(string)
0x862a  throw
0x862b  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x8630  stloc.1
0x8631  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x8636  stloc.2
0x8637  ldloc.0
0x8638  callvirt instance string [mscorlib]System.Security.Claims.Claim::get_Value()
0x863d  ldc.i4.1
0x863e  newarr   [mscorlib]System.Char
0x8643  dup
0x8644  ldc.i4.0
0x8645  ldc.i4.s 0x40
0x8647  stelem.i2
0x8648  ldc.i4.1
0x8649  callvirt instance string[] [mscorlib]System.String::Split(char[], valuetype [mscorlib]System.StringSplitOptions)
0x864e  stloc.3
0x864f  ldloc.3
0x8650  ldlen
0x8651  conv.i4
0x8652  ldc.i4.1
0x8653  ble.s    loc_866C
0x8655  ldloc.3
0x8656  ldc.i4.1
0x8657  ldelem.ref
0x8658  ldloca.s 2
0x865a  call     bool [mscorlib]System.Guid::TryParse(string, valuetype [mscorlib]System.Guid&)
0x865f  brtrue.s loc_866C
0x8661  ldstr    aTheTenantIdWas// "The tenant id was not contained within "...
0x8666  newobj   instance void [System.IdentityModel]System.IdentityModel.Tokens.SecurityTokenValidationException::.ctor(string)
0x866b  throw
0x866c  ldarg.1
0x866d  ldloc.2
0x866e  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x8673  brfalse.s loc_8680
0x8675  ldstr    aTheTenantIdDoe// "The tenant id does not match the reques"...
0x867a  newobj   instance void [System.IdentityModel]System.IdentityModel.Tokens.SecurityTokenValidationException::.ctor(string)
0x867f  throw
0x8680  ldloc.0
0x8681  callvirt instance string [mscorlib]System.Security.Claims.Claim::get_Value()
0x8686  call     class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpUtility::ParseQueryString(string)
0x868b  ldstr    aOrgid_0// "orgid"
0x8690  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x8695  ldloca.s 1
0x8697  call     bool [mscorlib]System.Guid::TryParse(string, valuetype [mscorlib]System.Guid&)
0x869c  brtrue.s loc_86A9
0x869e  ldstr    aTheOrganizatio// "The organization id was not contained w"...
0x86a3  newobj   instance void [System.IdentityModel]System.IdentityModel.Tokens.SecurityTokenValidationException::.ctor(string)
0x86a8  throw
0x86a9  ldarg.2
0x86aa  ldloc.1
0x86ab  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x86b0  brfalse.s loc_86BD
0x86b2  ldstr    aTheOrganizatio_0// "The organization id does not match the "...
0x86b7  newobj   instance void [System.IdentityModel]System.IdentityModel.Tokens.SecurityTokenValidationException::.ctor(string)
0x86bc  throw
0x86bd  ret
```
