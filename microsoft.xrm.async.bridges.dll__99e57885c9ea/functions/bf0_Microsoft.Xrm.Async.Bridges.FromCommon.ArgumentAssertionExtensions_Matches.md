# Microsoft.Xrm.Async.Bridges.FromCommon.ArgumentAssertionExtensions::Matches

- ea: `0xbf0`
- end: `0xc1c`
- name: `Microsoft.Xrm.Async.Bridges.FromCommon.ArgumentAssertionExtensions::Matches`
- size: `44`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0xbf0`

## pseudocode

```c

```

## disassembly

```asm
0xbf0  ldarg.1
0xbf1  ldarg.0
0xbf2  callvirt instance var<u1> class Microsoft.Xrm.Async.Bridges.FromCommon.ArgumentAssertion`1<string>::get_Value()
0xbf7  callvirt instance bool [System]System.Text.RegularExpressions.Regex::IsMatch(string)
0xbfc  brtrue.s loc_C1A
0xbfe  ldarg.0
0xbff  callvirt instance string class Microsoft.Xrm.Async.Bridges.FromCommon.ArgumentAssertion`1<string>::get_Name()
0xc04  ldarg.2
0xc05  dup
0xc06  brtrue.s loc_C14
0xc08  pop
0xc09  ldstr    aTheArgumentMus// "The argument must match the expression "...
0xc0e  ldarg.1
0xc0f  call     string [mscorlib]System.String::Format(string, object)
0xc14  newobj   instance void [mscorlib]System.ArgumentOutOfRangeException::.ctor(string, string)
0xc19  throw
0xc1a  ldarg.0
0xc1b  ret
```
