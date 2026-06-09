# Microsoft.Crm.Authentication.ActiveDirectoryUserInformation::ParseUserAuthToken

- ea: `0x5e50`
- end: `0x5e8a`
- name: `Microsoft.Crm.Authentication.ActiveDirectoryUserInformation::ParseUserAuthToken`
- size: `58`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x59d0`
- `0x59f0`
- `0x5a20`
- `0x5b50`
- `0x5b80`
- `0x5e50`

## string_xrefs

- `0x5e51`: `userToken`

## pseudocode

```c

```

## disassembly

```asm
0x5e50  ldarg.0
0x5e51  ldstr    aUsertoken// "userToken"
0x5e56  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string, string)
0x5e5b  ldarg.0
0x5e5c  call     string Microsoft.Crm.Authentication.UserAuthenticationInformation::GetTokenPrefix(string userAuth)
0x5e61  ldstr    aW// "W"
0x5e66  call     bool [mscorlib]System.String::op_Equality(string, string)
0x5e6b  brfalse.s loc_5E88
0x5e6d  ldarg.0
0x5e6e  call     string Microsoft.Crm.Authentication.UserAuthenticationInformation::RemoveTokenPrefix(string userAuth)
0x5e73  stloc.0
0x5e74  newobj   instance void Microsoft.Crm.Authentication.UserAuthenticationTokenInformation::.ctor()
0x5e79  dup
0x5e7a  ldc.i4.1
0x5e7b  callvirt instance void Microsoft.Crm.Authentication.UserAuthenticationTokenInformation::set_AuthenticationMode(valuetype Microsoft.Crm.Authentication.AuthenticationMode value)
0x5e80  dup
0x5e81  ldloc.0
0x5e82  callvirt instance void Microsoft.Crm.Authentication.UserAuthenticationTokenInformation::set_Identifier(string value)
0x5e87  ret
0x5e88  ldnull
0x5e89  ret
```
