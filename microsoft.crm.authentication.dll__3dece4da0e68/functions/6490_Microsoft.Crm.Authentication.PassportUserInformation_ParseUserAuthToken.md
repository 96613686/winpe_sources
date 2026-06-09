# Microsoft.Crm.Authentication.PassportUserInformation::ParseUserAuthToken

- ea: `0x6490`
- end: `0x650b`
- name: `Microsoft.Crm.Authentication.PassportUserInformation::ParseUserAuthToken`
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
- `0x6490`

## string_xrefs

- `0x6491`: `userToken`

## pseudocode

```c

```

## disassembly

```asm
0x6490  ldarg.0
0x6491  ldstr    aUsertoken// "userToken"
0x6496  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string, string)
0x649b  ldarg.0
0x649c  call     string Microsoft.Crm.Authentication.UserAuthenticationInformation::GetTokenPrefix(string userAuth)
0x64a1  ldstr    aP_0// "P"
0x64a6  call     bool [mscorlib]System.String::op_Equality(string, string)
0x64ab  brfalse.s loc_6509
0x64ad  ldarg.0
0x64ae  call     string Microsoft.Crm.Authentication.UserAuthenticationInformation::RemoveTokenPrefix(string userAuth)
0x64b3  newobj   instance void Microsoft.Crm.Authentication.UserAuthenticationTokenInformation::.ctor()
0x64b8  stloc.0
0x64b9  ldloc.0
0x64ba  ldc.i4.3
0x64bb  callvirt instance void Microsoft.Crm.Authentication.UserAuthenticationTokenInformation::set_AuthenticationMode(valuetype Microsoft.Crm.Authentication.AuthenticationMode value)
0x64c0  ldc.i4.1
0x64c1  newarr   [mscorlib]System.Char
0x64c6  dup
0x64c7  ldc.i4.0
0x64c8  ldc.i4.s 0x40
0x64ca  stelem.i2
0x64cb  ldc.i4.1
0x64cc  callvirt instance string[] [mscorlib]System.String::Split(char[], valuetype [mscorlib]System.StringSplitOptions)
0x64d1  stloc.1
0x64d2  ldloc.1
0x64d3  brfalse.s loc_6507
0x64d5  ldloc.1
0x64d6  ldlen
0x64d7  conv.i4
0x64d8  ldc.i4.2
0x64d9  bne.un.s loc_64EF
0x64db  ldloc.0
0x64dc  ldloc.1
0x64dd  ldc.i4.0
0x64de  ldelem.ref
0x64df  callvirt instance void Microsoft.Crm.Authentication.UserAuthenticationTokenInformation::set_Identifier(string value)
0x64e4  ldloc.0
0x64e5  ldloc.1
0x64e6  ldc.i4.1
0x64e7  ldelem.ref
0x64e8  callvirt instance void Microsoft.Crm.Authentication.UserAuthenticationTokenInformation::set_Domain(string value)
0x64ed  br.s     loc_6507
0x64ef  ldloc.1
0x64f0  ldlen
0x64f1  conv.i4
0x64f2  ldc.i4.1
0x64f3  bne.un.s loc_6500
0x64f5  ldloc.0
0x64f6  ldloc.1
0x64f7  ldc.i4.0
0x64f8  ldelem.ref
0x64f9  callvirt instance void Microsoft.Crm.Authentication.UserAuthenticationTokenInformation::set_Identifier(string value)
0x64fe  br.s     loc_6507
0x6500  ldloc.0
0x6501  ldarg.0
0x6502  callvirt instance void Microsoft.Crm.Authentication.UserAuthenticationTokenInformation::set_Identifier(string value)
0x6507  ldloc.0
0x6508  ret
0x6509  ldnull
0x650a  ret
```
