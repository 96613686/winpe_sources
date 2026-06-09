# Microsoft.Crm.CrmPluginAssemblyMetadata::ToString

- ea: `0x1dd90`
- end: `0x1de0a`
- name: `Microsoft.Crm.CrmPluginAssemblyMetadata::ToString`
- size: `122`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1f0b0`
- `0x1f0d0`
- `0x1f0f0`
- `0x1f110`

## string_xrefs

- `0x1ddc6`: `PublicKeyToken`
- `0x1ddd5`: `{0}, Version={1}, Culture={2}, PublicKeyToken={3}`

## pseudocode

```c

```

## disassembly

```asm
0x1dd90  ldarg.0
0x1dd91  call     instance string Microsoft.Crm.CrmPluginAssemblyMetadata::get_ShortName()
0x1dd96  ldstr    aShortname// "ShortName"
0x1dd9b  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string, string)
0x1dda0  ldarg.0
0x1dda1  call     instance string Microsoft.Crm.CrmPluginAssemblyMetadata::get_Version()
0x1dda6  ldstr    aVersion// "Version"
0x1ddab  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string, string)
0x1ddb0  ldarg.0
0x1ddb1  call     instance string Microsoft.Crm.CrmPluginAssemblyMetadata::get_Culture()
0x1ddb6  ldstr    aCulture// "Culture"
0x1ddbb  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string, string)
0x1ddc0  ldarg.0
0x1ddc1  call     instance string Microsoft.Crm.CrmPluginAssemblyMetadata::get_PublicKeyToken()
0x1ddc6  ldstr    aPublickeytoken// "PublicKeyToken"
0x1ddcb  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string, string)
0x1ddd0  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1ddd5  ldstr    a0Version1Cultu// "{0}, Version={1}, Culture={2}, PublicKe"...
0x1ddda  ldc.i4.4
0x1dddb  newarr   [mscorlib]System.Object
0x1dde0  dup
0x1dde1  ldc.i4.0
0x1dde2  ldarg.0
0x1dde3  call     instance string Microsoft.Crm.CrmPluginAssemblyMetadata::get_ShortName()
0x1dde8  stelem.ref
0x1dde9  dup
0x1ddea  ldc.i4.1
0x1ddeb  ldarg.0
0x1ddec  call     instance string Microsoft.Crm.CrmPluginAssemblyMetadata::get_Version()
0x1ddf1  stelem.ref
0x1ddf2  dup
0x1ddf3  ldc.i4.2
0x1ddf4  ldarg.0
0x1ddf5  call     instance string Microsoft.Crm.CrmPluginAssemblyMetadata::get_Culture()
0x1ddfa  stelem.ref
0x1ddfb  dup
0x1ddfc  ldc.i4.3
0x1ddfd  ldarg.0
0x1ddfe  call     instance string Microsoft.Crm.CrmPluginAssemblyMetadata::get_PublicKeyToken()
0x1de03  stelem.ref
0x1de04  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x1de09  ret
```
