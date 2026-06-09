# Microsoft.Crm.Asynchronous.DatabaseTuningManager::PrepareConfigurationXml

- ea: `0x2060`
- end: `0x208d`
- name: `Microsoft.Crm.Asynchronous.DatabaseTuningManager::PrepareConfigurationXml`
- size: `45`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1f60`

## pseudocode

```c

```

## disassembly

```asm
0x2060  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x2065  ldarg.0
0x2066  ldfld    string Microsoft.Crm.Asynchronous.DatabaseTuningManager::_dtaTemplateXml
0x206b  ldc.i4.3
0x206c  newarr   [mscorlib]System.Object
0x2071  dup
0x2072  ldc.i4.0
0x2073  ldarg.0
0x2074  ldfld    string Microsoft.Crm.Asynchronous.DatabaseTuningManager::_sqlServer
0x2079  stelem.ref
0x207a  dup
0x207b  ldc.i4.1
0x207c  ldarg.0
0x207d  ldfld    string Microsoft.Crm.Asynchronous.DatabaseTuningManager::_databaseName
0x2082  stelem.ref
0x2083  dup
0x2084  ldc.i4.2
0x2085  ldarg.1
0x2086  stelem.ref
0x2087  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x208c  ret
```
