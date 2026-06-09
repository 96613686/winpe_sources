# Microsoft.Crm.Extensibility.ODataV4.Edm.EdmExtensions::GetCustomQueryOptionForQueryView

- ea: `0x28e40`
- end: `0x28f0b`
- name: `Microsoft.Crm.Extensibility.ODataV4.Edm.EdmExtensions::GetCustomQueryOptionForQueryView`
- size: `203`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x11f10`
- `0x12610`

## callees

- `0x247b0`
- `0x28e40`
- `0x28f10`

## string_xrefs

- `0x28eef`: `fetchXml`
- `0x28ef5`: `fetchXml`

## pseudocode

```c

```

## disassembly

```asm
0x28e40  ldarg.0
0x28e41  call     class [mscorlib]System.Collections.Generic.IEnumerable`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>> [System.Web.Http]System.Net.Http.HttpRequestMessageExtensions::GetQueryNameValuePairs(class [System.Net.Http]System.Net.Http.HttpRequestMessage)
0x28e46  ldsfld   class [mscorlib]System.Func`2<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>, string> <>c::<>9__8_0
0x28e4b  dup
0x28e4c  brtrue.s loc_28E65
0x28e4e  pop
0x28e4f  ldsfld   class <>c <>c::<>9
0x28e54  ldftn    instance string <>c::<GetCustomQueryOptionForQueryView>b__8_0(valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string> p)
0x28e5a  newobj   instance void class [mscorlib]System.Func`2<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>, string>::.ctor(object, native int)
0x28e5f  dup
0x28e60  stsfld   class [mscorlib]System.Func`2<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>, string> <>c::<>9__8_0
0x28e65  ldsfld   class [mscorlib]System.Func`2<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>, string> <>c::<>9__8_1
0x28e6a  dup
0x28e6b  brtrue.s loc_28E84
0x28e6d  pop
0x28e6e  ldsfld   class <>c <>c::<>9
0x28e73  ldftn    instance string <>c::<GetCustomQueryOptionForQueryView>b__8_1(valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string> p)
0x28e79  newobj   instance void class [mscorlib]System.Func`2<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>, string>::.ctor(object, native int)
0x28e7e  dup
0x28e7f  stsfld   class [mscorlib]System.Func`2<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>, string> <>c::<>9__8_1
0x28e84  call     T0x2B0000C2
0x28e89  stloc.0
0x28e8a  ldarg.0
0x28e8b  ldarg.1
0x28e8c  call     class Microsoft.Crm.Extensibility.OData.CustomQueryOptions Microsoft.Crm.Extensibility.ODataV4.Edm.EdmExtensions::GetCustomQueryOption(class [System.Net.Http]System.Net.Http.HttpRequestMessage request, class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel edmModel)
0x28e91  stloc.1
0x28e92  ldloc.0
0x28e93  call     T0x2B0000F0
0x28e98  brfalse.s loc_28F09
0x28e9a  ldloc.0
0x28e9b  ldstr    aSavedquery_1// "savedQuery"
0x28ea0  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::ContainsKey(var<u1>)
0x28ea5  brfalse.s loc_28EC4
0x28ea7  ldloc.1
0x28ea8  ldstr    aSavedquery_0// "SavedQuery"
0x28ead  ldloc.0
0x28eae  ldstr    aSavedquery_1// "savedQuery"
0x28eb3  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::get_Item(void)
0x28eb8  newobj   instance void valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>::.ctor(var<u1>, !!T0)
0x28ebd  callvirt instance void Microsoft.Crm.Extensibility.OData.CustomQueryOptions::set_CustomQueryParameter(valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string> value)
0x28ec2  br.s     loc_28F09
0x28ec4  ldloc.0
0x28ec5  ldstr    aUserquery_1// "userQuery"
0x28eca  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::ContainsKey(var<u1>)
0x28ecf  brfalse.s loc_28EEE
0x28ed1  ldloc.1
0x28ed2  ldstr    aUserquery_0// "UserQuery"
0x28ed7  ldloc.0
0x28ed8  ldstr    aUserquery_1// "userQuery"
0x28edd  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::get_Item(void)
0x28ee2  newobj   instance void valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>::.ctor(var<u1>, !!T0)
0x28ee7  callvirt instance void Microsoft.Crm.Extensibility.OData.CustomQueryOptions::set_CustomQueryParameter(valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string> value)
0x28eec  br.s     loc_28F09
0x28eee  ldloc.1
0x28eef  ldstr    aFetchxml// "fetchXml"
0x28ef4  ldloc.0
0x28ef5  ldstr    aFetchxml// "fetchXml"
0x28efa  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::get_Item(void)
0x28eff  newobj   instance void valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>::.ctor(var<u1>, !!T0)
0x28f04  callvirt instance void Microsoft.Crm.Extensibility.OData.CustomQueryOptions::set_CustomQueryParameter(valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string> value)
0x28f09  ldloc.1
0x28f0a  ret
```
