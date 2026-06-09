# Microsoft.Crm.ApplicationConfig::IsTokenCheckIgnored

- ea: `0x18ba0`
- end: `0x18bbc`
- name: `Microsoft.Crm.ApplicationConfig::IsTokenCheckIgnored`
- size: `28`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18fb0`

## string_xrefs

- `0x18ba0`: `IgnoreTokenCheck`

## pseudocode

```c

```

## disassembly

```asm
0x18ba0  ldstr    aIgnoretokenche// "IgnoreTokenCheck"
0x18ba5  ldc.i4.0
0x18ba6  box      [mscorlib]System.Boolean
0x18bab  ldarg.0
0x18bac  call     object Microsoft.Crm.ApplicationConfig::Retrieve(string propertyName, object defaultValue, valuetype [mscorlib]System.Guid organizationId)
0x18bb1  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x18bb6  call     bool [mscorlib]System.Convert::ToBoolean(object, class [mscorlib]System.IFormatProvider)
0x18bbb  ret
```
