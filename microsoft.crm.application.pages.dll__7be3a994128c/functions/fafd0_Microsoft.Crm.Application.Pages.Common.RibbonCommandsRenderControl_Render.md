# Microsoft.Crm.Application.Pages.Common.RibbonCommandsRenderControl::Render

- ea: `0xfafd0`
- end: `0xfb117`
- name: `Microsoft.Crm.Application.Pages.Common.RibbonCommandsRenderControl::Render`
- size: `327`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0xfafd0`

## string_xrefs

- `0xfaffc`: `if(!Mscrm.RibbonCommands) Mscrm.RibbonCommands = {};`
- `0xfb007`: `if(!Mscrm.RibbonCommands.commands) Mscrm.RibbonCommands.commands = {};`
- `0xfb012`: `if(!Mscrm.RibbonCommands.commands[{0}]) Mscrm.RibbonCommands.commands[{0}] = {{}};`
- `0xfb01e`: `var c = Mscrm.RibbonCommands.commands[{0}];`
- `0xfb080`: `if(!Mscrm.RibbonCommands.enableRules) Mscrm.RibbonCommands.enableRules = {};`
- `0xfb08b`: `if(!Mscrm.RibbonCommands.enableRules[{0}]) Mscrm.RibbonCommands.enableRules[{0}] = {{}};`
- `0xfb097`: `var e = Mscrm.RibbonCommands.enableRules[{0}];`

## pseudocode

```c

```

## disassembly

```asm
0xfafd0  ldarg.0
0xfafd1  ldfld    string Microsoft.Crm.Application.Pages.Common.RibbonCommandsRenderControl::_entityLogicalName
0xfafd6  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xfafdb  brtrue.s loc_FAFEA
0xfafdd  ldarg.0
0xfafde  ldfld    string Microsoft.Crm.Application.Pages.Common.RibbonCommandsRenderControl::_entityLogicalName
0xfafe3  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmJavaScriptEncode(string)
0xfafe8  br.s     loc_FAFEF
0xfafea  ldstr    aNull_0// "null"
0xfafef  stloc.0
0xfaff0  ldarg.1
0xfaff1  ldstr    aTypeRegisterna_0// "Type.registerNamespace('Mscrm');"
0xfaff6  callvirt instance void [mscorlib]System.IO.TextWriter::WriteLine(string)
0xfaffb  ldarg.1
0xfaffc  ldstr    aIfMscrmRibbonc_0// "if(!Mscrm.RibbonCommands) Mscrm.RibbonC"...
0xfb001  callvirt instance void [mscorlib]System.IO.TextWriter::WriteLine(string)
0xfb006  ldarg.1
0xfb007  ldstr    aIfMscrmRibbonc_1// "if(!Mscrm.RibbonCommands.commands) Mscr"...
0xfb00c  callvirt instance void [mscorlib]System.IO.TextWriter::WriteLine(string)
0xfb011  ldarg.1
0xfb012  ldstr    aIfMscrmRibbonc_2// "if(!Mscrm.RibbonCommands.commands[{0}])"...
0xfb017  ldloc.0
0xfb018  callvirt instance void [mscorlib]System.IO.TextWriter::WriteLine(string, object)
0xfb01d  ldarg.1
0xfb01e  ldstr    aVarCMscrmRibbo// "var c = Mscrm.RibbonCommands.commands[{"...
0xfb023  ldloc.0
0xfb024  callvirt instance void [mscorlib]System.IO.TextWriter::WriteLine(string, object)
0xfb029  ldarg.0
0xfb02a  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonCommandDefinition> Microsoft.Crm.Application.Pages.Common.RibbonCommandsRenderControl::_commands
0xfb02f  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonCommandDefinition>::get_Keys()
0xfb034  callvirt instance valuetype [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection/Enumerator<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection<string, class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonCommandDefinition>::GetEnumerator()
0xfb039  stloc.1
0xfb03a  br.s     loc_FB066
0xfb03c  ldloca.s 1
0xfb03e  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection/Enumerator<string, class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonCommandDefinition>::get_Current()
0xfb043  stloc.2
0xfb044  ldarg.1
0xfb045  ldstr    aC01// "c[{0}]={1};"
0xfb04a  ldloc.2
0xfb04b  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmJavaScriptEncode(string)
0xfb050  ldarg.0
0xfb051  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonCommandDefinition> Microsoft.Crm.Application.Pages.Common.RibbonCommandsRenderControl::_commands
0xfb056  ldloc.2
0xfb057  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonCommandDefinition>::get_Item(void)
0xfb05c  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Ribbon.RibbonJavaScriptSerialization::GetCommandJson(class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonCommandDefinition)
0xfb061  callvirt instance void [mscorlib]System.IO.TextWriter::WriteLine(string, object, object)
0xfb066  ldloca.s 1
0xfb068  call     instance bool valuetype [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection/Enumerator<string, class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonCommandDefinition>::MoveNext()
0xfb06d  brtrue.s loc_FB03C
0xfb06f  leave.s  loc_FB07F
0xfb071  ldloca.s 1
0xfb073  constrained. valuetype [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection/Enumerator<string, class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonCommandDefinition>
0xfb079  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xfb07e  endfinally
0xfb07f  ldarg.1
0xfb080  ldstr    aIfMscrmRibbonc_3// "if(!Mscrm.RibbonCommands.enableRules) M"...
0xfb085  callvirt instance void [mscorlib]System.IO.TextWriter::WriteLine(string)
0xfb08a  ldarg.1
0xfb08b  ldstr    aIfMscrmRibbonc_4// "if(!Mscrm.RibbonCommands.enableRules[{0"...
0xfb090  ldloc.0
0xfb091  callvirt instance void [mscorlib]System.IO.TextWriter::WriteLine(string, object)
0xfb096  ldarg.1
0xfb097  ldstr    aVarEMscrmRibbo// "var e = Mscrm.RibbonCommands.enableRule"...
0xfb09c  ldloc.0
0xfb09d  callvirt instance void [mscorlib]System.IO.TextWriter::WriteLine(string, object)
0xfb0a2  ldarg.0
0xfb0a3  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RuleDefinition> Microsoft.Crm.Application.Pages.Common.RibbonCommandsRenderControl::_rules
0xfb0a8  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RuleDefinition>::get_Keys()
0xfb0ad  callvirt instance valuetype [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection/Enumerator<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection<string, class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RuleDefinition>::GetEnumerator()
0xfb0b2  stloc.3
0xfb0b3  br.s     loc_FB0E2
0xfb0b5  ldloca.s 3
0xfb0b7  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection/Enumerator<string, class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RuleDefinition>::get_Current()
0xfb0bc  stloc.s  4
0xfb0be  ldarg.1
0xfb0bf  ldstr    aE01// "e[{0}]={1};"
0xfb0c4  ldloc.s  4
0xfb0c6  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmJavaScriptEncode(string)
0xfb0cb  ldarg.0
0xfb0cc  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RuleDefinition> Microsoft.Crm.Application.Pages.Common.RibbonCommandsRenderControl::_rules
0xfb0d1  ldloc.s  4
0xfb0d3  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RuleDefinition>::get_Item(void)
0xfb0d8  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Ribbon.RibbonJavaScriptSerialization::GetRuleJson(class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RuleDefinition)
0xfb0dd  callvirt instance void [mscorlib]System.IO.TextWriter::WriteLine(string, object, object)
0xfb0e2  ldloca.s 3
0xfb0e4  call     instance bool valuetype [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection/Enumerator<string, class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RuleDefinition>::MoveNext()
0xfb0e9  brtrue.s loc_FB0B5
0xfb0eb  leave.s  loc_FB0FB
0xfb0ed  ldloca.s 3
0xfb0ef  constrained. valuetype [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection/Enumerator<string, class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RuleDefinition>
0xfb0f5  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xfb0fa  endfinally
0xfb0fb  leave.s  loc_FB116
0xfb0fd  pop
0xfb0fe  ldarg.0
0xfb0ff  callvirt instance class [System.Web]System.Web.UI.Page [System.Web]System.Web.UI.Control::get_Page()
0xfb104  callvirt instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.UI.Page::get_Response()
0xfb109  callvirt instance class [System.Web]System.Web.HttpCachePolicy [System.Web]System.Web.HttpResponse::get_Cache()
0xfb10e  ldc.i4.1
0xfb10f  callvirt instance void [System.Web]System.Web.HttpCachePolicy::SetCacheability(valuetype [System.Web]System.Web.HttpCacheability)
0xfb114  rethrow
0xfb116  ret
```
