# Microsoft.Crm.Extensibility.PluginAssemblyFactory::FormatAssemblyName

- ea: `0x40ca0`
- end: `0x40cc6`
- name: `Microsoft.Crm.Extensibility.PluginAssemblyFactory::FormatAssemblyName`
- size: `38`
- prototype: ``
- caller_count: `3`
- callee_count: `0`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x40a40`
- `0x40cd0`
- `0x40d70`

## string_xrefs

- `0x40ca5`: `{0}, Version={1}, Culture={2}, PublicKeyToken={3}`

## pseudocode

```c

```

## disassembly

```asm
0x40ca0  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x40ca5  ldstr    a0Version1Cultu// "{0}, Version={1}, Culture={2}, PublicKe"...
0x40caa  ldc.i4.4
0x40cab  newarr   [mscorlib]System.Object
0x40cb0  dup
0x40cb1  ldc.i4.0
0x40cb2  ldarg.0
0x40cb3  stelem.ref
0x40cb4  dup
0x40cb5  ldc.i4.1
0x40cb6  ldarg.1
0x40cb7  stelem.ref
0x40cb8  dup
0x40cb9  ldc.i4.2
0x40cba  ldarg.2
0x40cbb  stelem.ref
0x40cbc  dup
0x40cbd  ldc.i4.3
0x40cbe  ldarg.3
0x40cbf  stelem.ref
0x40cc0  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x40cc5  ret
```
