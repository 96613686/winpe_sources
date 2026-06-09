# Microsoft.Crm.Common.Application.Commands.ApplicationCommand::RetrieveKBArticleContent

- ea: `0x1c40`
- end: `0x1ca7`
- name: `Microsoft.Crm.Common.Application.Commands.ApplicationCommand::RetrieveKBArticleContent`
- size: `103`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0xc70`

## callees

- `0x1c40`

## pseudocode

```c

```

## disassembly

```asm
0x1c40  ldc.i4.1
0x1c41  newarr   [mscorlib]System.String
0x1c46  dup
0x1c47  ldc.i4.0
0x1c48  ldstr    aContent// "content"
0x1c4d  stelem.ref
0x1c4e  stloc.0
0x1c4f  ldstr    aKbarticle// "kbarticle"
0x1c54  ldarg.0
0x1c55  ldloc.0
0x1c56  ldarg.1
0x1c57  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.DataSource::Retrieve(string, valuetype [mscorlib]System.Guid, string[], class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1c5c  ldstr    aContent// "content"
0x1c61  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x1c66  castclass [mscorlib]System.String
0x1c6b  stloc.1
0x1c6c  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentUICulture()
0x1c71  callvirt instance class [mscorlib]System.Globalization.TextInfo [mscorlib]System.Globalization.CultureInfo::get_TextInfo()
0x1c76  callvirt instance bool [mscorlib]System.Globalization.TextInfo::get_IsRightToLeft()
0x1c7b  brfalse.s loc_1CA0
0x1c7d  ldstr    aTextAlignRight// "text-align:right;direction:rtl;"
0x1c82  stloc.2
0x1c83  ldstr    aStyleSBodySSTd// "(<style>\\s*body\\s*,\\s*td\\s*)(\\{)"
0x1c88  ldc.i4.1
0x1c89  newobj   instance void [System]System.Text.RegularExpressions.Regex::.ctor(string, valuetype [System]System.Text.RegularExpressions.RegexOptions)
0x1c8e  ldloc.1
0x1c8f  ldstr    a12// "$1$2"
0x1c94  ldloc.2
0x1c95  call     string [mscorlib]System.String::Concat(string, string)
0x1c9a  callvirt instance string [System]System.Text.RegularExpressions.Regex::Replace(string, string)
0x1c9f  stloc.1
0x1ca0  ldloc.1
0x1ca1  call     string [Microsoft.Crm.SafeHtml]Microsoft.Crm.SafeHtml::GetSafeHtml(string)
0x1ca6  ret
```
