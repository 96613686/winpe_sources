# Microsoft.Crm.Application.Components.UI.MocaDateTimeUI::RenderDateScroller

- ea: `0x16de0`
- end: `0x16e59`
- name: `Microsoft.Crm.Application.Components.UI.MocaDateTimeUI::RenderDateScroller`
- size: `121`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x16d40`

## callees

- `0x16de0`
- `0x16e60`
- `0x16eb0`

## string_xrefs

- `0x16e13`: `dayComponent`
- `0x16e21`: `monthComponent`
- `0x16e2f`: `yearComponent`

## pseudocode

```c

```

## disassembly

```asm
0x16de0  ldarg.0
0x16de1  call     instance class [mscorlib]System.Collections.Generic.IEnumerable`1<char> Microsoft.Crm.Application.Components.UI.MocaDateTimeUI::GetCultureDependentDatePartCharacterCollection()
0x16de6  ldarg.1
0x16de7  ldstr    aDivClassScroll_0// "<div class=\"scroller dateScroller\">"
0x16dec  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x16df1  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<char>::GetEnumerator()
0x16df6  stloc.0
0x16df7  br.s     loc_16E39
0x16df9  ldloc.0
0x16dfa  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<char>::get_Current()
0x16dff  stloc.1
0x16e00  ldloc.1
0x16e01  ldc.i4.s 0x64
0x16e03  beq.s    loc_16E11
0x16e05  ldloc.1
0x16e06  ldc.i4.s 0x6D
0x16e08  beq.s    loc_16E1F
0x16e0a  ldloc.1
0x16e0b  ldc.i4.s 0x79
0x16e0d  beq.s    loc_16E2D
0x16e0f  br.s     loc_16E39
0x16e11  ldarg.0
0x16e12  ldarg.1
0x16e13  ldstr    aDaycomponent// "dayComponent"
0x16e18  call     instance void Microsoft.Crm.Application.Components.UI.MocaDateTimeUI::RenderScrollerComponent(class [System.Web]System.Web.UI.HtmlTextWriter writer, string componentClass)
0x16e1d  br.s     loc_16E39
0x16e1f  ldarg.0
0x16e20  ldarg.1
0x16e21  ldstr    aMonthcomponent// "monthComponent"
0x16e26  call     instance void Microsoft.Crm.Application.Components.UI.MocaDateTimeUI::RenderScrollerComponent(class [System.Web]System.Web.UI.HtmlTextWriter writer, string componentClass)
0x16e2b  br.s     loc_16E39
0x16e2d  ldarg.0
0x16e2e  ldarg.1
0x16e2f  ldstr    aYearcomponent// "yearComponent"
0x16e34  call     instance void Microsoft.Crm.Application.Components.UI.MocaDateTimeUI::RenderScrollerComponent(class [System.Web]System.Web.UI.HtmlTextWriter writer, string componentClass)
0x16e39  ldloc.0
0x16e3a  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x16e3f  brtrue.s loc_16DF9
0x16e41  leave.s  loc_16E4D
0x16e43  ldloc.0
0x16e44  brfalse.s loc_16E4C
0x16e46  ldloc.0
0x16e47  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x16e4c  endfinally
0x16e4d  ldarg.1
0x16e4e  ldstr    aDiv// "</div>"
0x16e53  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x16e58  ret
```
