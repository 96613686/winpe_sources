# Microsoft.Crm.Sandbox.AssemblyAuthenticationContextProvider::AcquireToken

- ea: `0xba0`
- end: `0xc25`
- name: `Microsoft.Crm.Sandbox.AssemblyAuthenticationContextProvider::AcquireToken`
- size: `133`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0xba0`

## string_xrefs

- `0xbf8`: `AdalException while acquiring token: {0}`
- `0xc0c`: `AdalException while acquiring token: {0}`

## pseudocode

```c

```

## disassembly

```asm
0xba0  ldarg.1
0xba1  ldstr    aAuthority// "authority"
0xba6  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0xbab  ldarg.2
0xbac  ldstr    aResource// "resource"
0xbb1  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0xbb6  ldarg.1
0xbb7  newobj   instance void [Microsoft.IdentityModel.Clients.ActiveDirectory]Microsoft.IdentityModel.Clients.ActiveDirectory.AuthenticationContext::.ctor(string)
0xbbc  stloc.0
0xbbd  ldarg.3
0xbbe  brtrue.s loc_BDA
0xbc0  ldloc.0
0xbc1  ldarg.2
0xbc2  ldarg.0
0xbc3  ldfld    class [mscorlib]System.Lazy`1<class [Microsoft.IdentityModel.Clients.ActiveDirectory]Microsoft.IdentityModel.Clients.ActiveDirectory.ClientCredential> Microsoft.Crm.Sandbox.AssemblyAuthenticationContextProvider::_clientCredentials
0xbc8  callvirt instance var<u1> class [mscorlib]System.Lazy`1<class [Microsoft.IdentityModel.Clients.ActiveDirectory]Microsoft.IdentityModel.Clients.ActiveDirectory.ClientCredential>::get_Value()
0xbcd  callvirt instance class [Microsoft.IdentityModel.Clients.ActiveDirectory]Microsoft.IdentityModel.Clients.ActiveDirectory.AuthenticationResult [Microsoft.IdentityModel.Clients.ActiveDirectory]Microsoft.IdentityModel.Clients.ActiveDirectory.AuthenticationContext::AcquireToken(string, class [Microsoft.IdentityModel.Clients.ActiveDirectory]Microsoft.IdentityModel.Clients.ActiveDirectory.ClientCredential)
0xbd2  callvirt instance string [Microsoft.IdentityModel.Clients.ActiveDirectory]Microsoft.IdentityModel.Clients.ActiveDirectory.AuthenticationResult::get_AccessToken()
0xbd7  stloc.1
0xbd8  leave.s  loc_C23
0xbda  ldloc.0
0xbdb  ldarg.2
0xbdc  ldarg.0
0xbdd  ldfld    class [mscorlib]System.Lazy`1<class [Microsoft.IdentityModel.Clients.ActiveDirectory]Microsoft.IdentityModel.Clients.ActiveDirectory.ClientAssertionCertificate> Microsoft.Crm.Sandbox.AssemblyAuthenticationContextProvider::_clientAssertionCertificate
0xbe2  callvirt instance var<u1> class [mscorlib]System.Lazy`1<class [Microsoft.IdentityModel.Clients.ActiveDirectory]Microsoft.IdentityModel.Clients.ActiveDirectory.ClientAssertionCertificate>::get_Value()
0xbe7  callvirt instance class [Microsoft.IdentityModel.Clients.ActiveDirectory]Microsoft.IdentityModel.Clients.ActiveDirectory.AuthenticationResult [Microsoft.IdentityModel.Clients.ActiveDirectory]Microsoft.IdentityModel.Clients.ActiveDirectory.AuthenticationContext::AcquireToken(string, class [Microsoft.IdentityModel.Clients.ActiveDirectory]Microsoft.IdentityModel.Clients.ActiveDirectory.ClientAssertionCertificate)
0xbec  callvirt instance string [Microsoft.IdentityModel.Clients.ActiveDirectory]Microsoft.IdentityModel.Clients.ActiveDirectory.AuthenticationResult::get_AccessToken()
0xbf1  stloc.1
0xbf2  leave.s  loc_C23
0xbf4  stloc.2
0xbf5  ldloc.2
0xbf6  ldc.i4.s 0x1F
0xbf8  ldstr    aAdalexceptionW// "AdalException while acquiring token: {0"...
0xbfd  ldc.i4.1
0xbfe  newarr   [mscorlib]System.Object
0xc03  dup
0xc04  ldc.i4.0
0xc05  ldloc.2
0xc06  stelem.ref
0xc07  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceError(class [mscorlib]System.Exception, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0xc0c  ldstr    aAdalexceptionW// "AdalException while acquiring token: {0"...
0xc11  ldloc.2
0xc12  call     string [mscorlib]System.String::Format(string, object)
0xc17  ldloc.2
0xc18  ldc.i4   0x80091005
0xc1d  newobj   instance void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.CrmExceptions.CrmAdalException::.ctor(string, class [mscorlib]System.Exception, int32)
0xc22  throw
0xc23  ldloc.1
0xc24  ret
```
