# Microsoft.Crm.Asynchronous.ImportOperationTransform::GetPublishXml

- ea: `0x1d550`
- end: `0x1d56c`
- name: `Microsoft.Crm.Asynchronous.ImportOperationTransform::GetPublishXml`
- size: `28`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1d450`

## pseudocode

```c

```

## disassembly

```asm
0x1d550  ldstr    aPublishEntitie// "<publish><entities><Entity>{0}</Entity>"...
0x1d555  stloc.0
0x1d556  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1d55b  ldloc.0
0x1d55c  ldc.i4.1
0x1d55d  newarr   [mscorlib]System.Object
0x1d562  dup
0x1d563  ldc.i4.0
0x1d564  ldarg.1
0x1d565  stelem.ref
0x1d566  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x1d56b  ret
```
