# Microsoft.Crm.Authentication.UrlPathPredicate::LoadExtensions

- ea: `0x44c0`
- end: `0x4514`
- name: `Microsoft.Crm.Authentication.UrlPathPredicate::LoadExtensions`
- size: `84`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x4340`

## callees

- `0x44c0`
- `0x4520`

## string_xrefs

- `0x44c1`: `configuration`

## pseudocode

```c

```

## disassembly

```asm
0x44c0  ldarg.1
0x44c1  ldstr    aConfiguration// "configuration"
0x44c6  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x44cb  ldarg.1
0x44cc  callvirt instance int32 class [mscorlib]System.Collections.Generic.ICollection`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>>::get_Count()
0x44d1  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor(int32)
0x44d6  stloc.0
0x44d7  ldarg.1
0x44d8  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>>::GetEnumerator()
0x44dd  stloc.1
0x44de  br.s     loc_44FE
0x44e0  ldloc.1
0x44e1  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>>::get_Current()
0x44e6  stloc.2
0x44e7  ldarg.0
0x44e8  ldloc.2
0x44e9  call     instance string Microsoft.Crm.Authentication.UrlPathPredicate::ValidateExtension(valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string> entry)
0x44ee  stloc.3
0x44ef  ldloc.3
0x44f0  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x44f5  brtrue.s loc_44FE
0x44f7  ldloc.0
0x44f8  ldloc.3
0x44f9  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x44fe  ldloc.1
0x44ff  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x4504  brtrue.s loc_44E0
0x4506  leave.s  loc_4512
0x4508  ldloc.1
0x4509  brfalse.s loc_4511
0x450b  ldloc.1
0x450c  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x4511  endfinally
0x4512  ldloc.0
0x4513  ret
```
