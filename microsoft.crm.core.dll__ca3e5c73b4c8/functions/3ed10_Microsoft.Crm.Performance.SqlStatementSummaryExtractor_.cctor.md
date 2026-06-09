# Microsoft.Crm.Performance.SqlStatementSummaryExtractor::.cctor

- ea: `0x3ed10`
- end: `0x3ed9a`
- name: `Microsoft.Crm.Performance.SqlStatementSummaryExtractor::.cctor`
- size: `138`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops, installer_update, broker_com_uri`

## callees

- `0x33350`

## string_xrefs

- `0x3ed18`: `DELETE`
- `0x3ed28`: `UPDATE`
- `0x3ed4b`: `delete\s+(?:from\s+)*(?<data>[^\s\(]+)`
- `0x3ed69`: `update\s+(?<data>[^\s\(]+)`

## pseudocode

```c

```

## disassembly

```asm
0x3ed10  ldc.i4.5
0x3ed11  newarr   [mscorlib]System.String
0x3ed16  dup
0x3ed17  ldc.i4.0
0x3ed18  ldstr    aDelete// "DELETE"
0x3ed1d  stelem.ref
0x3ed1e  dup
0x3ed1f  ldc.i4.1
0x3ed20  ldstr    aInsert// "INSERT"
0x3ed25  stelem.ref
0x3ed26  dup
0x3ed27  ldc.i4.2
0x3ed28  ldstr    aUpdate_0// "UPDATE"
0x3ed2d  stelem.ref
0x3ed2e  dup
0x3ed2f  ldc.i4.3
0x3ed30  ldstr    aSelect_1// "SELECT"
0x3ed35  stelem.ref
0x3ed36  dup
0x3ed37  ldc.i4.4
0x3ed38  ldstr    aExec// "EXEC"
0x3ed3d  stelem.ref
0x3ed3e  stsfld   string[] Microsoft.Crm.Performance.SqlStatementSummaryExtractor::statementNames
0x3ed43  ldc.i4.5
0x3ed44  newarr   [System]System.Text.RegularExpressions.Regex
0x3ed49  dup
0x3ed4a  ldc.i4.0
0x3ed4b  ldstr    aDeleteSFromSDa// "delete\\s+(?:from\\s+)*(?<data>[^\\s\\("...
0x3ed50  ldc.i4.s 0xD
0x3ed52  call     class [System]System.Text.RegularExpressions.Regex Microsoft.Crm.CrmRegexCache::GetRegex(string pattern, valuetype [System]System.Text.RegularExpressions.RegexOptions options)
0x3ed57  stelem.ref
0x3ed58  dup
0x3ed59  ldc.i4.1
0x3ed5a  ldstr    aInsertSIntoSDa// "insert\\s+(?:into\\s+)*(?<data>[^\\s\\("...
0x3ed5f  ldc.i4.s 0xD
0x3ed61  call     class [System]System.Text.RegularExpressions.Regex Microsoft.Crm.CrmRegexCache::GetRegex(string pattern, valuetype [System]System.Text.RegularExpressions.RegexOptions options)
0x3ed66  stelem.ref
0x3ed67  dup
0x3ed68  ldc.i4.2
0x3ed69  ldstr    aUpdateSDataS// "update\\s+(?<data>[^\\s\\(]+)"
0x3ed6e  ldc.i4.s 0xD
0x3ed70  call     class [System]System.Text.RegularExpressions.Regex Microsoft.Crm.CrmRegexCache::GetRegex(string pattern, valuetype [System]System.Text.RegularExpressions.RegexOptions options)
0x3ed75  stelem.ref
0x3ed76  dup
0x3ed77  ldc.i4.3
0x3ed78  ldstr    aSelectSSfromSD// "select\\s.+\\sfrom\\s+(?<data>[^\\s\\(]"...
0x3ed7d  ldc.i4.s 0xD
0x3ed7f  call     class [System]System.Text.RegularExpressions.Regex Microsoft.Crm.CrmRegexCache::GetRegex(string pattern, valuetype [System]System.Text.RegularExpressions.RegexOptions options)
0x3ed84  stelem.ref
0x3ed85  dup
0x3ed86  ldc.i4.4
0x3ed87  ldstr    aExecSDataS// "exec\\s+(?<data>[^\\s\\(]+)"
0x3ed8c  ldc.i4.s 0xD
0x3ed8e  call     class [System]System.Text.RegularExpressions.Regex Microsoft.Crm.CrmRegexCache::GetRegex(string pattern, valuetype [System]System.Text.RegularExpressions.RegexOptions options)
0x3ed93  stelem.ref
0x3ed94  stsfld   class [System]System.Text.RegularExpressions.Regex[] Microsoft.Crm.Performance.SqlStatementSummaryExtractor::regexes
0x3ed99  ret
```
