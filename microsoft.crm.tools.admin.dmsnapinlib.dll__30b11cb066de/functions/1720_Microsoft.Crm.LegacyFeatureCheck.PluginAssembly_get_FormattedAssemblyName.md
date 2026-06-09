# Microsoft.Crm.LegacyFeatureCheck.PluginAssembly::get_FormattedAssemblyName

- ea: `0x1720`
- end: `0x175a`
- name: `Microsoft.Crm.LegacyFeatureCheck.PluginAssembly::get_FormattedAssemblyName`
- size: `58`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14a0`

## callees

- `0x1300`
- `0x1340`
- `0x1380`
- `0x13a0`

## string_xrefs

- `0x1725`: `{0}, Version={1}, Culture={2}, PublicKeyToken={3}`

## pseudocode

```c

```

## disassembly

```asm
0x1720  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1725  ldstr    a0Version1Cultu// "{0}, Version={1}, Culture={2}, PublicKe"...
0x172a  ldc.i4.4
0x172b  newarr   [mscorlib]System.Object
0x1730  dup
0x1731  ldc.i4.0
0x1732  ldarg.0
0x1733  call     instance string Microsoft.Crm.LegacyFeatureCheck.PluginAssembly::get_Name()
0x1738  stelem.ref
0x1739  dup
0x173a  ldc.i4.1
0x173b  ldarg.0
0x173c  call     instance string Microsoft.Crm.LegacyFeatureCheck.PluginAssembly::get_Version()
0x1741  stelem.ref
0x1742  dup
0x1743  ldc.i4.2
0x1744  ldarg.0
0x1745  call     instance string Microsoft.Crm.LegacyFeatureCheck.PluginAssembly::get_Culture()
0x174a  stelem.ref
0x174b  dup
0x174c  ldc.i4.3
0x174d  ldarg.0
0x174e  call     instance string Microsoft.Crm.LegacyFeatureCheck.PluginAssembly::get_PublicKeyToken()
0x1753  stelem.ref
0x1754  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x1759  ret
```
