# Microsoft.Crm.Authentication.Claims.SecurityTokenRequirementHandler::CreateSpnPrefixAudience

- ea: `0xddd0`
- end: `0xde29`
- name: `Microsoft.Crm.Authentication.Claims.SecurityTokenRequirementHandler::CreateSpnPrefixAudience`
- size: `89`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x8910`
- `0x8b40`
- `0x150b0`

## callees

- `0xddd0`

## pseudocode

```c

```

## disassembly

```asm
0xddd0  ldarg.0
0xddd1  ldstr    aAudience// "audience"
0xddd6  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string, string)
0xdddb  ldnull
0xdddc  stloc.0
0xdddd  ldarg.0
0xddde  ldc.i4.1
0xdddf  ldloca.s 0
0xdde1  call     bool [System]System.Uri::TryCreate(string, valuetype [System]System.UriKind, class [System]System.Uri&)
0xdde6  brfalse.s loc_DDEA
0xdde8  ldloc.0
0xdde9  ret
0xddea  ldarg.0
0xddeb  ldstr    aSpn// "spn:"
0xddf0  ldc.i4.5
0xddf1  callvirt instance bool [mscorlib]System.String::StartsWith(string, valuetype [mscorlib]System.StringComparison)
0xddf6  brtrue.s loc_DE09
0xddf8  ldstr    aSpn// "spn:"
0xddfd  ldarg.0
0xddfe  call     string [mscorlib]System.String::Concat(string, string)
0xde03  newobj   instance void [System]System.Uri::.ctor(string)
0xde08  ret
0xde09  ldnull
0xde0a  stloc.1
0xde0b  ldstr    aSpn// "spn:"
0xde10  ldarg.0
0xde11  call     string [mscorlib]System.String::Concat(string, string)
0xde16  ldc.i4.0
0xde17  ldloca.s 1
0xde19  call     bool [System]System.Uri::TryCreate(string, valuetype [System]System.UriKind, class [System]System.Uri&)
0xde1e  brfalse.s loc_DE22
0xde20  ldloc.1
0xde21  ret
0xde22  ldarg.0
0xde23  newobj   instance void [System]System.Uri::.ctor(string)
0xde28  ret
```
