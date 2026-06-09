# Microsoft.Crm.Sdk.RequestBuilderCacheBase`1::ConvertKeyToString

- ea: `0x5650`
- end: `0x5678`
- name: `Microsoft.Crm.Sdk.RequestBuilderCacheBase`1::ConvertKeyToString`
- size: `40`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x55c0`
- `0x55d0`

## pseudocode

```c

```

## disassembly

```asm
0x5650  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x5655  ldstr    a01// "{0},{1}"
0x565a  ldc.i4.2
0x565b  newarr   [mscorlib]System.Object
0x5660  dup
0x5661  ldc.i4.0
0x5662  ldarg.1
0x5663  callvirt instance string Microsoft.Crm.Sdk.RequestBuilderKey::get_Namespace()
0x5668  stelem.ref
0x5669  dup
0x566a  ldc.i4.1
0x566b  ldarg.1
0x566c  callvirt instance string Microsoft.Crm.Sdk.RequestBuilderKey::get_RequestName()
0x5671  stelem.ref
0x5672  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x5677  ret
```
