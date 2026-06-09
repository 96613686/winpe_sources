# Microsoft.Crm.Application.Components.UI.Lookup::RenderTouchLookup

- ea: `0x1f810`
- end: `0x1f9e7`
- name: `Microsoft.Crm.Application.Components.UI.Lookup::RenderTouchLookup`
- size: `471`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1f420`

## callees

- `0x1f300`
- `0x1f810`
- `0x23c20`
- `0x24120`
- `0x24210`
- `0x24280`

## string_xrefs

- `0x1f951`: `comboBox`

## pseudocode

```c

```

## disassembly

```asm
0x1f810  ldarg.1
0x1f811  ldc.i4.5
0x1f812  newarr   [mscorlib]System.String
0x1f817  dup
0x1f818  ldc.i4.0
0x1f819  ldstr    aDivId// "<div id=\""
0x1f81e  stelem.ref
0x1f81f  dup
0x1f820  ldc.i4.1
0x1f821  ldarg.0
0x1f822  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x1f827  stelem.ref
0x1f828  dup
0x1f829  ldc.i4.2
0x1f82a  ldstr    aClass// "\" class=\""
0x1f82f  stelem.ref
0x1f830  dup
0x1f831  ldc.i4.3
0x1f832  ldstr    aTouchlookupcon// "touchLookupControl"
0x1f837  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string)
0x1f83c  stelem.ref
0x1f83d  dup
0x1f83e  ldc.i4.4
0x1f83f  ldstr    aMsCrmLookup// " \"ms-crm-Lookup\""
0x1f844  stelem.ref
0x1f845  call     string [mscorlib]System.String::Concat(string[])
0x1f84a  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x1f84f  ldarg.1
0x1f850  ldstr    aTabindex// "tabindex"
0x1f855  ldstr    a0// "0"
0x1f85a  ldc.i4.0
0x1f85b  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x1f860  ldarg.0
0x1f861  call     instance bool Microsoft.Crm.Application.Components.UI.Lookup::get_IsDisplayOnlyLookup()
0x1f866  brtrue.s loc_1F878
0x1f868  ldarg.0
0x1f869  callvirt instance bool Microsoft.Crm.Application.Components.UI.CrmUIControl::get_ReadOnly()
0x1f86e  brtrue.s loc_1F878
0x1f870  ldarg.0
0x1f871  callvirt instance bool Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_Disabled()
0x1f876  brfalse.s loc_1F888
0x1f878  ldarg.0
0x1f879  ldstr    aLookupdisabled// "lookupdisabled"
0x1f87e  ldstr    aTrue// "true"
0x1f883  callvirt instance void Microsoft.Crm.Application.Components.UI.CrmUIControl::AddExpando(string name, string value)
0x1f888  ldarg.1
0x1f889  ldarg.0
0x1f88a  callvirt instance string Microsoft.Crm.Application.Components.UI.CrmUIControl::get_Expandos()
0x1f88f  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x1f894  ldarg.1
0x1f895  ldstr    asc_2B7B6// ">"
0x1f89a  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x1f89f  ldarg.1
0x1f8a0  ldc.i4.5
0x1f8a1  newarr   [mscorlib]System.String
0x1f8a6  dup
0x1f8a7  ldc.i4.0
0x1f8a8  ldstr    aDivClass// "<div class=\""
0x1f8ad  stelem.ref
0x1f8ae  dup
0x1f8af  ldc.i4.1
0x1f8b0  ldstr    aControlheader// "controlHeader"
0x1f8b5  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string)
0x1f8ba  stelem.ref
0x1f8bb  dup
0x1f8bc  ldc.i4.2
0x1f8bd  ldstr    aDivSpanClass// "\"><div><span class=\""
0x1f8c2  stelem.ref
0x1f8c3  dup
0x1f8c4  ldc.i4.3
0x1f8c5  ldstr    aControldisplay// "controlDisplay"
0x1f8ca  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string)
0x1f8cf  stelem.ref
0x1f8d0  dup
0x1f8d1  ldc.i4.4
0x1f8d2  ldstr    asc_42682// "\">"
0x1f8d7  stelem.ref
0x1f8d8  call     string [mscorlib]System.String::Concat(string[])
0x1f8dd  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x1f8e2  ldarg.1
0x1f8e3  ldstr    aSpanDivDiv// "</span></div></div>"
0x1f8e8  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x1f8ed  ldarg.1
0x1f8ee  ldstr    aDivClass// "<div class=\""
0x1f8f3  ldstr    aEditablepanel// "editablePanel"
0x1f8f8  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string)
0x1f8fd  ldstr    aStyleDisplayNo_1// "\" style=\"display:none\">"
0x1f902  call     string [mscorlib]System.String::Concat(string, string, string)
0x1f907  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x1f90c  ldarg.1
0x1f90d  ldstr    aDivClass// "<div class=\""
0x1f912  ldstr    aLookuppanel// "lookupPanel"
0x1f917  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string)
0x1f91c  ldstr    asc_42682// "\">"
0x1f921  call     string [mscorlib]System.String::Concat(string, string, string)
0x1f926  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x1f92b  ldarg.1
0x1f92c  ldc.i4.5
0x1f92d  newarr   [mscorlib]System.String
0x1f932  dup
0x1f933  ldc.i4.0
0x1f934  ldstr    aDivClass// "<div class=\""
0x1f939  stelem.ref
0x1f93a  dup
0x1f93b  ldc.i4.1
0x1f93c  ldstr    aLookupentityse// "lookupEntitySelector"
0x1f941  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string)
0x1f946  stelem.ref
0x1f947  dup
0x1f948  ldc.i4.2
0x1f949  ldstr    aSelectClass// "\"> <select class=\""
0x1f94e  stelem.ref
0x1f94f  dup
0x1f950  ldc.i4.3
0x1f951  ldstr    aCombobox// "comboBox"
0x1f956  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string)
0x1f95b  stelem.ref
0x1f95c  dup
0x1f95d  ldc.i4.4
0x1f95e  ldstr    aSelectDiv// "\"></select></div>"
0x1f963  stelem.ref
0x1f964  call     string [mscorlib]System.String::Concat(string[])
0x1f969  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x1f96e  ldarg.1
0x1f96f  ldc.i4.5
0x1f970  newarr   [mscorlib]System.String
0x1f975  dup
0x1f976  ldc.i4.0
0x1f977  ldstr    aDivClass// "<div class=\""
0x1f97c  stelem.ref
0x1f97d  dup
0x1f97e  ldc.i4.1
0x1f97f  ldstr    aLookupsearchfi// "lookupSearchField"
0x1f984  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string)
0x1f989  stelem.ref
0x1f98a  dup
0x1f98b  ldc.i4.2
0x1f98c  ldstr    aInputClass// "\"> <input class=\""
0x1f991  stelem.ref
0x1f992  dup
0x1f993  ldc.i4.3
0x1f994  ldstr    aTextbox// "textbox"
0x1f999  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string)
0x1f99e  stelem.ref
0x1f99f  dup
0x1f9a0  ldc.i4.4
0x1f9a1  ldstr    aDiv_6// "\"></div>"
0x1f9a6  stelem.ref
0x1f9a7  call     string [mscorlib]System.String::Concat(string[])
0x1f9ac  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x1f9b1  ldarg.1
0x1f9b2  ldstr    aDiv// "</div>"
0x1f9b7  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x1f9bc  ldarg.1
0x1f9bd  ldstr    aDivClass// "<div class=\""
0x1f9c2  ldstr    aPartylist// "partyList"
0x1f9c7  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string)
0x1f9cc  ldstr    aDiv_6// "\"></div>"
0x1f9d1  call     string [mscorlib]System.String::Concat(string, string, string)
0x1f9d6  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x1f9db  ldarg.1
0x1f9dc  ldstr    aDivDiv// "</div></div>"
0x1f9e1  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x1f9e6  ret
```
