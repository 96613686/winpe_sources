# Microsoft.Crm.SpreadsheetMLParser::CheckForEmptyFirstRow

- ea: `0x23c30`
- end: `0x23c7e`
- name: `Microsoft.Crm.SpreadsheetMLParser::CheckForEmptyFirstRow`
- size: `78`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x23b70`

## callees

- `0x23700`
- `0x23c30`
- `0x23f10`

## string_xrefs

- `0x23c38`: `SpreadsheetML file has not been initialized`

## pseudocode

```c

```

## disassembly

```asm
0x23c30  ldarg.0
0x23c31  ldfld    string Microsoft.Crm.SpreadsheetMLParser::_content
0x23c36  brtrue.s loc_23C43
0x23c38  ldstr    aSpreadsheetmlF// "SpreadsheetML file has not been initial"...
0x23c3d  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0x23c42  throw
0x23c43  ldnull
0x23c44  stloc.0
0x23c45  ldarg.0
0x23c46  call     instance class Microsoft.Crm.SpreadsheetMLRow Microsoft.Crm.SpreadsheetMLParser::FetchFirstRow()
0x23c4b  stloc.0
0x23c4c  leave.s  loc_23C60
0x23c4e  pop
0x23c4f  ldc.i4   0x80040351
0x23c54  ldc.i4.0
0x23c55  newarr   [mscorlib]System.Object
0x23c5a  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0x23c5f  throw
0x23c60  ldloc.0
0x23c61  brfalse.s loc_23C6C
0x23c63  ldloc.0
0x23c64  callvirt instance int32 Microsoft.Crm.SpreadsheetMLRow::get_MaxCellIndex()
0x23c69  ldc.i4.0
0x23c6a  bgt.s    loc_23C7D
0x23c6c  ldc.i4   0x80040366
0x23c71  ldc.i4.0
0x23c72  newarr   [mscorlib]System.Object
0x23c77  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0x23c7c  throw
0x23c7d  ret
```
