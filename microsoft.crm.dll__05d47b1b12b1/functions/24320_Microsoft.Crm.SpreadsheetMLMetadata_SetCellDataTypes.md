# Microsoft.Crm.SpreadsheetMLMetadata::SetCellDataTypes

- ea: `0x24320`
- end: `0x24370`
- name: `Microsoft.Crm.SpreadsheetMLMetadata::SetCellDataTypes`
- size: `80`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x24180`

## callees

- `0x24320`

## string_xrefs

- `0x2433d`: `each of the values in this comma separated list should be a valid SpreadsheetMLCellType`

## pseudocode

```c

```

## disassembly

```asm
0x24320  ldarg.1
0x24321  ldstr    asc_6B1E0// ","
0x24326  call     string[] [Microsoft.Crm.Core]Microsoft.Crm.CrmRegexCache::Split(string, string)
0x2432b  stloc.0
0x2432c  ldc.i4.0
0x2432d  stloc.1
0x2432e  br.s     loc_24357
0x24330  ldloc.0
0x24331  ldloc.1
0x24332  ldelem.ref
0x24333  ldloca.s 2
0x24335  call     T0x2B00001A
0x2433a  brtrue.s loc_24347
0x2433c  ldc.i4.0
0x2433d  ldstr    aEachOfTheValue_0// "each of the values in this comma separa"...
0x24342  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x24347  ldarg.0
0x24348  ldfld    class [mscorlib]System.Collections.Generic.List`1<valuetype Microsoft.Crm.SpreadsheetMLCellType> Microsoft.Crm.SpreadsheetMLMetadata::_cellDataTypes
0x2434d  ldloc.2
0x2434e  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype Microsoft.Crm.SpreadsheetMLCellType>::Add(var<u1>)
0x24353  ldloc.1
0x24354  ldc.i4.1
0x24355  add
0x24356  stloc.1
0x24357  ldloc.1
0x24358  ldloc.0
0x24359  ldlen
0x2435a  conv.i4
0x2435b  blt.s    loc_24330
0x2435d  leave.s  loc_2436F
0x2435f  callvirt instance string [mscorlib]System.Exception::get_Message()
0x24364  ldc.i4   0x8004F601
0x24369  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x2436e  throw
0x2436f  ret
```
