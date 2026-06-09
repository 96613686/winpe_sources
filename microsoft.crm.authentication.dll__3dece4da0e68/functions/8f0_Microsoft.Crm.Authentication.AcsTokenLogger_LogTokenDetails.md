# Microsoft.Crm.Authentication.AcsTokenLogger::LogTokenDetails

- ea: `0x8f0`
- end: `0x93b`
- name: `Microsoft.Crm.Authentication.AcsTokenLogger::LogTokenDetails`
- size: `75`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x31b0`

## string_xrefs

- `0x905`: `ACSAUTH: user authenticated using ACS token. Issuer: {0}, Audience: {1} and OrganizationId: {2}.`

## pseudocode

```c

```

## disassembly

```asm
0x8f0  ldarg.0
0x8f1  ldstr    aClaimsprincipa// "claimsPrincipal"
0x8f6  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x8fb  ldarg.0
0x8fc  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]IdentityExtensions::GetOrganizationId(class [mscorlib]System.Security.Claims.ClaimsPrincipal)
0x901  stloc.0
0x902  ldloc.0
0x903  ldc.i4.s 0x14
0x905  ldstr    aAcsauthUserAut// "ACSAUTH: user authenticated using ACS t"...
0x90a  ldc.i4.3
0x90b  newarr   [mscorlib]System.Object
0x910  dup
0x911  ldc.i4.0
0x912  ldarg.0
0x913  call     string [Microsoft.Crm.Core]IdentityExtensions::GetIssuer(class [mscorlib]System.Security.Claims.ClaimsPrincipal)
0x918  stelem.ref
0x919  dup
0x91a  ldc.i4.1
0x91b  ldstr    asc_1636A// ";"
0x920  ldarg.0
0x921  call     string[] [Microsoft.Crm.Core]IdentityExtensions::GetAudiences(class [mscorlib]System.Security.Claims.ClaimsPrincipal)
0x926  call     string [mscorlib]System.String::Join(string, string[])
0x92b  stelem.ref
0x92c  dup
0x92d  ldc.i4.2
0x92e  ldloc.0
0x92f  box      [mscorlib]System.Guid
0x934  stelem.ref
0x935  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceWarning(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x93a  ret
```
