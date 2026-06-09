# Microsoft.Crm.Extensibility.ODataV4.Edm.EdmExtensions::IsCustomQueryOptionPresent

- ea: `0x28c90`
- end: `0x28d44`
- name: `Microsoft.Crm.Extensibility.ODataV4.Edm.EdmExtensions::IsCustomQueryOptionPresent`
- size: `180`
- prototype: ``
- caller_count: `4`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x11f10`
- `0x12610`
- `0x1e010`
- `0x20b80`

## callees

- `0x28c90`
- `0x28d50`
- `0x28dd0`
- `0x28fa0`

## string_xrefs

- `0x28d07`: `fetchXml`
- `0x28d25`: `No Other Query options supported when SavedQuery or UserQuery or FetchXml option is provided`
- `0x28d38`: `Count Segment is not supported when SavedQuery or UserQuery or FetchXml option is provided`

## pseudocode

```c

```

## disassembly

```asm
0x28c90  ldc.i4.0
0x28c91  stloc.0
0x28c92  ldarg.0
0x28c93  call     class [mscorlib]System.Collections.Generic.IEnumerable`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>> [System.Web.Http]System.Net.Http.HttpRequestMessageExtensions::GetQueryNameValuePairs(class [System.Net.Http]System.Net.Http.HttpRequestMessage)
0x28c98  call     T0x2B0000EF
0x28c9d  brfalse  loc_28D42
0x28ca2  ldarg.0
0x28ca3  call     class [mscorlib]System.Collections.Generic.IEnumerable`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>> [System.Web.Http]System.Net.Http.HttpRequestMessageExtensions::GetQueryNameValuePairs(class [System.Net.Http]System.Net.Http.HttpRequestMessage)
0x28ca8  ldsfld   class [mscorlib]System.Func`2<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>, string> <>c::<>9__5_0
0x28cad  dup
0x28cae  brtrue.s loc_28CC7
0x28cb0  pop
0x28cb1  ldsfld   class <>c <>c::<>9
0x28cb6  ldftn    instance string <>c::<IsCustomQueryOptionPresent>b__5_0(valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string> p)
0x28cbc  newobj   instance void class [mscorlib]System.Func`2<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>, string>::.ctor(object, native int)
0x28cc1  dup
0x28cc2  stsfld   class [mscorlib]System.Func`2<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>, string> <>c::<>9__5_0
0x28cc7  ldsfld   class [mscorlib]System.Func`2<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>, string> <>c::<>9__5_1
0x28ccc  dup
0x28ccd  brtrue.s loc_28CE6
0x28ccf  pop
0x28cd0  ldsfld   class <>c <>c::<>9
0x28cd5  ldftn    instance string <>c::<IsCustomQueryOptionPresent>b__5_1(valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string> p)
0x28cdb  newobj   instance void class [mscorlib]System.Func`2<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>, string>::.ctor(object, native int)
0x28ce0  dup
0x28ce1  stsfld   class [mscorlib]System.Func`2<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>, string> <>c::<>9__5_1
0x28ce6  call     T0x2B0000C2
0x28ceb  stloc.1
0x28cec  ldloc.1
0x28ced  ldstr    aSavedquery_1// "savedQuery"
0x28cf2  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::ContainsKey(var<u1>)
0x28cf7  brtrue.s loc_28D13
0x28cf9  ldloc.1
0x28cfa  ldstr    aUserquery_1// "userQuery"
0x28cff  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::ContainsKey(var<u1>)
0x28d04  brtrue.s loc_28D13
0x28d06  ldloc.1
0x28d07  ldstr    aFetchxml// "fetchXml"
0x28d0c  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::ContainsKey(var<u1>)
0x28d11  br.s     loc_28D14
0x28d13  ldc.i4.1
0x28d14  stloc.0
0x28d15  ldloc.0
0x28d16  brfalse.s loc_28D42
0x28d18  ldarg.0
0x28d19  ldarg.1
0x28d1a  call     void Microsoft.Crm.Extensibility.ODataV4.Edm.EdmExtensions::ValidateRequestAndThrowForMetadataEntity(class [System.Net.Http]System.Net.Http.HttpRequestMessage request, class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel edmModel)
0x28d1f  ldloc.1
0x28d20  call     bool Microsoft.Crm.Extensibility.ODataV4.Edm.EdmExtensions::CheckIfQueryParameterSupportedForCustomOptions(class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> queryParameters)
0x28d25  ldstr    aNoOtherQueryOp// "No Other Query options supported when S"...
0x28d2a  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x28d2f  ldarg.0
0x28d30  call     bool Microsoft.Crm.Extensibility.ODataV4.Edm.EdmExtensions::GetCountSegment(class [System.Net.Http]System.Net.Http.HttpRequestMessage request)
0x28d35  ldc.i4.0
0x28d36  ceq
0x28d38  ldstr    aCountSegmentIs// "Count Segment is not supported when Sav"...
0x28d3d  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x28d42  ldloc.0
0x28d43  ret
```
