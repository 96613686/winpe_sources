# Microsoft.Xrm.Tools.OwinJobManager.Client.Helpers.HttpQueryStringHelper::ConvertTo

- ea: `0xa30`
- end: `0xa88`
- name: `Microsoft.Xrm.Tools.OwinJobManager.Client.Helpers.HttpQueryStringHelper::ConvertTo`
- size: `88`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0xd0`

## callees

- `0xa30`

## pseudocode

```c

```

## disassembly

```asm
0xa30  ldsfld   string [mscorlib]System.String::Empty
0xa35  call     class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpUtility::ParseQueryString(string)
0xa3a  stloc.0
0xa3b  ldarg.0
0xa3c  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>>::GetEnumerator()
0xa41  stloc.1
0xa42  br.s     loc_A6D
0xa44  ldloc.1
0xa45  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>>::get_Current()
0xa4a  stloc.2
0xa4b  ldloca.s 2
0xa4d  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>::get_Value()
0xa52  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0xa57  brtrue.s loc_A6D
0xa59  ldloc.0
0xa5a  ldloca.s 2
0xa5c  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>::get_Key()
0xa61  ldloca.s 2
0xa63  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>::get_Value()
0xa68  callvirt instance void [System]System.Collections.Specialized.NameValueCollection::Add(string, string)
0xa6d  ldloc.1
0xa6e  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0xa73  brtrue.s loc_A44
0xa75  leave.s  loc_A81
0xa77  ldloc.1
0xa78  brfalse.s loc_A80
0xa7a  ldloc.1
0xa7b  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xa80  endfinally
0xa81  ldloc.0
0xa82  callvirt instance string [mscorlib]System.Object::ToString()
0xa87  ret
```
