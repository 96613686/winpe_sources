# Microsoft.Crm.Common.Repository::FlushCache

- ea: `0xce0`
- end: `0xd57`
- name: `Microsoft.Crm.Common.Repository::FlushCache`
- size: `119`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0xb70`
- `0xce0`
- `0x1840`
- `0x1e10`

## string_xrefs

- `0xce8`: `cacheKey`

## pseudocode

```c

```

## disassembly

```asm
0xce0  ldarg.1
0xce1  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0xce6  brfalse.s loc_CF3
0xce8  ldstr    aCachekey// "cacheKey"
0xced  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xcf2  throw
0xcf3  ldarg.1
0xcf4  call     string Microsoft.Crm.Common.Repository::GetTypeFromCacheKey(string cacheKey)
0xcf9  stloc.0
0xcfa  ldarg.0
0xcfb  ldfld    class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<class [mscorlib]System.Type, class TypeInformation> Microsoft.Crm.Common.Repository::_typeInformation
0xd00  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<var<u1>, !!T0>> class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<class [mscorlib]System.Type, class TypeInformation>::GetEnumerator()
0xd05  stloc.1
0xd06  br.s     loc_D42
0xd08  ldloc.1
0xd09  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<class [mscorlib]System.Type, class TypeInformation>>::get_Current()
0xd0e  stloc.2
0xd0f  ldloca.s 2
0xd11  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<class [mscorlib]System.Type, class TypeInformation>::get_Key()
0xd16  callvirt instance string [mscorlib]System.Type::get_FullName()
0xd1b  ldloc.0
0xd1c  ldc.i4.5
0xd1d  call     bool [mscorlib]System.String::Equals(string, string, valuetype [mscorlib]System.StringComparison)
0xd22  brfalse.s loc_D42
0xd24  ldloca.s 2
0xd26  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<class [mscorlib]System.Type, class TypeInformation>::get_Value()
0xd2b  stloc.3
0xd2c  ldloc.3
0xd2d  callvirt instance class Microsoft.Crm.Common.ICacheProvider TypeInformation::get_CacheProvider()
0xd32  brfalse.s loc_D4A
0xd34  ldloc.3
0xd35  callvirt instance class Microsoft.Crm.Common.ICacheProvider TypeInformation::get_CacheProvider()
0xd3a  ldarg.1
0xd3b  callvirt instance void Microsoft.Crm.Common.ICacheProvider::Remove(string key)
0xd40  leave.s  loc_D56
0xd42  ldloc.1
0xd43  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0xd48  brtrue.s loc_D08
0xd4a  leave.s  loc_D56
0xd4c  ldloc.1
0xd4d  brfalse.s loc_D55
0xd4f  ldloc.1
0xd50  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xd55  endfinally
0xd56  ret
```
