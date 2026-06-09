# Microsoft.Crm.Performance.SqlStatementComplexityExtractor::.cctor

- ea: `0x3ee20`
- end: `0x3ee86`
- name: `Microsoft.Crm.Performance.SqlStatementComplexityExtractor::.cctor`
- size: `102`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops, installer_update, broker_com_uri`

## callees

- `0x33350`

## string_xrefs

- `0x3ee37`: `\s*update\s+`
- `0x3ee55`: `\s*delete\s+`

## pseudocode

```c

```

## disassembly

```asm
0x3ee20  ldc.i4.6
0x3ee21  newarr   [System]System.Text.RegularExpressions.Regex
0x3ee26  dup
0x3ee27  ldc.i4.0
0x3ee28  ldstr    aSSelectS// "\\s*select\\s+"
0x3ee2d  ldc.i4.s 9
0x3ee2f  call     class [System]System.Text.RegularExpressions.Regex Microsoft.Crm.CrmRegexCache::GetRegex(string pattern, valuetype [System]System.Text.RegularExpressions.RegexOptions options)
0x3ee34  stelem.ref
0x3ee35  dup
0x3ee36  ldc.i4.1
0x3ee37  ldstr    aSUpdateS// "\\s*update\\s+"
0x3ee3c  ldc.i4.s 9
0x3ee3e  call     class [System]System.Text.RegularExpressions.Regex Microsoft.Crm.CrmRegexCache::GetRegex(string pattern, valuetype [System]System.Text.RegularExpressions.RegexOptions options)
0x3ee43  stelem.ref
0x3ee44  dup
0x3ee45  ldc.i4.2
0x3ee46  ldstr    aSInsertS// "\\s*insert\\s+"
0x3ee4b  ldc.i4.s 9
0x3ee4d  call     class [System]System.Text.RegularExpressions.Regex Microsoft.Crm.CrmRegexCache::GetRegex(string pattern, valuetype [System]System.Text.RegularExpressions.RegexOptions options)
0x3ee52  stelem.ref
0x3ee53  dup
0x3ee54  ldc.i4.3
0x3ee55  ldstr    aSDeleteS// "\\s*delete\\s+"
0x3ee5a  ldc.i4.s 9
0x3ee5c  call     class [System]System.Text.RegularExpressions.Regex Microsoft.Crm.CrmRegexCache::GetRegex(string pattern, valuetype [System]System.Text.RegularExpressions.RegexOptions options)
0x3ee61  stelem.ref
0x3ee62  dup
0x3ee63  ldc.i4.4
0x3ee64  ldstr    aSJoinS// "\\s+join\\s+"
0x3ee69  ldc.i4.s 9
0x3ee6b  call     class [System]System.Text.RegularExpressions.Regex Microsoft.Crm.CrmRegexCache::GetRegex(string pattern, valuetype [System]System.Text.RegularExpressions.RegexOptions options)
0x3ee70  stelem.ref
0x3ee71  dup
0x3ee72  ldc.i4.5
0x3ee73  ldstr    aSExecS// "\\s*exec\\s+"
0x3ee78  ldc.i4.s 9
0x3ee7a  call     class [System]System.Text.RegularExpressions.Regex Microsoft.Crm.CrmRegexCache::GetRegex(string pattern, valuetype [System]System.Text.RegularExpressions.RegexOptions options)
0x3ee7f  stelem.ref
0x3ee80  stsfld   class [System]System.Text.RegularExpressions.Regex[] Microsoft.Crm.Performance.SqlStatementComplexityExtractor::regexes
0x3ee85  ret
```
