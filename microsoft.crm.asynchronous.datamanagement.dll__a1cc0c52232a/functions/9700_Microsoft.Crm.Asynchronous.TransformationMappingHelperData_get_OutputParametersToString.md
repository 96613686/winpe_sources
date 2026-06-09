# Microsoft.Crm.Asynchronous.TransformationMappingHelperData::get_OutputParametersToString

- ea: `0x9700`
- end: `0x970d`
- name: `Microsoft.Crm.Asynchronous.TransformationMappingHelperData::get_OutputParametersToString`
- size: `13`
- prototype: ``
- caller_count: `8`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x9c10`
- `0x9d80`
- `0xa070`
- `0xa600`
- `0x17910`
- `0x18840`
- `0x18f40`
- `0x19370`

## callees

- `0x9790`

## pseudocode

```c

```

## disassembly

```asm
0x9700  ldarg.0
0x9701  ldarg.0
0x9702  ldfld    class [mscorlib]System.Collections.Generic.List`1<string> Microsoft.Crm.Asynchronous.TransformationMappingHelperData::_outputColumns
0x9707  call     instance string Microsoft.Crm.Asynchronous.TransformationMappingHelperData::GetStringRepresentation(class [mscorlib]System.Collections.Generic.List`1<string> inputColumns)
0x970c  ret
```
