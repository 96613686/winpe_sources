# Microsoft.Crm.Extensibility.OData.CrmODataUtilities::CreateNextPageLink

- ea: `0x20450`
- end: `0x20609`
- name: `Microsoft.Crm.Extensibility.OData.CrmODataUtilities::CreateNextPageLink`
- size: `441`
- prototype: ``
- caller_count: `3`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x32f0`
- `0x3c20`
- `0x12a60`

## callees

- `0x20450`
- `0x206e0`
- `0x20770`
- `0x20960`
- `0x28fe0`
- `0x29060`

## string_xrefs

- `0x2050a`: `$skiptoken`
- `0x205f6`: `$skiptoken`

## pseudocode

```c

```

## disassembly

```asm
0x20450  newobj   instance void [System]System.UriBuilder::.ctor()
0x20455  stloc.0
0x20456  ldarg.0
0x20457  call     class [System]System.Uri Microsoft.Crm.Extensibility.ODataV4.Edm.EdmExtensions::GetServiceRouteUri(class [System.Net.Http]System.Net.Http.HttpRequestMessage request)
0x2045c  stloc.1
0x2045d  ldloc.0
0x2045e  ldloc.1
0x2045f  callvirt instance string [System]System.Uri::get_Scheme()
0x20464  callvirt instance void [System]System.UriBuilder::set_Scheme(string)
0x20469  ldloc.0
0x2046a  ldloc.1
0x2046b  callvirt instance string [System]System.Uri::get_Host()
0x20470  callvirt instance void [System]System.UriBuilder::set_Host(string)
0x20475  ldloc.0
0x20476  ldarg.0
0x20477  callvirt instance class [System]System.Uri [System.Net.Http]System.Net.Http.HttpRequestMessage::get_RequestUri()
0x2047c  callvirt instance string [System]System.Uri::get_AbsolutePath()
0x20481  callvirt instance void [System]System.UriBuilder::set_Path(string)
0x20486  ldarga.s 3
0x20488  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::get_HasValue()
0x2048d  brfalse.s loc_204B7
0x2048f  ldloc.0
0x20490  dup
0x20491  callvirt instance string [System]System.UriBuilder::get_Path()
0x20496  ldstr    asc_3B90E// "("
0x2049b  ldarga.s 3
0x2049d  constrained. valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>
0x204a3  callvirt instance string [mscorlib]System.Object::ToString()
0x204a8  ldstr    asc_36900// ")"
0x204ad  call     string [mscorlib]System.String::Concat(string, string, string, string)
0x204b2  callvirt instance void [System]System.UriBuilder::set_Path(string)
0x204b7  ldloc.0
0x204b8  ldloc.1
0x204b9  callvirt instance int32 [System]System.Uri::get_Port()
0x204be  callvirt instance void [System]System.UriBuilder::set_Port(int32)
0x204c3  ldarg.0
0x204c4  call     class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.Crm.Extensibility.ODataV4.Edm.EdmExtensions::QueryParameterDictionary(class [System.Net.Http]System.Net.Http.HttpRequestMessage request)
0x204c9  dup
0x204ca  ldsfld   class [mscorlib]System.Func`2<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>, bool> <>c::<>9__49_0
0x204cf  dup
0x204d0  brtrue.s loc_204E9
0x204d2  pop
0x204d3  ldsfld   class <>c <>c::<>9
0x204d8  ldftn    instance bool <>c::<CreateNextPageLink>b__49_0(valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string> x)
0x204de  newobj   instance void class [mscorlib]System.Func`2<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>, bool>::.ctor(object, native int)
0x204e3  dup
0x204e4  stsfld   class [mscorlib]System.Func`2<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>, bool> <>c::<>9__49_0
0x204e9  call     T0x2B0000C1
0x204ee  stloc.2
0x204ef  callvirt instance valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::GetEnumerator()
0x204f4  stloc.3
0x204f5  br       loc_205DA
0x204fa  ldloca.s 3
0x204fc  call     instance valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<var<u1>, !!T0> valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<string, string>::get_Current()
0x20501  stloc.s  4
0x20503  ldloca.s 4
0x20505  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>::get_Key()
0x2050a  ldstr    aSkiptoken// "$skiptoken"
0x2050f  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x20514  brfalse  loc_205DA
0x20519  ldloca.s 4
0x2051b  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>::get_Key()
0x20520  ldstr    aExpand// "$expand"
0x20525  call     bool [mscorlib]System.String::op_Equality(string, string)
0x2052a  brfalse.s loc_205A8
0x2052c  ldarg.2
0x2052d  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x20532  brfalse.s loc_2054D
0x20534  ldloca.s 4
0x20536  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>::get_Key()
0x2053b  ldloca.s 4
0x2053d  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>::get_Value()
0x20542  ldloc.0
0x20543  call     void Microsoft.Crm.Extensibility.OData.CrmODataUtilities::AddToQueryPath(string queryParameterKey, string queryParameterValue, class [System]System.UriBuilder uriPath)
0x20548  br       loc_205DA
0x2054d  ldloca.s 4
0x2054f  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>::get_Value()
0x20554  ldarg.2
0x20555  ldloc.0
0x20556  callvirt instance class [System]System.Uri [System]System.UriBuilder::get_Uri()
0x2055b  call     valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string> Microsoft.Crm.Extensibility.OData.CrmODataUtilities::GetNavigationClauseSegment(string expandClause, string navigationPropertyName, class [System]System.Uri uriPath)
0x20560  stloc.s  5
0x20562  ldloca.s 5
0x20564  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>::get_Key()
0x20569  ldsfld   string [mscorlib]System.String::Empty
0x2056e  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x20573  brfalse.s loc_205DA
0x20575  ldloc.0
0x20576  dup
0x20577  callvirt instance string [System]System.UriBuilder::get_Path()
0x2057c  ldstr    asc_422BE// "/"
0x20581  ldloca.s 5
0x20583  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>::get_Key()
0x20588  call     string [mscorlib]System.String::Concat(string, string, string)
0x2058d  callvirt instance void [System]System.UriBuilder::set_Path(string)
0x20592  ldloca.s 5
0x20594  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>::get_Key()
0x20599  ldloca.s 5
0x2059b  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>::get_Value()
0x205a0  ldloc.0
0x205a1  call     void Microsoft.Crm.Extensibility.OData.CrmODataUtilities::AddQueryStringToExpandClauses(string expandClauseSegment, string queryPath, class [System]System.UriBuilder uriPath)
0x205a6  br.s     loc_205DA
0x205a8  ldloc.2
0x205a9  brfalse.s loc_205C6
0x205ab  ldarg.2
0x205ac  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x205b1  brtrue.s loc_205C6
0x205b3  ldloca.s 4
0x205b5  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>::get_Key()
0x205ba  ldstr    aNolock// "NoLock"
0x205bf  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x205c4  brtrue.s loc_205DA
0x205c6  ldloca.s 4
0x205c8  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>::get_Key()
0x205cd  ldloca.s 4
0x205cf  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>::get_Value()
0x205d4  ldloc.0
0x205d5  call     void Microsoft.Crm.Extensibility.OData.CrmODataUtilities::AddToQueryPath(string queryParameterKey, string queryParameterValue, class [System]System.UriBuilder uriPath)
0x205da  ldloca.s 3
0x205dc  call     instance bool valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<string, string>::MoveNext()
0x205e1  brtrue   loc_204FA
0x205e6  leave.s  loc_205F6
0x205e8  ldloca.s 3
0x205ea  constrained. valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<string, string>
0x205f0  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x205f5  endfinally
0x205f6  ldstr    aSkiptoken// "$skiptoken"
0x205fb  ldarg.1
0x205fc  ldloc.0
0x205fd  call     void Microsoft.Crm.Extensibility.OData.CrmODataUtilities::AddToQueryPath(string queryParameterKey, string queryParameterValue, class [System]System.UriBuilder uriPath)
0x20602  ldloc.0
0x20603  callvirt instance class [System]System.Uri [System]System.UriBuilder::get_Uri()
0x20608  ret
```
