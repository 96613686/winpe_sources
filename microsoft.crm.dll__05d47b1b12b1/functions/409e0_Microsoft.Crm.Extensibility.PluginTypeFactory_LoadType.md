# Microsoft.Crm.Extensibility.PluginTypeFactory::LoadType

- ea: `0x409e0`
- end: `0x40a0d`
- name: `Microsoft.Crm.Extensibility.PluginTypeFactory::LoadType`
- size: `45`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x409e0`

## string_xrefs

- `0x409f0`: `Unable to load the plugin type: {0}`

## pseudocode

```c

```

## disassembly

```asm
0x409e0  ldarg.0
0x409e1  ldc.i4.1
0x409e2  call     class [mscorlib]System.Type [mscorlib]System.Type::GetType(string, bool)
0x409e7  stloc.0
0x409e8  leave.s  loc_40A0B
0x409ea  stloc.1
0x409eb  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x409f0  ldstr    aUnableToLoadTh// "Unable to load the plugin type: {0}"
0x409f5  ldc.i4.1
0x409f6  newarr   [mscorlib]System.Object
0x409fb  dup
0x409fc  ldc.i4.0
0x409fd  ldarg.0
0x409fe  stelem.ref
0x409ff  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x40a04  ldloc.1
0x40a05  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmTypeLoadException::.ctor(string, class [mscorlib]System.Exception)
0x40a0a  throw
0x40a0b  ldloc.0
0x40a0c  ret
```
