# Microsoft.Crm.Application.Bundling.JsFile::get_CacheKey

- ea: `0x128f0`
- end: `0x12927`
- name: `Microsoft.Crm.Application.Bundling.JsFile::get_CacheKey`
- size: `55`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x12950`

## callees

- `0x128f0`
- `0x12930`

## string_xrefs

- `0x128fe`: `JsFileCache_`

## pseudocode

```c

```

## disassembly

```asm
0x128f0  ldarg.0
0x128f1  ldfld    string Microsoft.Crm.Application.Bundling.JsFile::_cacheKey
0x128f6  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x128fb  brfalse.s loc_12920
0x128fd  ldarg.0
0x128fe  ldstr    aJsfilecache// "JsFileCache_"
0x12903  ldarg.0
0x12904  call     instance int32 Microsoft.Crm.Application.Bundling.JsFile::get_HashKey()
0x12909  stloc.0
0x1290a  ldloca.s 0
0x1290c  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x12911  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x12916  call     string [mscorlib]System.String::Concat(string, string)
0x1291b  stfld    string Microsoft.Crm.Application.Bundling.JsFile::_cacheKey
0x12920  ldarg.0
0x12921  ldfld    string Microsoft.Crm.Application.Bundling.JsFile::_cacheKey
0x12926  ret
```
