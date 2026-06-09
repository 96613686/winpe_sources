# Microsoft.Crm.Authentication.AcsTokenLogger::IsAcsToken

- ea: `0x960`
- end: `0x97c`
- name: `Microsoft.Crm.Authentication.AcsTokenLogger::IsAcsToken`
- size: `28`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x8d0`

## callees

- `0x960`

## string_xrefs

- `0x96b`: `.accesscontrol.windows.net`

## pseudocode

```c

```

## disassembly

```asm
0x960  ldarg.0
0x961  call     string [Microsoft.Crm.Core]IdentityExtensions::GetIssuer(class [mscorlib]System.Security.Claims.ClaimsPrincipal)
0x966  stloc.0
0x967  ldloc.0
0x968  brfalse.s loc_97A
0x96a  ldloc.0
0x96b  ldstr    aAccesscontrolW// ".accesscontrol.windows.net"
0x970  ldc.i4.5
0x971  callvirt instance int32 [mscorlib]System.String::IndexOf(string, valuetype [mscorlib]System.StringComparison)
0x976  ldc.i4.m1
0x977  cgt
0x979  ret
0x97a  ldc.i4.0
0x97b  ret
```
