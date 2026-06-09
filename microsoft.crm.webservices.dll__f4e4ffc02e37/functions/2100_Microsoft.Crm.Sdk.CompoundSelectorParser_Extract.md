# Microsoft.Crm.Sdk.CompoundSelectorParser::Extract

- ea: `0x2100`
- end: `0x2122`
- name: `Microsoft.Crm.Sdk.CompoundSelectorParser::Extract`
- size: `34`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1500`
- `0x1520`

## pseudocode

```c

```

## disassembly

```asm
0x2100  ldarg.1
0x2101  call     class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.DynamicEntity Microsoft.Crm.Sdk.ParserHelper::ExtractEntity(object targetField)
0x2106  stloc.0
0x2107  ldarg.1
0x2108  ldstr    aChildentities// "ChildEntities"
0x210d  call     class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.DynamicEntity[] Microsoft.Crm.Sdk.ParserHelper::ExtractEntityArray(object targetField, string fieldName)
0x2112  stloc.1
0x2113  ldc.i4.2
0x2114  newarr   [mscorlib]System.Object
0x2119  dup
0x211a  ldc.i4.0
0x211b  ldloc.0
0x211c  stelem.ref
0x211d  dup
0x211e  ldc.i4.1
0x211f  ldloc.1
0x2120  stelem.ref
0x2121  ret
```
