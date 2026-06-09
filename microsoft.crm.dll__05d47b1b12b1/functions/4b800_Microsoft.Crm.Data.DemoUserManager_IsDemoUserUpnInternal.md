# Microsoft.Crm.Data.DemoUserManager::IsDemoUserUpnInternal

- ea: `0x4b800`
- end: `0x4b85f`
- name: `Microsoft.Crm.Data.DemoUserManager::IsDemoUserUpnInternal`
- size: `95`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x4b790`
- `0x4b7a0`
- `0x4b7e0`

## callees

- `0x4b800`

## string_xrefs

- `0x4b853`: `crmdemo.dynamics.com`

## pseudocode

```c

```

## disassembly

```asm
0x4b800  ldarg.1
0x4b801  ldnull
0x4b802  stind.ref
0x4b803  ldarg.2
0x4b804  ldc.i4.0
0x4b805  stind.i4
0x4b806  ldarg.0
0x4b807  ldc.i4.1
0x4b808  newarr   [mscorlib]System.Char
0x4b80d  dup
0x4b80e  ldc.i4.0
0x4b80f  ldc.i4.s 0x40
0x4b811  stelem.i2
0x4b812  callvirt instance string[] [mscorlib]System.String::Split(char[])
0x4b817  stloc.0
0x4b818  ldloc.0
0x4b819  ldc.i4.0
0x4b81a  ldelem.ref
0x4b81b  ldc.i4.1
0x4b81c  newarr   [mscorlib]System.Char
0x4b821  dup
0x4b822  ldc.i4.0
0x4b823  ldc.i4.s 0x5F
0x4b825  stelem.i2
0x4b826  callvirt instance string[] [mscorlib]System.String::Split(char[])
0x4b82b  stloc.1
0x4b82c  ldloc.1
0x4b82d  ldlen
0x4b82e  conv.i4
0x4b82f  ldc.i4.2
0x4b830  beq.s    loc_4B834
0x4b832  ldc.i4.0
0x4b833  ret
0x4b834  ldarg.1
0x4b835  ldloc.1
0x4b836  ldc.i4.0
0x4b837  ldelem.ref
0x4b838  stind.ref
0x4b839  ldloc.1
0x4b83a  ldc.i4.1
0x4b83b  ldelem.ref
0x4b83c  ldc.i4   0x1FF
0x4b841  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x4b846  ldarg.2
0x4b847  call     bool [mscorlib]System.Int32::TryParse(string, valuetype [mscorlib]System.Globalization.NumberStyles, class [mscorlib]System.IFormatProvider, int32&)
0x4b84c  brtrue.s loc_4B850
0x4b84e  ldc.i4.0
0x4b84f  ret
0x4b850  ldloc.0
0x4b851  ldc.i4.1
0x4b852  ldelem.ref
0x4b853  ldstr    aCrmdemoDynamic// "crmdemo.dynamics.com"
0x4b858  ldc.i4.5
0x4b859  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x4b85e  ret
```
