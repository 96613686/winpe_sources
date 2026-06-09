# Microsoft.Crm.SpreadsheetMLParser::ValidateHeaderColumns

- ea: `0x23b70`
- end: `0x23b95`
- name: `Microsoft.Crm.SpreadsheetMLParser::ValidateHeaderColumns`
- size: `37`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x23b70`
- `0x23ba0`
- `0x23c30`

## string_xrefs

- `0x23b7d`: `SpreadsheetML file has not been initialized`

## pseudocode

```c

```

## disassembly

```asm
0x23b70  ldarg.0
0x23b71  ldfld    string Microsoft.Crm.SpreadsheetMLParser::_content
0x23b76  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x23b7b  brfalse.s loc_23B88
0x23b7d  ldstr    aSpreadsheetmlF// "SpreadsheetML file has not been initial"...
0x23b82  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0x23b87  throw
0x23b88  ldarg.0
0x23b89  call     instance void Microsoft.Crm.SpreadsheetMLParser::CheckForEmptyFirstRow()
0x23b8e  ldarg.0
0x23b8f  call     instance void Microsoft.Crm.SpreadsheetMLParser::CheckForEmptyHeaderColumn()
0x23b94  ret
```
