# Microsoft.Crm.Protocols.WSTrust.Bindings.ClientExceptionHelper::GetString

- ea: `0x1850`
- end: `0x1872`
- name: `Microsoft.Crm.Protocols.WSTrust.Bindings.ClientExceptionHelper::GetString`
- size: `34`
- prototype: ``
- caller_count: `6`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0xe60`
- `0x1000`
- `0x11e0`
- `0x1480`
- `0x1540`
- `0x1750`

## callees

- `0x1850`

## pseudocode

```c

```

## disassembly

```asm
0x1850  ldarg.0
0x1851  stloc.0
0x1852  ldarg.0
0x1853  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x1858  brfalse.s loc_185C
0x185a  ldarg.0
0x185b  ret
0x185c  ldarg.1
0x185d  brfalse.s loc_1870
0x185f  ldarg.1
0x1860  ldlen
0x1861  brfalse.s loc_1870
0x1863  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentCulture()
0x1868  ldloc.0
0x1869  ldarg.1
0x186a  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x186f  stloc.0
0x1870  ldloc.0
0x1871  ret
```
