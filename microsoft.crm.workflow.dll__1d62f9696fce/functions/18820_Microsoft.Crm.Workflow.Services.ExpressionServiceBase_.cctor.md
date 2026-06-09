# Microsoft.Crm.Workflow.Services.ExpressionServiceBase::.cctor

- ea: `0x18820`
- end: `0x18847`
- name: `Microsoft.Crm.Workflow.Services.ExpressionServiceBase::.cctor`
- size: `39`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## string_xrefs

- `0x18820`: `&lt;hyperlink&gt;\s*&lt;name&gt;(.*?)&lt;/name&gt;\s*&lt;value&gt;(.*?)&lt;/value&gt;\s*&lt;/hyperlink&gt;`

## pseudocode

```c

```

## disassembly

```asm
0x18820  ldstr    aLtHyperlinkGtS// "&lt;hyperlink&gt;\\s*&lt;name&gt;(.*?)&"...
0x18825  ldc.i4.s 0x23
0x18827  call     class [System]System.Text.RegularExpressions.Regex [Microsoft.Crm.Core]Microsoft.Crm.CrmRegexCache::GetRegex(string, valuetype [System]System.Text.RegularExpressions.RegexOptions)
0x1882c  stsfld   class [System]System.Text.RegularExpressions.Regex Microsoft.Crm.Workflow.Services.ExpressionServiceBase::HyperlinkRegex
0x18831  ldstr    asc_38F66// "(?!\")<(.)*?>"
0x18836  call     class [System]System.Text.RegularExpressions.Regex [Microsoft.Crm.Core]Microsoft.Crm.CrmRegexCache::GetRegex(string)
0x1883b  stsfld   class [System]System.Text.RegularExpressions.Regex Microsoft.Crm.Workflow.Services.ExpressionServiceBase::HtmlTagsRegex
0x18840  ldnull
0x18841  stsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<class [mscorlib]System.Type, class [mscorlib]System.Type> Microsoft.Crm.Workflow.Services.ExpressionServiceBase::_crmToXrmWorkflowTypes
0x18846  ret
```
