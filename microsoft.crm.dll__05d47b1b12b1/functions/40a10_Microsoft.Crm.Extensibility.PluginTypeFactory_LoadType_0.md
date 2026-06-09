# Microsoft.Crm.Extensibility.PluginTypeFactory::LoadType_0

- ea: `0x40a10`
- end: `0x40a3e`
- name: `Microsoft.Crm.Extensibility.PluginTypeFactory::LoadType_0`
- size: `46`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x40a90`

## callees

- `0x40a10`

## string_xrefs

- `0x40a21`: `Unable to load the plugin type: {0}`

## pseudocode

```c

```

## disassembly

```asm
0x40a10  ldarg.1
0x40a11  ldarg.0
0x40a12  ldc.i4.1
0x40a13  callvirt instance class [mscorlib]System.Type [mscorlib]System.Reflection.Assembly::GetType(string, bool)
0x40a18  stloc.0
0x40a19  leave.s  loc_40A3C
0x40a1b  stloc.1
0x40a1c  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x40a21  ldstr    aUnableToLoadTh// "Unable to load the plugin type: {0}"
0x40a26  ldc.i4.1
0x40a27  newarr   [mscorlib]System.Object
0x40a2c  dup
0x40a2d  ldc.i4.0
0x40a2e  ldarg.0
0x40a2f  stelem.ref
0x40a30  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x40a35  ldloc.1
0x40a36  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmTypeLoadException::.ctor(string, class [mscorlib]System.Exception)
0x40a3b  throw
0x40a3c  ldloc.0
0x40a3d  ret
```
