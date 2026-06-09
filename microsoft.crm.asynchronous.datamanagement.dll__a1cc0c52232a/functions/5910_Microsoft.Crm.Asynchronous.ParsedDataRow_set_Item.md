# Microsoft.Crm.Asynchronous.ParsedDataRow::set_Item

- ea: `0x5910`
- end: `0x5981`
- name: `Microsoft.Crm.Asynchronous.ParsedDataRow::set_Item`
- size: `113`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18840`
- `0x1ab90`
- `0x1b470`
- `0x1c810`

## callees

- `0x5910`
- `0x5a90`
- `0x5ab0`

## pseudocode

```c

```

## disassembly

```asm
0x5910  ldarg.2
0x5911  brtrue.s loc_593D
0x5913  ldarg.0
0x5914  ldfld    class Microsoft.Crm.Asynchronous.ParsedDataObject[] Microsoft.Crm.Asynchronous.ParsedDataRow::_parsedDataObjects
0x5919  ldarg.1
0x591a  ldelem.ref
0x591b  stloc.0
0x591c  ldloc.0
0x591d  brfalse.s loc_5980
0x591f  ldloc.0
0x5920  callvirt instance string Microsoft.Crm.Asynchronous.ParsedDataObject::get_ColumnName()
0x5925  stloc.1
0x5926  ldarg.0
0x5927  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> Microsoft.Crm.Asynchronous.ParsedDataRow::_columnNameToArrayIndexDictionary
0x592c  ldloc.1
0x592d  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Remove(var<u1>)
0x5932  pop
0x5933  ldarg.0
0x5934  ldfld    class Microsoft.Crm.Asynchronous.ParsedDataObject[] Microsoft.Crm.Asynchronous.ParsedDataRow::_parsedDataObjects
0x5939  ldarg.1
0x593a  ldarg.2
0x593b  stelem.ref
0x593c  ret
0x593d  ldarg.1
0x593e  ldarg.0
0x593f  ldfld    class Microsoft.Crm.Asynchronous.ParsedDataObject[] Microsoft.Crm.Asynchronous.ParsedDataRow::_parsedDataObjects
0x5944  ldlen
0x5945  conv.i4
0x5946  bge.s    loc_5980
0x5948  ldc.i4.m1
0x5949  stloc.2
0x594a  ldarg.0
0x594b  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> Microsoft.Crm.Asynchronous.ParsedDataRow::_columnNameToArrayIndexDictionary
0x5950  ldarg.2
0x5951  callvirt instance string Microsoft.Crm.Asynchronous.ParsedDataObject::get_ColumnName()
0x5956  ldloca.s 2
0x5958  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::TryGetValue(var<u1>, !!T0)
0x595d  pop
0x595e  ldarg.0
0x595f  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> Microsoft.Crm.Asynchronous.ParsedDataRow::_columnNameToArrayIndexDictionary
0x5964  ldarg.2
0x5965  callvirt instance string Microsoft.Crm.Asynchronous.ParsedDataObject::get_ColumnName()
0x596a  ldarg.1
0x596b  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::set_Item(var<u1>, !!T0)
0x5970  ldarg.0
0x5971  ldfld    class Microsoft.Crm.Asynchronous.ParsedDataObject[] Microsoft.Crm.Asynchronous.ParsedDataRow::_parsedDataObjects
0x5976  ldarg.1
0x5977  ldarg.2
0x5978  stelem.ref
0x5979  ldarg.2
0x597a  ldarg.0
0x597b  callvirt instance void Microsoft.Crm.Asynchronous.ParsedDataObject::set_ParentRow(class Microsoft.Crm.Asynchronous.ParsedDataRow value)
0x5980  ret
```
