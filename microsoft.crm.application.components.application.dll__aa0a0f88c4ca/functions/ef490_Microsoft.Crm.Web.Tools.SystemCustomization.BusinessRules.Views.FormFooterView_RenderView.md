# Microsoft.Crm.Web.Tools.SystemCustomization.BusinessRules.Views.FormFooterView::RenderView

- ea: `0xef490`
- end: `0xef5a7`
- name: `Microsoft.Crm.Web.Tools.SystemCustomization.BusinessRules.Views.FormFooterView::RenderView`
- size: `279`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0xea2b0`
- `0xea2f0`
- `0xef490`

## string_xrefs

- `0xef4d7`: `SystemCustomization.BusinessRules.ReadOnly`
- `0xef51a`: `\n<div>\n	<div id='{0}_text' class='footerActivateState'>\n		<span>{1}</span>\n	</div>\n	<div id='{2}_text' class='footerReadOnlyState'>\n		<span>{3}</span>\n		{4}\n	</div>\n	<div class='footerSpliter'></div>\n</div>`
- `0xef538`: `footerReadOnlyState`
- `0xef583`: `footerReadOnlyState`

## pseudocode

```c

```

## disassembly

```asm
0xef490  ldarg.0
0xef491  ldfld    class Microsoft.Crm.Web.Tools.SystemCustomization.BusinessRules.ViewModels.IManageBusinessRuleViewModel Microsoft.Crm.Web.Tools.SystemCustomization.BusinessRules.Views.FormFooterView::_viewModel
0xef496  callvirt instance bool Microsoft.Crm.Web.Tools.SystemCustomization.BusinessRules.ViewModels.IManageBusinessRuleViewModel::get_Activated()
0xef49b  brtrue.s loc_EF4AE
0xef49d  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xef4a2  ldstr    aSystemcustomiz_198// "SystemCustomization.BusinessRules.Draft"
0xef4a7  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xef4ac  br.s     loc_EF4BD
0xef4ae  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xef4b3  ldstr    aSystemcustomiz_199// "SystemCustomization.BusinessRules.Activ"...
0xef4b8  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xef4bd  stloc.0
0xef4be  ldarg.0
0xef4bf  ldfld    class Microsoft.Crm.Web.Tools.SystemCustomization.BusinessRules.ViewModels.IManageBusinessRuleViewModel Microsoft.Crm.Web.Tools.SystemCustomization.BusinessRules.Views.FormFooterView::_viewModel
0xef4c4  callvirt instance bool Microsoft.Crm.Web.Tools.SystemCustomization.BusinessRules.ViewModels.IManageBusinessRuleViewModel::get_ReadOnly()
0xef4c9  brtrue.s loc_EF4D2
0xef4cb  ldstr    asc_F537C// ""
0xef4d0  br.s     loc_EF4E1
0xef4d2  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xef4d7  ldstr    aSystemcustomiz_200// "SystemCustomization.BusinessRules.ReadO"...
0xef4dc  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xef4e1  stloc.1
0xef4e2  ldstr    asc_F537C// ""
0xef4e7  stloc.2
0xef4e8  ldarg.0
0xef4e9  ldfld    class Microsoft.Crm.Web.Tools.SystemCustomization.BusinessRules.ViewModels.IManageBusinessRuleViewModel Microsoft.Crm.Web.Tools.SystemCustomization.BusinessRules.Views.FormFooterView::_viewModel
0xef4ee  callvirt instance bool Microsoft.Crm.Web.Tools.SystemCustomization.BusinessRules.ViewModels.IManageBusinessRuleViewModel::get_ReadOnly()
0xef4f3  brfalse.s loc_EF514
0xef4f5  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xef4fa  ldstr    aImgAlt0Title0S// "<img alt='{0}' title='{0}' src='/_imgs/"...
0xef4ff  ldc.i4.1
0xef500  newarr   [mscorlib]System.Object
0xef505  dup
0xef506  ldc.i4.0
0xef507  ldloc.1
0xef508  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlEncode(string)
0xef50d  stelem.ref
0xef50e  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xef513  stloc.2
0xef514  ldarg.1
0xef515  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xef51a  ldstr    aDivDivId0TextC// "\r\n<div>\r\n\t<div id='{0}_text' class"...
0xef51f  ldc.i4.5
0xef520  newarr   [mscorlib]System.Object
0xef525  dup
0xef526  ldc.i4.0
0xef527  ldstr    aFooteractivate// "footerActivatedState"
0xef52c  stelem.ref
0xef52d  dup
0xef52e  ldc.i4.1
0xef52f  ldloc.0
0xef530  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlEncode(string)
0xef535  stelem.ref
0xef536  dup
0xef537  ldc.i4.2
0xef538  ldstr    aFooterreadonly// "footerReadOnlyState"
0xef53d  stelem.ref
0xef53e  dup
0xef53f  ldc.i4.3
0xef540  ldloc.1
0xef541  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlEncode(string)
0xef546  stelem.ref
0xef547  dup
0xef548  ldc.i4.4
0xef549  ldloc.2
0xef54a  stelem.ref
0xef54b  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xef550  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0xef555  ldarg.1
0xef556  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xef55b  ldstr    aInputTypeHidde_56// "<input type='hidden' id='{0}' name='{0}"...
0xef560  ldc.i4.4
0xef561  newarr   [mscorlib]System.Object
0xef566  dup
0xef567  ldc.i4.0
0xef568  ldstr    aFooteractivate// "footerActivatedState"
0xef56d  stelem.ref
0xef56e  dup
0xef56f  ldc.i4.1
0xef570  ldarg.0
0xef571  ldfld    class Microsoft.Crm.Web.Tools.SystemCustomization.BusinessRules.ViewModels.IManageBusinessRuleViewModel Microsoft.Crm.Web.Tools.SystemCustomization.BusinessRules.Views.FormFooterView::_viewModel
0xef576  callvirt instance bool Microsoft.Crm.Web.Tools.SystemCustomization.BusinessRules.ViewModels.IManageBusinessRuleViewModel::get_Activated()
0xef57b  box      [mscorlib]System.Boolean
0xef580  stelem.ref
0xef581  dup
0xef582  ldc.i4.2
0xef583  ldstr    aFooterreadonly// "footerReadOnlyState"
0xef588  stelem.ref
0xef589  dup
0xef58a  ldc.i4.3
0xef58b  ldarg.0
0xef58c  ldfld    class Microsoft.Crm.Web.Tools.SystemCustomization.BusinessRules.ViewModels.IManageBusinessRuleViewModel Microsoft.Crm.Web.Tools.SystemCustomization.BusinessRules.Views.FormFooterView::_viewModel
0xef591  callvirt instance bool Microsoft.Crm.Web.Tools.SystemCustomization.BusinessRules.ViewModels.IManageBusinessRuleViewModel::get_ReadOnly()
0xef596  box      [mscorlib]System.Boolean
0xef59b  stelem.ref
0xef59c  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xef5a1  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0xef5a6  ret
```
