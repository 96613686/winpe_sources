# Microsoft.Crm.Sandbox.SandboxCodeUnit::CopyCollection_0

- ea: `0x32b0`
- end: `0x3311`
- name: `Microsoft.Crm.Sandbox.SandboxCodeUnit::CopyCollection_0`
- size: `97`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x32b0`

## pseudocode

```c

```

## disassembly

```asm
0x32b0  ldarg.0
0x32b1  brfalse.s loc_3310
0x32b3  ldarg.1
0x32b4  brfalse.s loc_3310
0x32b6  ldarg.0
0x32b7  ldarg.1
0x32b8  bne.un.s loc_32BB
0x32ba  ret
0x32bb  ldarg.0
0x32bc  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<var<u1>, !!T0>> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<mvar<u1>, !!T0>::GetEnumerator()
0x32c1  stloc.0
0x32c2  br.s     loc_32FC
0x32c4  ldloc.0
0x32c5  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<mvar<u1>, !!T0>>::get_Current()
0x32ca  stloc.1
0x32cb  ldloca.s 1
0x32cd  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<mvar<u1>, !!T0>::get_Key()
0x32d2  stloc.2
0x32d3  ldloca.s 2
0x32d5  ldarg.2
0x32d6  box      mvar<u1>
0x32db  constrained. mvar<u1>
0x32e1  callvirt instance bool [mscorlib]System.Object::Equals(object)
0x32e6  brtrue.s loc_32FC
0x32e8  ldarg.1
0x32e9  ldloca.s 1
0x32eb  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<mvar<u1>, !!T0>::get_Key()
0x32f0  ldloca.s 1
0x32f2  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<mvar<u1>, !!T0>::get_Value()
0x32f7  callvirt instance void class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<mvar<u1>, !!T0>::set_Item(var<u1>, !!T0)
0x32fc  ldloc.0
0x32fd  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x3302  brtrue.s loc_32C4
0x3304  leave.s  loc_3310
0x3306  ldloc.0
0x3307  brfalse.s loc_330F
0x3309  ldloc.0
0x330a  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x330f  endfinally
0x3310  ret
```
