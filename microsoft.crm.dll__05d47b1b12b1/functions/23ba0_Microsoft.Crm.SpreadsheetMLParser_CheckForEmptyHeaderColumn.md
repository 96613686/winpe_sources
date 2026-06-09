# Microsoft.Crm.SpreadsheetMLParser::CheckForEmptyHeaderColumn

- ea: `0x23ba0`
- end: `0x23c2b`
- name: `Microsoft.Crm.SpreadsheetMLParser::CheckForEmptyHeaderColumn`
- size: `139`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x23b70`

## callees

- `0x23700`
- `0x23ba0`
- `0x23f10`
- `0x23f80`

## string_xrefs

- `0x23bad`: `SpreadsheetML file has not been initialized`

## pseudocode

```c

```

## disassembly

```asm
0x23ba0  ldarg.0
0x23ba1  ldfld    string Microsoft.Crm.SpreadsheetMLParser::_content
0x23ba6  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x23bab  brfalse.s loc_23BB8
0x23bad  ldstr    aSpreadsheetmlF// "SpreadsheetML file has not been initial"...
0x23bb2  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0x23bb7  throw
0x23bb8  ldnull
0x23bb9  stloc.0
0x23bba  ldarg.0
0x23bbb  call     instance class Microsoft.Crm.SpreadsheetMLRow Microsoft.Crm.SpreadsheetMLParser::FetchFirstRow()
0x23bc0  stloc.0
0x23bc1  leave.s  loc_23BD5
0x23bc3  pop
0x23bc4  ldc.i4   0x80040351
0x23bc9  ldc.i4.0
0x23bca  newarr   [mscorlib]System.Object
0x23bcf  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0x23bd4  throw
0x23bd5  ldloc.0
0x23bd6  brfalse.s loc_23BE1
0x23bd8  ldloc.0
0x23bd9  callvirt instance int32 Microsoft.Crm.SpreadsheetMLRow::get_MaxCellIndex()
0x23bde  ldc.i4.0
0x23bdf  bgt.s    loc_23BF2
0x23be1  ldc.i4   0x80040366
0x23be6  ldc.i4.0
0x23be7  newarr   [mscorlib]System.Object
0x23bec  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0x23bf1  throw
0x23bf2  ldc.i4.0
0x23bf3  stloc.1
0x23bf4  ldc.i4.0
0x23bf5  stloc.2
0x23bf6  br.s     loc_23C21
0x23bf8  ldloc.2
0x23bf9  ldc.i4.1
0x23bfa  add
0x23bfb  stloc.3
0x23bfc  ldloc.0
0x23bfd  ldloc.3
0x23bfe  callvirt instance class Microsoft.Crm.SpreadsheetMLCell Microsoft.Crm.SpreadsheetMLRow::GetCellAtIndex(int32 index)
0x23c03  brtrue.s loc_23C09
0x23c05  ldc.i4.1
0x23c06  stloc.1
0x23c07  br.s     loc_23C1D
0x23c09  ldloc.1
0x23c0a  brfalse.s loc_23C1D
0x23c0c  ldc.i4   0x80040337
0x23c11  ldc.i4.0
0x23c12  newarr   [mscorlib]System.Object
0x23c17  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0x23c1c  throw
0x23c1d  ldloc.2
0x23c1e  ldc.i4.1
0x23c1f  add
0x23c20  stloc.2
0x23c21  ldloc.2
0x23c22  ldloc.0
0x23c23  callvirt instance int32 Microsoft.Crm.SpreadsheetMLRow::get_MaxCellIndex()
0x23c28  blt.s    loc_23BF8
0x23c2a  ret
```
