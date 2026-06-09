# Microsoft.Crm.Extensibility.ODataV4.Edm.EdmExtensions::QueryParameterDictionary

- ea: `0x28fe0`
- end: `0x2902a`
- name: `Microsoft.Crm.Extensibility.ODataV4.Edm.EdmExtensions::QueryParameterDictionary`
- size: `74`
- prototype: ``
- caller_count: `21`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x11f10`
- `0x13da0`
- `0x13e80`
- `0x13ea0`
- `0x14880`
- `0x14e10`
- `0x199d0`
- `0x1d660`
- `0x1d750`
- `0x1de20`
- `0x1df90`
- `0x1e010`
- `0x1eb40`
- `0x1f4d0`
- `0x20360`
- `0x20450`
- `0x20610`
- `0x21100`
- `0x21200`
- `0x21270`
- `0x28c30`

## callees

- `0x28fe0`

## pseudocode

```c

```

## disassembly

```asm
0x28fe0  ldarg.0
0x28fe1  call     class [mscorlib]System.Collections.Generic.IEnumerable`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>> [System.Web.Http]System.Net.Http.HttpRequestMessageExtensions::GetQueryNameValuePairs(class [System.Net.Http]System.Net.Http.HttpRequestMessage)
0x28fe6  ldsfld   class [mscorlib]System.Func`2<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>, string> <>c::<>9__16_0
0x28feb  dup
0x28fec  brtrue.s loc_29005
0x28fee  pop
0x28fef  ldsfld   class <>c <>c::<>9
0x28ff4  ldftn    instance string <>c::<QueryParameterDictionary>b__16_0(valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string> p)
0x28ffa  newobj   instance void class [mscorlib]System.Func`2<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>, string>::.ctor(object, native int)
0x28fff  dup
0x29000  stsfld   class [mscorlib]System.Func`2<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>, string> <>c::<>9__16_0
0x29005  ldsfld   class [mscorlib]System.Func`2<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>, string> <>c::<>9__16_1
0x2900a  dup
0x2900b  brtrue.s loc_29024
0x2900d  pop
0x2900e  ldsfld   class <>c <>c::<>9
0x29013  ldftn    instance string <>c::<QueryParameterDictionary>b__16_1(valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string> p)
0x29019  newobj   instance void class [mscorlib]System.Func`2<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>, string>::.ctor(object, native int)
0x2901e  dup
0x2901f  stsfld   class [mscorlib]System.Func`2<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>, string> <>c::<>9__16_1
0x29024  call     T0x2B0000C2
0x29029  ret
```
