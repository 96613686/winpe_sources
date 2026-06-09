# Microsoft.Crm.Sandbox.LocalConfigStoreSerializer::ConvertDictionaryObjectToByte

- ea: `0x96b0`
- end: `0x96ff`
- name: `Microsoft.Crm.Sandbox.LocalConfigStoreSerializer::ConvertDictionaryObjectToByte`
- size: `79`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x9560`

## callees

- `0x95b0`
- `0x96b0`

## pseudocode

```c

```

## disassembly

```asm
0x96b0  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, unsigned int8[]>::.ctor()
0x96b5  stloc.0
0x96b6  ldarg.1
0x96b7  brfalse.s loc_96FD
0x96b9  ldarg.1
0x96ba  callvirt instance valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::GetEnumerator()
0x96bf  stloc.1
0x96c0  br.s     loc_96E4
0x96c2  ldloca.s 1
0x96c4  call     instance valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<var<u1>, !!T0> valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<string, object>::get_Current()
0x96c9  stloc.2
0x96ca  ldloc.0
0x96cb  ldloca.s 2
0x96cd  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, object>::get_Key()
0x96d2  ldarg.0
0x96d3  ldloca.s 2
0x96d5  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, object>::get_Value()
0x96da  call     instance unsigned int8[] Microsoft.Crm.Sandbox.LocalConfigStoreSerializer::ObjectToByteArray(object obj)
0x96df  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, unsigned int8[]>::Add(var<u1>, !!T0)
0x96e4  ldloca.s 1
0x96e6  call     instance bool valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<string, object>::MoveNext()
0x96eb  brtrue.s loc_96C2
0x96ed  leave.s  loc_96FD
0x96ef  ldloca.s 1
0x96f1  constrained. valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<string, object>
0x96f7  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x96fc  endfinally
0x96fd  ldloc.0
0x96fe  ret
```
