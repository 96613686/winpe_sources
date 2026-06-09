# Microsoft.Crm.Authentication.FederatedUserInformation::ParseUserAuthToken

- ea: `0x5f70`
- end: `0x5feb`
- name: `Microsoft.Crm.Authentication.FederatedUserInformation::ParseUserAuthToken`
- size: `123`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x7f0`

## callees

- `0x59d0`
- `0x59f0`
- `0x5a10`
- `0x5a20`
- `0x5b50`
- `0x5b80`
- `0x5f70`

## string_xrefs

- `0x5f71`: `userToken`

## pseudocode

```c

```

## disassembly

```asm
0x5f70  ldarg.0
0x5f71  ldstr    aUsertoken// "userToken"
0x5f76  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string, string)
0x5f7b  ldarg.0
0x5f7c  call     string Microsoft.Crm.Authentication.UserAuthenticationInformation::GetTokenPrefix(string userAuth)
0x5f81  ldstr    aC_0// "C"
0x5f86  call     bool [mscorlib]System.String::op_Equality(string, string)
0x5f8b  brfalse.s loc_5FE9
0x5f8d  ldarg.0
0x5f8e  call     string Microsoft.Crm.Authentication.UserAuthenticationInformation::RemoveTokenPrefix(string userAuth)
0x5f93  newobj   instance void Microsoft.Crm.Authentication.UserAuthenticationTokenInformation::.ctor()
0x5f98  stloc.0
0x5f99  ldloc.0
0x5f9a  ldc.i4.2
0x5f9b  callvirt instance void Microsoft.Crm.Authentication.UserAuthenticationTokenInformation::set_AuthenticationMode(valuetype Microsoft.Crm.Authentication.AuthenticationMode value)
0x5fa0  ldc.i4.1
0x5fa1  newarr   [mscorlib]System.Char
0x5fa6  dup
0x5fa7  ldc.i4.0
0x5fa8  ldc.i4.s 0x40
0x5faa  stelem.i2
0x5fab  ldc.i4.1
0x5fac  callvirt instance string[] [mscorlib]System.String::Split(char[], valuetype [mscorlib]System.StringSplitOptions)
0x5fb1  stloc.1
0x5fb2  ldloc.1
0x5fb3  brfalse.s loc_5FE7
0x5fb5  ldloc.1
0x5fb6  ldlen
0x5fb7  conv.i4
0x5fb8  ldc.i4.2
0x5fb9  bne.un.s loc_5FCF
0x5fbb  ldloc.0
0x5fbc  ldloc.1
0x5fbd  ldc.i4.0
0x5fbe  ldelem.ref
0x5fbf  callvirt instance void Microsoft.Crm.Authentication.UserAuthenticationTokenInformation::set_Identifier(string value)
0x5fc4  ldloc.0
0x5fc5  ldloc.1
0x5fc6  ldc.i4.1
0x5fc7  ldelem.ref
0x5fc8  callvirt instance void Microsoft.Crm.Authentication.UserAuthenticationTokenInformation::set_Domain(string value)
0x5fcd  br.s     loc_5FE7
0x5fcf  ldloc.1
0x5fd0  ldlen
0x5fd1  conv.i4
0x5fd2  ldc.i4.1
0x5fd3  bne.un.s loc_5FE0
0x5fd5  ldloc.0
0x5fd6  ldloc.1
0x5fd7  ldc.i4.0
0x5fd8  ldelem.ref
0x5fd9  callvirt instance void Microsoft.Crm.Authentication.UserAuthenticationTokenInformation::set_Identifier(string value)
0x5fde  br.s     loc_5FE7
0x5fe0  ldloc.0
0x5fe1  ldarg.0
0x5fe2  callvirt instance void Microsoft.Crm.Authentication.UserAuthenticationTokenInformation::set_Identifier(string value)
0x5fe7  ldloc.0
0x5fe8  ret
0x5fe9  ldnull
0x5fea  ret
```
