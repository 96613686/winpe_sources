# Microsoft.Xrm.Async.Bridges.FromCommon.ArgumentAssertionExtensions::Matches_0

- ea: `0xc20`
- end: `0xc55`
- name: `Microsoft.Xrm.Async.Bridges.FromCommon.ArgumentAssertionExtensions::Matches_0`
- size: `53`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0xc20`

## pseudocode

```c

```

## disassembly

```asm
0xc20  ldarg.2
0xc21  ldarg.1
0xc22  ldarg.0
0xc23  callvirt instance var<u1> class Microsoft.Xrm.Async.Bridges.FromCommon.ArgumentAssertion`1<string>::get_Value()
0xc28  callvirt instance class [System]System.Text.RegularExpressions.Match [System]System.Text.RegularExpressions.Regex::Match(string)
0xc2d  stind.ref
0xc2e  ldarg.2
0xc2f  ldind.ref
0xc30  callvirt instance bool [System]System.Text.RegularExpressions.Group::get_Success()
0xc35  brtrue.s loc_C53
0xc37  ldarg.0
0xc38  callvirt instance string class Microsoft.Xrm.Async.Bridges.FromCommon.ArgumentAssertion`1<string>::get_Name()
0xc3d  ldarg.3
0xc3e  dup
0xc3f  brtrue.s loc_C4D
0xc41  pop
0xc42  ldstr    aTheArgumentMus// "The argument must match the expression "...
0xc47  ldarg.1
0xc48  call     string [mscorlib]System.String::Format(string, object)
0xc4d  newobj   instance void [mscorlib]System.ArgumentOutOfRangeException::.ctor(string, string)
0xc52  throw
0xc53  ldarg.0
0xc54  ret
```
