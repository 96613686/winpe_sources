# Microsoft.Crm.Extensibility.OData.CrmODataUtilities::IsFetchXmlQueryOption

- ea: `0x20b80`
- end: `0x20be1`
- name: `Microsoft.Crm.Extensibility.OData.CrmODataUtilities::IsFetchXmlQueryOption`
- size: `97`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x3c20`
- `0x33c70`

## callees

- `0x20b80`
- `0x28c90`

## string_xrefs

- `0x20bd4`: `fetchXml`

## pseudocode

```c

```

## disassembly

```asm
0x20b80  ldarg.0
0x20b81  call     class [mscorlib]System.Collections.Generic.IEnumerable`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>> [System.Web.Http]System.Net.Http.HttpRequestMessageExtensions::GetQueryNameValuePairs(class [System.Net.Http]System.Net.Http.HttpRequestMessage)
0x20b86  ldsfld   class [mscorlib]System.Func`2<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>, string> <>c::<>9__59_0
0x20b8b  dup
0x20b8c  brtrue.s loc_20BA5
0x20b8e  pop
0x20b8f  ldsfld   class <>c <>c::<>9
0x20b94  ldftn    instance string <>c::<IsFetchXmlQueryOption>b__59_0(valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string> p)
0x20b9a  newobj   instance void class [mscorlib]System.Func`2<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>, string>::.ctor(object, native int)
0x20b9f  dup
0x20ba0  stsfld   class [mscorlib]System.Func`2<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>, string> <>c::<>9__59_0
0x20ba5  ldsfld   class [mscorlib]System.Func`2<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>, string> <>c::<>9__59_1
0x20baa  dup
0x20bab  brtrue.s loc_20BC4
0x20bad  pop
0x20bae  ldsfld   class <>c <>c::<>9
0x20bb3  ldftn    instance string <>c::<IsFetchXmlQueryOption>b__59_1(valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string> p)
0x20bb9  newobj   instance void class [mscorlib]System.Func`2<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>, string>::.ctor(object, native int)
0x20bbe  dup
0x20bbf  stsfld   class [mscorlib]System.Func`2<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>, string> <>c::<>9__59_1
0x20bc4  call     T0x2B0000C2
0x20bc9  stloc.0
0x20bca  ldarg.0
0x20bcb  ldarg.1
0x20bcc  call     bool Microsoft.Crm.Extensibility.ODataV4.Edm.EdmExtensions::IsCustomQueryOptionPresent(class [System.Net.Http]System.Net.Http.HttpRequestMessage request, class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel edmModel)
0x20bd1  brfalse.s loc_20BDF
0x20bd3  ldloc.0
0x20bd4  ldstr    aFetchxml// "fetchXml"
0x20bd9  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::ContainsKey(var<u1>)
0x20bde  ret
0x20bdf  ldc.i4.0
0x20be0  ret
```
