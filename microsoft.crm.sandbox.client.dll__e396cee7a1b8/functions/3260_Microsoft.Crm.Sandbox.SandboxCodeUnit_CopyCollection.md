# Microsoft.Crm.Sandbox.SandboxCodeUnit::CopyCollection

- ea: `0x3260`
- end: `0x32a4`
- name: `Microsoft.Crm.Sandbox.SandboxCodeUnit::CopyCollection`
- size: `68`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x3260`

## pseudocode

```c

```

## disassembly

```asm
0x3260  ldarg.0
0x3261  brfalse.s loc_32A3
0x3263  ldarg.1
0x3264  brfalse.s loc_32A3
0x3266  ldarg.0
0x3267  ldarg.1
0x3268  bne.un.s loc_326B
0x326a  ret
0x326b  ldarg.0
0x326c  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<var<u1>, !!T0>> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<mvar<u1>, !!T0>::GetEnumerator()
0x3271  stloc.0
0x3272  br.s     loc_328F
0x3274  ldloc.0
0x3275  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<mvar<u1>, !!T0>>::get_Current()
0x327a  stloc.1
0x327b  ldarg.1
0x327c  ldloca.s 1
0x327e  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<mvar<u1>, !!T0>::get_Key()
0x3283  ldloca.s 1
0x3285  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<mvar<u1>, !!T0>::get_Value()
0x328a  callvirt instance void class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<mvar<u1>, !!T0>::set_Item(var<u1>, !!T0)
0x328f  ldloc.0
0x3290  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x3295  brtrue.s loc_3274
0x3297  leave.s  loc_32A3
0x3299  ldloc.0
0x329a  brfalse.s loc_32A2
0x329c  ldloc.0
0x329d  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x32a2  endfinally
0x32a3  ret
```
