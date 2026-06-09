# Microsoft.Xrm.Async.Bridges.WebApp.WebAppBuilder::ConfigureWebApp

- ea: `0x130`
- end: `0x17e`
- name: `Microsoft.Xrm.Async.Bridges.WebApp.WebAppBuilder::ConfigureWebApp`
- size: `78`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0xe0`

## callees

- `0x180`

## pseudocode

```c

```

## disassembly

```asm
0x130  ldarg.1
0x131  call     T0x2B000003
0x136  stloc.0
0x137  ldarg.2
0x138  newobj   instance void [Microsoft.Owin.Security.ActiveDirectory]Microsoft.Owin.Security.ActiveDirectory.WindowsAzureActiveDirectoryBearerAuthenticationOptions::.ctor()
0x13d  dup
0x13e  ldc.i4.0
0x13f  callvirt instance void [Microsoft.Owin.Security]Microsoft.Owin.Security.AuthenticationOptions::set_AuthenticationMode(valuetype [Microsoft.Owin.Security]Microsoft.Owin.Security.AuthenticationMode)
0x144  dup
0x145  ldloc.0
0x146  callvirt instance string [Microsoft.Xrm.Async.Bridges]Microsoft.Xrm.Async.Bridges.FromCommon.EndpointAuthConfig::get_Tenant()
0x14b  callvirt instance void [Microsoft.Owin.Security.ActiveDirectory]Microsoft.Owin.Security.ActiveDirectory.WindowsAzureActiveDirectoryBearerAuthenticationOptions::set_Tenant(string)
0x150  dup
0x151  newobj   instance void [System.IdentityModel.Tokens.Jwt]System.IdentityModel.Tokens.TokenValidationParameters::.ctor()
0x156  dup
0x157  ldloc.0
0x158  callvirt instance string [Microsoft.Xrm.Async.Bridges]Microsoft.Xrm.Async.Bridges.FromCommon.EndpointAuthConfig::get_Audience()
0x15d  callvirt instance void [System.IdentityModel.Tokens.Jwt]System.IdentityModel.Tokens.TokenValidationParameters::set_ValidAudience(string)
0x162  callvirt instance void [Microsoft.Owin.Security.ActiveDirectory]Microsoft.Owin.Security.ActiveDirectory.WindowsAzureActiveDirectoryBearerAuthenticationOptions::set_TokenValidationParameters(class [System.IdentityModel.Tokens.Jwt]System.IdentityModel.Tokens.TokenValidationParameters)
0x167  call     class [Owin]Owin.IAppBuilder [Microsoft.Owin.Security.ActiveDirectory]Owin.WindowsAzureActiveDirectoryBearerAuthenticationExtensions::UseWindowsAzureActiveDirectoryBearerAuthentication(class [Owin]Owin.IAppBuilder, class [Microsoft.Owin.Security.ActiveDirectory]Microsoft.Owin.Security.ActiveDirectory.WindowsAzureActiveDirectoryBearerAuthenticationOptions)
0x16c  pop
0x16d  ldarg.0
0x16e  ldarg.1
0x16f  callvirt instance class [System.Web.Http]System.Web.Http.HttpConfiguration Microsoft.Xrm.Async.Bridges.WebApp.WebAppBuilder::GetHttpConfiguration(class [Autofac]Autofac.ILifetimeScope scope)
0x174  stloc.1
0x175  ldarg.2
0x176  ldloc.1
0x177  call     class [Owin]Owin.IAppBuilder [System.Web.Http.Owin]Owin.WebApiAppBuilderExtensions::UseWebApi(class [Owin]Owin.IAppBuilder, class [System.Web.Http]System.Web.Http.HttpConfiguration)
0x17c  pop
0x17d  ret
```
