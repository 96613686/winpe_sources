# Microsoft.Crm.Sandbox.LocalConfigStoreSerializer::ConvertDictionaryByteToObject

- ea: `0x9660`
- end: `0x96af`
- name: `Microsoft.Crm.Sandbox.LocalConfigStoreSerializer::ConvertDictionaryByteToObject`
- size: `79`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x94d0`
- `0x9540`

## callees

- `0x9600`
- `0x9660`

## pseudocode

```c

```

## disassembly

```asm
0x9660  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::.ctor()
0x9665  stloc.0
0x9666  ldarg.1
0x9667  brfalse.s loc_96AD
0x9669  ldarg.1
0x966a  callvirt instance valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<string, unsigned int8[]>::GetEnumerator()
0x966f  stloc.1
0x9670  br.s     loc_9694
0x9672  ldloca.s 1
0x9674  call     instance valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<var<u1>, !!T0> valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<string, unsigned int8[]>::get_Current()
0x9679  stloc.2
0x967a  ldloc.0
0x967b  ldloca.s 2
0x967d  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, unsigned int8[]>::get_Key()
0x9682  ldarg.0
0x9683  ldloca.s 2
0x9685  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, unsigned int8[]>::get_Value()
0x968a  call     instance object Microsoft.Crm.Sandbox.LocalConfigStoreSerializer::ByteArrayToObject(unsigned int8[] arrBytes)
0x968f  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x9694  ldloca.s 1
0x9696  call     instance bool valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<string, unsigned int8[]>::MoveNext()
0x969b  brtrue.s loc_9672
0x969d  leave.s  loc_96AD
0x969f  ldloca.s 1
0x96a1  constrained. valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<string, unsigned int8[]>
0x96a7  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x96ac  endfinally
0x96ad  ldloc.0
0x96ae  ret
```
