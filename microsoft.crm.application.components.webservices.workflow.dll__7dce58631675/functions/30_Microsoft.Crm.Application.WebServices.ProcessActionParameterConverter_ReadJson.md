# Microsoft.Crm.Application.WebServices.ProcessActionParameterConverter::ReadJson

- ea: `0x30`
- end: `0x1a4`
- name: `Microsoft.Crm.Application.WebServices.ProcessActionParameterConverter::ReadJson`
- size: `372`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x30`

## pseudocode

```c

```

## disassembly

```asm
0x30  ldarg.s  4
0x32  ldarg.1
0x33  callvirt T0x2B000001
0x38  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::.ctor()
0x3d  stloc.0
0x3e  callvirt instance valuetype [Newtonsoft.Json]Newtonsoft.Json.Linq.JEnumerable`1<class [Newtonsoft.Json]Newtonsoft.Json.Linq.JToken> [Newtonsoft.Json]Newtonsoft.Json.Linq.JToken::Children()
0x43  stloc.2
0x44  ldloca.s 2
0x46  call     instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> valuetype [Newtonsoft.Json]Newtonsoft.Json.Linq.JEnumerable`1<class [Newtonsoft.Json]Newtonsoft.Json.Linq.JToken>::GetEnumerator()
0x4b  stloc.1
0x4c  br       loc_18B
0x51  ldloc.1
0x52  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Newtonsoft.Json]Newtonsoft.Json.Linq.JToken>::get_Current()
0x57  stloc.3
0x58  ldloc.3
0x59  call     T0x2B000002
0x5e  callvirt instance valuetype [Newtonsoft.Json]Newtonsoft.Json.Linq.JTokenType [Newtonsoft.Json]Newtonsoft.Json.Linq.JToken::get_Type()
0x63  stloc.s  4
0x65  ldloc.s  4
0x67  ldc.i4.6
0x68  sub
0x69  switch   loc_8F, loc_10B, loc_E5, loc_BA, loc_15B, loc_16F, loc_133
0x8a  br       loc_16F
0x8f  ldloc.0
0x90  ldloc.3
0x91  call     T0x2B000002
0x96  callvirt instance string [Newtonsoft.Json]Newtonsoft.Json.Linq.JToken::get_Path()
0x9b  ldloc.3
0x9c  call     T0x2B000003
0xa1  call     T0x2B000002
0xa6  call     int32 [mscorlib]System.Convert::ToInt32(object)
0xab  box      [mscorlib]System.Int32
0xb0  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0xb5  br       loc_18B
0xba  ldloc.0
0xbb  ldloc.3
0xbc  call     T0x2B000002
0xc1  callvirt instance string [Newtonsoft.Json]Newtonsoft.Json.Linq.JToken::get_Path()
0xc6  ldloc.3
0xc7  call     T0x2B000003
0xcc  call     T0x2B000002
0xd1  call     bool [mscorlib]System.Convert::ToBoolean(object)
0xd6  box      [mscorlib]System.Boolean
0xdb  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0xe0  br       loc_18B
0xe5  ldloc.0
0xe6  ldloc.3
0xe7  call     T0x2B000002
0xec  callvirt instance string [Newtonsoft.Json]Newtonsoft.Json.Linq.JToken::get_Path()
0xf1  ldloc.3
0xf2  call     T0x2B000003
0xf7  call     T0x2B000002
0xfc  call     string [mscorlib]System.Convert::ToString(object)
0x101  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x106  br       loc_18B
0x10b  ldloc.0
0x10c  ldloc.3
0x10d  call     T0x2B000002
0x112  callvirt instance string [Newtonsoft.Json]Newtonsoft.Json.Linq.JToken::get_Path()
0x117  ldloc.3
0x118  call     T0x2B000003
0x11d  call     T0x2B000002
0x122  call     float64 [mscorlib]System.Convert::ToDouble(object)
0x127  box      [mscorlib]System.Double
0x12c  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x131  br.s     loc_18B
0x133  ldloc.0
0x134  ldloc.3
0x135  call     T0x2B000002
0x13a  callvirt instance string [Newtonsoft.Json]Newtonsoft.Json.Linq.JToken::get_Path()
0x13f  ldloc.3
0x140  call     T0x2B000003
0x145  call     T0x2B000002
0x14a  call     valuetype [mscorlib]System.DateTime [mscorlib]System.Convert::ToDateTime(object)
0x14f  box      [mscorlib]System.DateTime
0x154  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x159  br.s     loc_18B
0x15b  ldloc.0
0x15c  ldloc.3
0x15d  call     T0x2B000002
0x162  callvirt instance string [Newtonsoft.Json]Newtonsoft.Json.Linq.JToken::get_Path()
0x167  ldnull
0x168  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x16d  br.s     loc_18B
0x16f  ldloc.0
0x170  ldloc.3
0x171  call     T0x2B000002
0x176  callvirt instance string [Newtonsoft.Json]Newtonsoft.Json.Linq.JToken::get_Path()
0x17b  ldloc.3
0x17c  call     T0x2B000003
0x181  call     T0x2B000002
0x186  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x18b  ldloc.1
0x18c  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x191  brtrue   loc_51
0x196  leave.s  loc_1A2
0x198  ldloc.1
0x199  brfalse.s loc_1A1
0x19b  ldloc.1
0x19c  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1a1  endfinally
0x1a2  ldloc.0
0x1a3  ret
```
