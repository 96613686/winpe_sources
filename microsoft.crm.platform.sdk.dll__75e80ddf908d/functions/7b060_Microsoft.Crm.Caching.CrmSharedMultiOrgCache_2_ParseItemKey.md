# Microsoft.Crm.Caching.CrmSharedMultiOrgCache`2::ParseItemKey

- ea: `0x7b060`
- end: `0x7b194`
- name: `Microsoft.Crm.Caching.CrmSharedMultiOrgCache`2::ParseItemKey`
- size: `308`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x7b060`

## string_xrefs

- `0x7b099`: `We must alsways find the '}' (close bracket) of the version number for a cached item`
- `0x7b128`: `We must always find the '}' (close bracket) of the version number for a cached item`

## pseudocode

```c

```

## disassembly

```asm
0x7b060  ldarg.1
0x7b061  switch   loc_7B077, loc_7B0E2, loc_7B111
0x7b072  br       loc_7B17E
0x7b077  ldarg.2
0x7b078  ldc.i4.0
0x7b079  ldc.i4.s 0x26
0x7b07b  callvirt instance string [mscorlib]System.String::Substring(int32, int32)
0x7b080  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x7b085  ldc.i4.s 0x26
0x7b087  stloc.0
0x7b088  ldarg.2
0x7b089  ldc.i4.s 0x7D
0x7b08b  ldloc.0
0x7b08c  callvirt instance int32 [mscorlib]System.String::IndexOf(char, int32)
0x7b091  stloc.1
0x7b092  ldc.i4.m1
0x7b093  ldloc.1
0x7b094  ceq
0x7b096  ldc.i4.0
0x7b097  ceq
0x7b099  ldstr    aWeMustAlswaysF// "We must alsways find the '}' (close bra"...
0x7b09e  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x7b0a3  ldloc.0
0x7b0a4  ldc.i4.1
0x7b0a5  add
0x7b0a6  stloc.2
0x7b0a7  ldloc.1
0x7b0a8  ldc.i4.1
0x7b0a9  sub
0x7b0aa  ldloc.2
0x7b0ab  sub
0x7b0ac  ldc.i4.1
0x7b0ad  add
0x7b0ae  stloc.3
0x7b0af  ldarg.2
0x7b0b0  ldloc.2
0x7b0b1  ldloc.3
0x7b0b2  callvirt instance string [mscorlib]System.String::Substring(int32, int32)
0x7b0b7  newobj   instance void [mscorlib]System.Version::.ctor(string)
0x7b0bc  stloc.s  4
0x7b0be  ldloc.1
0x7b0bf  ldc.i4.1
0x7b0c0  add
0x7b0c1  stloc.s  5
0x7b0c3  ldarg.0
0x7b0c4  ldarg.2
0x7b0c5  ldloc.s  5
0x7b0c7  callvirt instance string [mscorlib]System.String::Substring(int32)
0x7b0cc  callvirt instance var<u1> class Microsoft.Crm.Caching.CrmMultiOrgCacheBase`2<var<u1>, !!T0>::ConvertStringToKey(!!T0)
0x7b0d1  stloc.s  6
0x7b0d3  newobj   instance void valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::.ctor(var<u1>)
0x7b0d8  ldloc.s  4
0x7b0da  ldloc.s  6
0x7b0dc  newobj   instance void valuetype Microsoft.Crm.Caching.OrganizationKeyWrapper`1<var<u1>>::.ctor(valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>, class [mscorlib]System.Version, var<u1>)
0x7b0e1  ret
0x7b0e2  ldarg.2
0x7b0e3  ldc.i4.0
0x7b0e4  ldc.i4.s 0x26
0x7b0e6  callvirt instance string [mscorlib]System.String::Substring(int32, int32)
0x7b0eb  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x7b0f0  ldc.i4.s 0x26
0x7b0f2  stloc.s  7
0x7b0f4  ldarg.0
0x7b0f5  ldarg.2
0x7b0f6  ldloc.s  7
0x7b0f8  callvirt instance string [mscorlib]System.String::Substring(int32)
0x7b0fd  callvirt instance var<u1> class Microsoft.Crm.Caching.CrmMultiOrgCacheBase`2<var<u1>, !!T0>::ConvertStringToKey(!!T0)
0x7b102  stloc.s  8
0x7b104  newobj   instance void valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::.ctor(var<u1>)
0x7b109  ldloc.s  8
0x7b10b  newobj   instance void valuetype Microsoft.Crm.Caching.OrganizationKeyWrapper`1<var<u1>>::.ctor(valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>, var<u1>)
0x7b110  ret
0x7b111  ldc.i4.0
0x7b112  stloc.s  9
0x7b114  ldarg.2
0x7b115  ldc.i4.s 0x7D
0x7b117  ldloc.s  9
0x7b119  callvirt instance int32 [mscorlib]System.String::IndexOf(char, int32)
0x7b11e  stloc.s  0xA
0x7b120  ldc.i4.m1
0x7b121  ldloc.s  0xA
0x7b123  ceq
0x7b125  ldc.i4.0
0x7b126  ceq
0x7b128  ldstr    aWeMustAlwaysFi// "We must always find the '}' (close brac"...
0x7b12d  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x7b132  ldloc.s  9
0x7b134  ldc.i4.1
0x7b135  add
0x7b136  stloc.s  0xB
0x7b138  ldloc.s  0xA
0x7b13a  ldc.i4.1
0x7b13b  sub
0x7b13c  ldloc.s  0xB
0x7b13e  sub
0x7b13f  ldc.i4.1
0x7b140  add
0x7b141  stloc.s  0xC
0x7b143  ldarg.2
0x7b144  ldloc.s  0xB
0x7b146  ldloc.s  0xC
0x7b148  callvirt instance string [mscorlib]System.String::Substring(int32, int32)
0x7b14d  newobj   instance void [mscorlib]System.Version::.ctor(string)
0x7b152  stloc.s  0xD
0x7b154  ldloc.s  0xA
0x7b156  ldc.i4.1
0x7b157  add
0x7b158  stloc.s  0xE
0x7b15a  ldarg.0
0x7b15b  ldarg.2
0x7b15c  ldloc.s  0xE
0x7b15e  callvirt instance string [mscorlib]System.String::Substring(int32)
0x7b163  callvirt instance var<u1> class Microsoft.Crm.Caching.CrmMultiOrgCacheBase`2<var<u1>, !!T0>::ConvertStringToKey(!!T0)
0x7b168  stloc.s  0xF
0x7b16a  ldloca.s 0x10
0x7b16c  initobj  valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>
0x7b172  ldloc.s  0x10
0x7b174  ldloc.s  0xD
0x7b176  ldloc.s  0xF
0x7b178  newobj   instance void valuetype Microsoft.Crm.Caching.OrganizationKeyWrapper`1<var<u1>>::.ctor(valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>, class [mscorlib]System.Version, var<u1>)
0x7b17d  ret
0x7b17e  ldstr    aItemkeytype// "itemKeyType"
0x7b183  ldarg.1
0x7b184  box      Microsoft.Crm.Caching.ItemKeyType
0x7b189  ldstr    aUnknownEnumVal// "Unknown enum value"
0x7b18e  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmArgumentOutOfRangeException::.ctor(string, object, string)
0x7b193  throw
```
