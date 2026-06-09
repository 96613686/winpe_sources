# Microsoft.Crm.Common.Repository::BuildCacheKey_0

- ea: `0x1640`
- end: `0x1837`
- name: `Microsoft.Crm.Common.Repository::BuildCacheKey_0`
- size: `503`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `broker_com_uri`

## callees

- `0xc30`
- `0xc50`
- `0x1640`
- `0x1870`
- `0x19d0`
- `0x19f0`
- `0x1a10`
- `0x1a30`
- `0x1a90`
- `0x1ab0`
- `0x1ad0`

## pseudocode

```c

```

## disassembly

```asm
0x1640  ldarg.0
0x1641  brtrue.s loc_164E
0x1643  ldstr    aQuery// "query"
0x1648  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x164d  throw
0x164e  call     class [mscorlib]System.StringComparer [mscorlib]System.StringComparer::get_Ordinal()
0x1653  newobj   instance void class [System]System.Collections.Generic.SortedSet`1<string>::.ctor(class [mscorlib]System.Collections.Generic.IComparer`1<var<u1>>)
0x1658  stloc.0
0x1659  ldarg.0
0x165a  callvirt instance class [mscorlib]System.Collections.Generic.ICollection`1<class Microsoft.Crm.Common.Specification> Microsoft.Crm.Common.RepositoryQuery::get_Specifications()
0x165f  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.Crm.Common.Specification>::GetEnumerator()
0x1664  stloc.3
0x1665  br.s     loc_16C6
0x1667  ldloc.3
0x1668  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class Microsoft.Crm.Common.Specification>::get_Current()
0x166d  stloc.s  4
0x166f  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1674  ldstr    a012// "{0}:{1}:{2};"
0x1679  ldc.i4.3
0x167a  newarr   [mscorlib]System.Object
0x167f  dup
0x1680  ldc.i4.0
0x1681  ldloc.s  4
0x1683  callvirt instance string Microsoft.Crm.Common.Specification::get_Property()
0x1688  callvirt instance string [mscorlib]System.String::ToUpperInvariant()
0x168d  stelem.ref
0x168e  dup
0x168f  ldc.i4.1
0x1690  ldloc.s  4
0x1692  callvirt instance valuetype Microsoft.Crm.Common.ComparisonOperator Microsoft.Crm.Common.Specification::get_Comparison()
0x1697  stloc.s  6
0x1699  ldloca.s 6
0x169b  constrained. Microsoft.Crm.Common.ComparisonOperator
0x16a1  callvirt instance string [mscorlib]System.Object::ToString()
0x16a6  stelem.ref
0x16a7  dup
0x16a8  ldc.i4.2
0x16a9  ldloc.s  4
0x16ab  callvirt instance object Microsoft.Crm.Common.Specification::get_Value()
0x16b0  call     string Microsoft.Crm.Common.Repository::StringRepresentationForValue(object value)
0x16b5  stelem.ref
0x16b6  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x16bb  stloc.s  5
0x16bd  ldloc.0
0x16be  ldloc.s  5
0x16c0  callvirt instance bool class [System]System.Collections.Generic.SortedSet`1<string>::Add(var<u1>)
0x16c5  pop
0x16c6  ldloc.3
0x16c7  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x16cc  brtrue.s loc_1667
0x16ce  leave.s  loc_16DA
0x16d0  ldloc.3
0x16d1  brfalse.s loc_16D9
0x16d3  ldloc.3
0x16d4  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x16d9  endfinally
0x16da  ldarg.0
0x16db  callvirt instance valuetype [mscorlib]System.Nullable`1<int32> Microsoft.Crm.Common.RepositoryQuery::get_Top()
0x16e0  stloc.s  7
0x16e2  ldloca.s 7
0x16e4  call     instance bool valuetype [mscorlib]System.Nullable`1<int32>::get_HasValue()
0x16e9  brfalse.s loc_1719
0x16eb  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x16f0  ldstr    aTop0// "Top:{0};"
0x16f5  ldc.i4.1
0x16f6  newarr   [mscorlib]System.Object
0x16fb  dup
0x16fc  ldc.i4.0
0x16fd  ldarg.0
0x16fe  callvirt instance valuetype [mscorlib]System.Nullable`1<int32> Microsoft.Crm.Common.RepositoryQuery::get_Top()
0x1703  box      valuetype [mscorlib]System.Nullable`1<int32>
0x1708  stelem.ref
0x1709  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x170e  stloc.s  8
0x1710  ldloc.0
0x1711  ldloc.s  8
0x1713  callvirt instance bool class [System]System.Collections.Generic.SortedSet`1<string>::Add(var<u1>)
0x1718  pop
0x1719  ldc.i4.0
0x171a  stloc.1
0x171b  ldarg.0
0x171c  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<class Microsoft.Crm.Common.PropertyOrder> Microsoft.Crm.Common.RepositoryQuery::get_OrderBy()
0x1721  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.Crm.Common.PropertyOrder>::GetEnumerator()
0x1726  stloc.s  9
0x1728  br.s     loc_1779
0x172a  ldloc.s  9
0x172c  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class Microsoft.Crm.Common.PropertyOrder>::get_Current()
0x1731  stloc.s  0xA
0x1733  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1738  ldstr    aOrder012// "Order{0}:{1}:{2};"
0x173d  ldc.i4.3
0x173e  newarr   [mscorlib]System.Object
0x1743  dup
0x1744  ldc.i4.0
0x1745  ldloc.1
0x1746  box      [mscorlib]System.Int32
0x174b  stelem.ref
0x174c  dup
0x174d  ldc.i4.1
0x174e  ldloc.s  0xA
0x1750  callvirt instance bool Microsoft.Crm.Common.PropertyOrder::get_AscendingOrder()
0x1755  box      [mscorlib]System.Boolean
0x175a  stelem.ref
0x175b  dup
0x175c  ldc.i4.2
0x175d  ldloc.s  0xA
0x175f  callvirt instance string Microsoft.Crm.Common.PropertyOrder::get_Property()
0x1764  stelem.ref
0x1765  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x176a  stloc.s  0xB
0x176c  ldloc.1
0x176d  ldc.i4.1
0x176e  add
0x176f  stloc.1
0x1770  ldloc.0
0x1771  ldloc.s  0xB
0x1773  callvirt instance bool class [System]System.Collections.Generic.SortedSet`1<string>::Add(var<u1>)
0x1778  pop
0x1779  ldloc.s  9
0x177b  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x1780  brtrue.s loc_172A
0x1782  leave.s  loc_1790
0x1784  ldloc.s  9
0x1786  brfalse.s loc_178F
0x1788  ldloc.s  9
0x178a  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x178f  endfinally
0x1790  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x1795  stloc.2
0x1796  ldloc.2
0x1797  ldtoken  mvar<u1>
0x179c  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x17a1  callvirt instance string [mscorlib]System.Type::get_FullName()
0x17a6  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x17ab  pop
0x17ac  ldloc.2
0x17ad  ldstr    asc_2974// ";"
0x17b2  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x17b7  pop
0x17b8  ldloc.2
0x17b9  ldstr    asc_2978// ":"
0x17be  ldarg.0
0x17bf  callvirt instance class [mscorlib]System.Collections.Generic.ICollection`1<string> Microsoft.Crm.Common.RepositoryQuery::get_PropertiesToReturn()
0x17c4  call     string [mscorlib]System.String::Join(string, class [mscorlib]System.Collections.Generic.IEnumerable`1<string>)
0x17c9  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x17ce  pop
0x17cf  ldloc.2
0x17d0  ldstr    asc_2974// ";"
0x17d5  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x17da  pop
0x17db  ldloc.0
0x17dc  callvirt instance valuetype [System]System.Collections.Generic.SortedSet`1/Enumerator<var<u1>> class [System]System.Collections.Generic.SortedSet`1<string>::GetEnumerator()
0x17e1  stloc.s  0xC
0x17e3  br.s     loc_17F7
0x17e5  ldloca.s 0xC
0x17e7  call     instance var<u1> valuetype [System]System.Collections.Generic.SortedSet`1/Enumerator<string>::get_Current()
0x17ec  stloc.s  0xD
0x17ee  ldloc.2
0x17ef  ldloc.s  0xD
0x17f1  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x17f6  pop
0x17f7  ldloca.s 0xC
0x17f9  call     instance bool valuetype [System]System.Collections.Generic.SortedSet`1/Enumerator<string>::MoveNext()
0x17fe  brtrue.s loc_17E5
0x1800  leave.s  loc_1810
0x1802  ldloca.s 0xC
0x1804  constrained. valuetype [System]System.Collections.Generic.SortedSet`1/Enumerator<string>
0x180a  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x180f  endfinally
0x1810  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1815  ldstr    a01// "{0}{1}"
0x181a  ldc.i4.2
0x181b  newarr   [mscorlib]System.Object
0x1820  dup
0x1821  ldc.i4.0
0x1822  ldstr    aRepository// "Repository_"
0x1827  stelem.ref
0x1828  dup
0x1829  ldc.i4.1
0x182a  ldloc.2
0x182b  callvirt instance string [mscorlib]System.Object::ToString()
0x1830  stelem.ref
0x1831  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x1836  ret
```
