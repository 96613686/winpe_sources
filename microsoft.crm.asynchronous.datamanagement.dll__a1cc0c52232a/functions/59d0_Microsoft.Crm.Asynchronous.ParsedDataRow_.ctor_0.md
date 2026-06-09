# Microsoft.Crm.Asynchronous.ParsedDataRow::.ctor_0

- ea: `0x59d0`
- end: `0x5a4d`
- name: `Microsoft.Crm.Asynchronous.ParsedDataRow::.ctor_0`
- size: `125`
- prototype: ``
- caller_count: `7`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x59b0`
- `0x17130`
- `0x17910`
- `0x19d30`
- `0x1b370`
- `0x1c810`
- `0x1fcb0`

## callees

- `0x59d0`
- `0x5a90`
- `0x5ab0`

## pseudocode

```c

```

## disassembly

```asm
0x59d0  ldarg.0
0x59d1  call     instance void [mscorlib]System.Object::.ctor()
0x59d6  ldarg.0
0x59d7  ldarg.1
0x59d8  stfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.ParsedDataRow::_importDataId
0x59dd  ldarg.0
0x59de  ldarg.2
0x59df  stfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.ParsedDataRow::_recordId
0x59e4  ldarg.0
0x59e5  ldarg.3
0x59e6  stfld    class Microsoft.Crm.Asynchronous.ParsedDataObject[] Microsoft.Crm.Asynchronous.ParsedDataRow::_parsedDataObjects
0x59eb  ldarg.0
0x59ec  ldarg.s  4
0x59ee  stfld    bool Microsoft.Crm.Asynchronous.ParsedDataRow::_isExistingRecord
0x59f3  ldarg.0
0x59f4  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::.ctor()
0x59f9  stfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> Microsoft.Crm.Asynchronous.ParsedDataRow::_columnNameToArrayIndexDictionary
0x59fe  ldc.i4.0
0x59ff  stloc.0
0x5a00  br.s     loc_5A41
0x5a02  ldarg.0
0x5a03  ldfld    class Microsoft.Crm.Asynchronous.ParsedDataObject[] Microsoft.Crm.Asynchronous.ParsedDataRow::_parsedDataObjects
0x5a08  ldloc.0
0x5a09  ldelem.ref
0x5a0a  stloc.1
0x5a0b  ldloc.1
0x5a0c  brfalse.s loc_5A3D
0x5a0e  ldloc.1
0x5a0f  ldarg.0
0x5a10  callvirt instance void Microsoft.Crm.Asynchronous.ParsedDataObject::set_ParentRow(class Microsoft.Crm.Asynchronous.ParsedDataRow value)
0x5a15  ldc.i4.m1
0x5a16  stloc.2
0x5a17  ldarg.0
0x5a18  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> Microsoft.Crm.Asynchronous.ParsedDataRow::_columnNameToArrayIndexDictionary
0x5a1d  ldloc.1
0x5a1e  callvirt instance string Microsoft.Crm.Asynchronous.ParsedDataObject::get_ColumnName()
0x5a23  ldloca.s 2
0x5a25  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::TryGetValue(var<u1>, !!T0)
0x5a2a  pop
0x5a2b  ldarg.0
0x5a2c  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> Microsoft.Crm.Asynchronous.ParsedDataRow::_columnNameToArrayIndexDictionary
0x5a31  ldloc.1
0x5a32  callvirt instance string Microsoft.Crm.Asynchronous.ParsedDataObject::get_ColumnName()
0x5a37  ldloc.0
0x5a38  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::set_Item(var<u1>, !!T0)
0x5a3d  ldloc.0
0x5a3e  ldc.i4.1
0x5a3f  add
0x5a40  stloc.0
0x5a41  ldloc.0
0x5a42  ldarg.0
0x5a43  ldfld    class Microsoft.Crm.Asynchronous.ParsedDataObject[] Microsoft.Crm.Asynchronous.ParsedDataRow::_parsedDataObjects
0x5a48  ldlen
0x5a49  conv.i4
0x5a4a  blt.s    loc_5A02
0x5a4c  ret
```
