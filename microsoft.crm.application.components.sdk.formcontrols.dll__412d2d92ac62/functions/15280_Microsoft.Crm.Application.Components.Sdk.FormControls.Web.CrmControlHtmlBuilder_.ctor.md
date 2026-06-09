# Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmControlHtmlBuilder::.ctor

- ea: `0x15280`
- end: `0x152cb`
- name: `Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmControlHtmlBuilder::.ctor`
- size: `75`
- prototype: ``
- caller_count: `5`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x17010`
- `0x17180`
- `0x17230`
- `0x172f0`
- `0x174d0`

## callees

- `0x15280`
- `0x152e0`

## string_xrefs

- `0x1529c`: `htmlTextWriter`

## pseudocode

```c

```

## disassembly

```asm
0x15280  ldarg.0
0x15281  call     instance void [mscorlib]System.Object::.ctor()
0x15286  ldarg.1
0x15287  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x1528c  brfalse.s loc_15299
0x1528e  ldstr    aHtmltagname// "htmlTagName"
0x15293  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x15298  throw
0x15299  ldarg.2
0x1529a  brtrue.s loc_152A7
0x1529c  ldstr    aHtmltextwriter// "htmlTextWriter"
0x152a1  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x152a6  throw
0x152a7  ldarg.0
0x152a8  ldarg.1
0x152a9  callvirt instance string [mscorlib]System.String::ToLower()
0x152ae  stfld    string Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmControlHtmlBuilder::htmlTagName
0x152b3  ldarg.0
0x152b4  ldarg.2
0x152b5  stfld    class [System.Web]System.Web.UI.HtmlTextWriter Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmControlHtmlBuilder::htmlTextWriter
0x152ba  ldarg.0
0x152bb  call     class [mscorlib]System.StringComparer [mscorlib]System.StringComparer::get_OrdinalIgnoreCase()
0x152c0  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::.ctor(class [mscorlib]System.Collections.Generic.IEqualityComparer`1<var<u1>>)
0x152c5  call     instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmControlHtmlBuilder::set_Attributes(class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> value)
0x152ca  ret
```
