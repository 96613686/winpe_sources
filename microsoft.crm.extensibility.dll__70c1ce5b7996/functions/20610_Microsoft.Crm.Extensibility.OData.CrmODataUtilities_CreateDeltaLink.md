# Microsoft.Crm.Extensibility.OData.CrmODataUtilities::CreateDeltaLink

- ea: `0x20610`
- end: `0x206d3`
- name: `Microsoft.Crm.Extensibility.OData.CrmODataUtilities::CreateDeltaLink`
- size: `195`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x32f0`
- `0x3c20`

## callees

- `0x20610`
- `0x206e0`
- `0x28fe0`
- `0x29060`

## string_xrefs

- `0x2066f`: `$deltatoken`
- `0x206bb`: `$deltatoken`

## pseudocode

```c

```

## disassembly

```asm
0x20610  newobj   instance void [System]System.UriBuilder::.ctor()
0x20615  stloc.0
0x20616  ldarg.0
0x20617  call     class [System]System.Uri Microsoft.Crm.Extensibility.ODataV4.Edm.EdmExtensions::GetServiceRouteUri(class [System.Net.Http]System.Net.Http.HttpRequestMessage request)
0x2061c  stloc.1
0x2061d  ldloc.0
0x2061e  ldloc.1
0x2061f  callvirt instance string [System]System.Uri::get_Scheme()
0x20624  callvirt instance void [System]System.UriBuilder::set_Scheme(string)
0x20629  ldloc.0
0x2062a  ldloc.1
0x2062b  callvirt instance string [System]System.Uri::get_Host()
0x20630  callvirt instance void [System]System.UriBuilder::set_Host(string)
0x20635  ldloc.0
0x20636  ldarg.0
0x20637  callvirt instance class [System]System.Uri [System.Net.Http]System.Net.Http.HttpRequestMessage::get_RequestUri()
0x2063c  callvirt instance string [System]System.Uri::get_AbsolutePath()
0x20641  callvirt instance void [System]System.UriBuilder::set_Path(string)
0x20646  ldloc.0
0x20647  ldloc.1
0x20648  callvirt instance int32 [System]System.Uri::get_Port()
0x2064d  callvirt instance void [System]System.UriBuilder::set_Port(int32)
0x20652  ldarg.0
0x20653  call     class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.Crm.Extensibility.ODataV4.Edm.EdmExtensions::QueryParameterDictionary(class [System.Net.Http]System.Net.Http.HttpRequestMessage request)
0x20658  callvirt instance valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::GetEnumerator()
0x2065d  stloc.2
0x2065e  br.s     loc_206A2
0x20660  ldloca.s 2
0x20662  call     instance valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<var<u1>, !!T0> valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<string, string>::get_Current()
0x20667  stloc.3
0x20668  ldloca.s 3
0x2066a  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>::get_Key()
0x2066f  ldstr    aDeltatoken// "$deltatoken"
0x20674  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x20679  brfalse.s loc_206A2
0x2067b  ldloca.s 3
0x2067d  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>::get_Key()
0x20682  ldstr    aSelect// "$select"
0x20687  call     bool [mscorlib]System.String::op_Equality(string, string)
0x2068c  brfalse.s loc_206A2
0x2068e  ldloca.s 3
0x20690  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>::get_Key()
0x20695  ldloca.s 3
0x20697  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>::get_Value()
0x2069c  ldloc.0
0x2069d  call     void Microsoft.Crm.Extensibility.OData.CrmODataUtilities::AddToQueryPath(string queryParameterKey, string queryParameterValue, class [System]System.UriBuilder uriPath)
0x206a2  ldloca.s 2
0x206a4  call     instance bool valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<string, string>::MoveNext()
0x206a9  brtrue.s loc_20660
0x206ab  leave.s  loc_206BB
0x206ad  ldloca.s 2
0x206af  constrained. valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<string, string>
0x206b5  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x206ba  endfinally
0x206bb  ldstr    aDeltatoken// "$deltatoken"
0x206c0  ldarg.1
0x206c1  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmUrlEncode(string)
0x206c6  ldloc.0
0x206c7  call     void Microsoft.Crm.Extensibility.OData.CrmODataUtilities::AddToQueryPath(string queryParameterKey, string queryParameterValue, class [System]System.UriBuilder uriPath)
0x206cc  ldloc.0
0x206cd  callvirt instance class [System]System.Uri [System]System.UriBuilder::get_Uri()
0x206d2  ret
```
