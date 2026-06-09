# Microsoft.Crm.ScaleGroupApi.Startup::Configuration

- ea: `0xc10`
- end: `0xccb`
- name: `Microsoft.Crm.ScaleGroupApi.Startup::Configuration`
- size: `187`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callees

- `0x3f0`
- `0x410`
- `0x470`
- `0x500`

## string_xrefs

- `0xc1b`: `AzureAdFederationUrl`

## pseudocode

```c

```

## disassembly

```asm
0xc10  call     class Microsoft.Crm.ScaleGroupApi.AzureApplicationInfo Microsoft.Crm.ScaleGroupApi.AzureApplicationInfo::RetrieveInfo()
0xc15  stloc.0
0xc16  call     class [Microsoft.Crm.Core]Microsoft.Crm.ISiteSettingsProvider [Microsoft.Crm.Core]Microsoft.Crm.SiteSettingsProvider::get_Instance()
0xc1b  ldstr    aAzureadfederat// "AzureAdFederationUrl"
0xc20  ldc.i4.0
0xc21  callvirt T0x2B000004
0xc26  stloc.1
0xc27  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xc2c  ldloc.1
0xc2d  ldc.i4.1
0xc2e  newarr   [mscorlib]System.Object
0xc33  dup
0xc34  ldc.i4.0
0xc35  ldloc.0
0xc36  callvirt instance string Microsoft.Crm.ScaleGroupApi.AzureApplicationInfo::get_ScaleGroupApiDomain()
0xc3b  stelem.ref
0xc3c  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xc41  stloc.2
0xc42  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0xc47  dup
0xc48  ldloc.0
0xc49  callvirt instance string Microsoft.Crm.ScaleGroupApi.AzureApplicationInfo::get_Issuer()
0xc4e  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0xc53  stloc.3
0xc54  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0xc59  dup
0xc5a  ldloc.0
0xc5b  callvirt instance string Microsoft.Crm.ScaleGroupApi.AzureApplicationInfo::get_ScaleGroupAppIdUri()
0xc60  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0xc65  stloc.s  4
0xc67  newobj   instance void [Microsoft.Owin.Security.ActiveDirectory]Microsoft.Owin.Security.ActiveDirectory.WindowsAzureActiveDirectoryBearerAuthenticationOptions::.ctor()
0xc6c  dup
0xc6d  ldloc.2
0xc6e  callvirt instance void [Microsoft.Owin.Security.ActiveDirectory]Microsoft.Owin.Security.ActiveDirectory.WindowsAzureActiveDirectoryBearerAuthenticationOptions::set_MetadataAddress(string)
0xc73  dup
0xc74  newobj   instance void [System.IdentityModel.Tokens.Jwt]System.IdentityModel.Tokens.TokenValidationParameters::.ctor()
0xc79  dup
0xc7a  ldc.i4.1
0xc7b  callvirt instance void [System.IdentityModel.Tokens.Jwt]System.IdentityModel.Tokens.TokenValidationParameters::set_ValidateAudience(bool)
0xc80  dup
0xc81  ldc.i4.1
0xc82  callvirt instance void [System.IdentityModel.Tokens.Jwt]System.IdentityModel.Tokens.TokenValidationParameters::set_ValidateIssuer(bool)
0xc87  dup
0xc88  ldloc.3
0xc89  callvirt instance void [System.IdentityModel.Tokens.Jwt]System.IdentityModel.Tokens.TokenValidationParameters::set_ValidIssuers(class [mscorlib]System.Collections.Generic.IEnumerable`1<string>)
0xc8e  dup
0xc8f  ldloc.s  4
0xc91  callvirt instance void [System.IdentityModel.Tokens.Jwt]System.IdentityModel.Tokens.TokenValidationParameters::set_ValidAudiences(class [mscorlib]System.Collections.Generic.IEnumerable`1<string>)
0xc96  dup
0xc97  ldnull
0xc98  ldftn    bool Microsoft.Crm.ScaleGroupApi.TokenAudienceValidator::AudienceValidator(class [mscorlib]System.Collections.Generic.IEnumerable`1<string> audiences, class [System.IdentityModel]System.IdentityModel.Tokens.SecurityToken token, class [System.IdentityModel.Tokens.Jwt]System.IdentityModel.Tokens.TokenValidationParameters parameters)
0xc9e  newobj   instance void [System.IdentityModel.Tokens.Jwt]System.IdentityModel.Tokens.AudienceValidator::.ctor(object, native int)
0xca3  callvirt instance void [System.IdentityModel.Tokens.Jwt]System.IdentityModel.Tokens.TokenValidationParameters::set_AudienceValidator(class [System.IdentityModel.Tokens.Jwt]System.IdentityModel.Tokens.AudienceValidator)
0xca8  dup
0xca9  ldnull
0xcaa  ldftn    string Microsoft.Crm.ScaleGroupApi.MultiTenantIssuerValidator::Validate(string issuer, class [System.IdentityModel]System.IdentityModel.Tokens.SecurityToken token, class [System.IdentityModel.Tokens.Jwt]System.IdentityModel.Tokens.TokenValidationParameters parameters)
0xcb0  newobj   instance void [System.IdentityModel.Tokens.Jwt]System.IdentityModel.Tokens.IssuerValidator::.ctor(object, native int)
0xcb5  callvirt instance void [System.IdentityModel.Tokens.Jwt]System.IdentityModel.Tokens.TokenValidationParameters::set_IssuerValidator(class [System.IdentityModel.Tokens.Jwt]System.IdentityModel.Tokens.IssuerValidator)
0xcba  callvirt instance void [Microsoft.Owin.Security.ActiveDirectory]Microsoft.Owin.Security.ActiveDirectory.WindowsAzureActiveDirectoryBearerAuthenticationOptions::set_TokenValidationParameters(class [System.IdentityModel.Tokens.Jwt]System.IdentityModel.Tokens.TokenValidationParameters)
0xcbf  stloc.s  5
0xcc1  ldarg.1
0xcc2  ldloc.s  5
0xcc4  call     class [Owin]Owin.IAppBuilder [Microsoft.Owin.Security.ActiveDirectory]Owin.WindowsAzureActiveDirectoryBearerAuthenticationExtensions::UseWindowsAzureActiveDirectoryBearerAuthentication(class [Owin]Owin.IAppBuilder, class [Microsoft.Owin.Security.ActiveDirectory]Microsoft.Owin.Security.ActiveDirectory.WindowsAzureActiveDirectoryBearerAuthenticationOptions)
0xcc9  pop
0xcca  ret
```
