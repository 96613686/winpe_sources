# Microsoft.Crm.Application.Components.Sdk.FormControls.Web.SearchWidget::RenderSearchAndFilters

- ea: `0x26020`
- end: `0x264bf`
- name: `Microsoft.Crm.Application.Components.Sdk.FormControls.Web.SearchWidget::RenderSearchAndFilters`
- size: `1183`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x25e10`

## callees

- `0x26020`
- `0x264e0`
- `0x26820`
- `0x27040`
- `0x27060`
- `0x270c0`
- `0x27a00`

## pseudocode

```c

```

## disassembly

```asm
0x26020  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x26025  ldstr    aKmcontrolFilte// "KMControl.Filter.Label.FilterResultBy"
0x2602a  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x2602f  stloc.0
0x26030  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x26035  ldstr    aKmcontrolFilte_0// "KMControl.Filter.Label.ArticleType"
0x2603a  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x2603f  stloc.1
0x26040  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x26045  ldstr    aKmcontrolFilte_1// "KMControl.Filter.Label.Language"
0x2604a  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x2604f  stloc.2
0x26050  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x26055  ldstr    aKmcontrolFilte_2// "KMControl.Filter.Label.Department"
0x2605a  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x2605f  stloc.3
0x26060  ldarg.1
0x26061  ldstr    aDivId0StyleHei// "<div id=\"{0}\" style=\"height:100%\"><"...
0x26066  ldarg.0
0x26067  callvirt instance string [System.Web]System.Web.UI.Control::get_ClientID()
0x2606c  ldstr    aKmwallelementc// "_kmWallElementContainer"
0x26071  call     string [mscorlib]System.String::Concat(string, string)
0x26076  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string)
0x2607b  ldarg.0
0x2607c  callvirt instance string [System.Web]System.Web.UI.Control::get_ClientID()
0x26081  ldstr    aHeader_0// "_header"
0x26086  call     string [mscorlib]System.String::Concat(string, string)
0x2608b  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string)
0x26090  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string, object, object)
0x26095  ldarg.1
0x26096  ldstr    aDivClassKmwall// "<div class=\"kmwall-div-table\" style="...
0x2609b  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x260a0  ldarg.1
0x260a1  ldstr    aDivValignTopCl// "<div valign=\"top\" class=\"kmwall-tabl"...
0x260a6  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x260ab  ldarg.0
0x260ac  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.WatermarkTextBox Microsoft.Crm.Application.Components.Sdk.FormControls.Web.SearchWidget::searchTextBox
0x260b1  ldarg.1
0x260b2  callvirt instance void [System.Web]System.Web.UI.Control::RenderControl(class [System.Web]System.Web.UI.HtmlTextWriter)
0x260b7  ldarg.1
0x260b8  ldstr    aDivDiv// "</div></div>"
0x260bd  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x260c2  ldarg.1
0x260c3  ldstr    aDivValignTopCl_0// "<div valign=\"top\" class=\"kmwall-tabl"...
0x260c8  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x260cd  ldarg.1
0x260ce  ldstr    aATabindex0Clas// "<a tabindex=\"{0}\" class=\"ms-crm-Find"...
0x260d3  ldc.i4.4
0x260d4  newarr   [mscorlib]System.Object
0x260d9  dup
0x260da  ldc.i4.0
0x260db  ldarg.0
0x260dc  call     instance int32 Microsoft.Crm.Application.Components.Sdk.FormControls.Web.SearchWidget::get_TabIndex()
0x260e1  stloc.s  4
0x260e3  ldloca.s 4
0x260e5  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x260ea  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x260ef  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string)
0x260f4  stelem.ref
0x260f5  dup
0x260f6  ldc.i4.1
0x260f7  ldarg.0
0x260f8  callvirt instance string [System.Web]System.Web.UI.Control::get_ClientID()
0x260fd  ldstr    aFindcriteriabu// "_findCriteriaButton"
0x26102  call     string [mscorlib]System.String::Concat(string, string)
0x26107  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string)
0x2610c  stelem.ref
0x2610d  dup
0x2610e  ldc.i4.2
0x2610f  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x26114  ldstr    aSearchwidgetSt// "SearchWidget.StartSearch"
0x26119  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x2611e  stelem.ref
0x2611f  dup
0x26120  ldc.i4.3
0x26121  ldarg.0
0x26122  callvirt instance string [System.Web]System.Web.UI.Control::get_ClientID()
0x26127  ldstr    aFindcriteriaim// "_findCriteriaImg"
0x2612c  call     string [mscorlib]System.String::Concat(string, string)
0x26131  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string)
0x26136  stelem.ref
0x26137  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string, object[])
0x2613c  ldarg.1
0x2613d  ldstr    aDiv_0// "</div>"
0x26142  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x26147  ldarg.1
0x26148  ldstr    aDivDivDiv// "</div></div></div>"
0x2614d  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x26152  ldarg.1
0x26153  ldstr    aDivClassKmwall_0// "<div class=\"kmwall-div-table filterdiv"...
0x26158  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x2615d  ldarg.0
0x2615e  call     instance bool Microsoft.Crm.Application.Components.Sdk.FormControls.Web.SearchWidget::get_AllowChangingFiltersOnUI()
0x26163  brtrue.s loc_26182
0x26165  ldarg.0
0x26166  call     instance bool Microsoft.Crm.Application.Components.Sdk.FormControls.Web.SearchWidget::get_ShowLanguageFilter()
0x2616b  brtrue.s loc_26182
0x2616d  ldarg.0
0x2616e  call     instance bool Microsoft.Crm.Application.Components.Sdk.FormControls.Web.SearchWidget::get_ShowDepartmentFilter()
0x26173  brtrue.s loc_26182
0x26175  ldarg.1
0x26176  ldstr    aStyleDisplayNo_0// " style=\"display:none;\">"
0x2617b  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x26180  br.s     loc_2618D
0x26182  ldarg.1
0x26183  ldstr    asc_3033C// ">"
0x26188  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x2618d  ldarg.1
0x2618e  ldstr    aDivClassKmwall_1// "<div class=\"kmwall-div-table-row\">"
0x26193  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x26198  ldarg.1
0x26199  ldstr    aDivClassKmwall_2// "<div class=\"kmwall-div-textdisplaynone"...
0x2619e  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x261a3  ldarg.1
0x261a4  ldloc.0
0x261a5  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x261aa  ldarg.1
0x261ab  ldstr    aDiv_0// "</div>"
0x261b0  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x261b5  ldarg.0
0x261b6  call     instance bool Microsoft.Crm.Application.Components.Sdk.FormControls.Web.SearchWidget::get_AllowChangingFiltersOnUI()
0x261bb  brfalse.s loc_26213
0x261bd  ldarg.1
0x261be  ldstr    aDivClassKmwall_3// "<div class=\"kmwall-div-textdisplaynone"...
0x261c3  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x261c8  ldarg.1
0x261c9  ldloc.1
0x261ca  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x261cf  ldarg.1
0x261d0  ldstr    aDiv_0// "</div>"
0x261d5  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x261da  ldarg.1
0x261db  ldstr    aDivId0ClassKmw// "<div id=\"{0}\" class=\"kmwall-div-tabl"...
0x261e0  ldarg.0
0x261e1  callvirt instance string [System.Web]System.Web.UI.Control::get_ClientID()
0x261e6  ldstr    aKmwalltypefilt// "_kmwallTypeFilterButton"
0x261eb  call     string [mscorlib]System.String::Concat(string, string)
0x261f0  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string)
0x261f5  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string, object)
0x261fa  ldarg.0
0x261fb  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.ArticleTypesFilter Microsoft.Crm.Application.Components.Sdk.FormControls.Web.SearchWidget::inlineActivityWallFilterButton
0x26200  ldarg.1
0x26201  callvirt instance void [System.Web]System.Web.UI.Control::RenderControl(class [System.Web]System.Web.UI.HtmlTextWriter)
0x26206  ldarg.1
0x26207  ldstr    aDiv_0// "</div>"
0x2620c  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x26211  br.s     loc_26259
0x26213  ldarg.0
0x26214  call     instance bool Microsoft.Crm.Application.Components.Sdk.FormControls.Web.SearchWidget::get_ShowLanguageFilter()
0x26219  brtrue.s loc_26259
0x2621b  ldarg.0
0x2621c  call     instance bool Microsoft.Crm.Application.Components.Sdk.FormControls.Web.SearchWidget::get_ShowDepartmentFilter()
0x26221  brtrue.s loc_26259
0x26223  ldarg.1
0x26224  ldstr    aDivId0ClassKmw_0// "<div id=\"{0}\" class=\"kmwall-div-tabl"...
0x26229  ldarg.0
0x2622a  callvirt instance string [System.Web]System.Web.UI.Control::get_ClientID()
0x2622f  ldstr    aKmwalltypefilt// "_kmwallTypeFilterButton"
0x26234  call     string [mscorlib]System.String::Concat(string, string)
0x26239  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string)
0x2623e  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string, object)
0x26243  ldarg.1
0x26244  ldstr    aNbsp// "&nbsp;"
0x26249  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x2624e  ldarg.1
0x2624f  ldstr    aDiv_0// "</div>"
0x26254  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x26259  ldarg.0
0x2625a  call     instance bool Microsoft.Crm.Application.Components.Sdk.FormControls.Web.SearchWidget::get_ShowLanguageFilter()
0x2625f  brfalse  loc_26305
0x26264  ldarg.0
0x26265  call     instance bool Microsoft.Crm.Application.Components.Sdk.FormControls.Web.SearchWidget::get_IsKnowledgeMangementParatureConfigured()
0x2626a  brtrue   loc_26305
0x2626f  ldarg.1
0x26270  ldstr    aDivClassKmwall_4// "<div class=\"kmwall-div-textdisplaynone"...
0x26275  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x2627a  ldarg.0
0x2627b  call     instance bool Microsoft.Crm.Application.Components.Sdk.FormControls.Web.SearchWidget::get_AllowChangingFiltersOnUI()
0x26280  brtrue.s loc_2628F
0x26282  ldarg.1
0x26283  ldstr    aStylePaddingTo// " style=\"padding-top: 0px;\">"
0x26288  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x2628d  br.s     loc_2629A
0x2628f  ldarg.1
0x26290  ldstr    asc_3033C// ">"
0x26295  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x2629a  ldarg.1
0x2629b  ldloc.2
0x2629c  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x262a1  ldarg.1
0x262a2  ldstr    aDiv_0// "</div>"
0x262a7  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x262ac  ldarg.1
0x262ad  ldstr    aDivId0ClassKmw_1// "<div id=\"{0}\" class=\"kmwall-div-tabl"...
0x262b2  ldarg.0
0x262b3  callvirt instance string [System.Web]System.Web.UI.Control::get_ClientID()
0x262b8  ldstr    aKmwalllanguage// "_kmwallLanguageFilterButton"
0x262bd  call     string [mscorlib]System.String::Concat(string, string)
0x262c2  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string)
0x262c7  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string, object)
0x262cc  ldarg.0
0x262cd  call     instance bool Microsoft.Crm.Application.Components.Sdk.FormControls.Web.SearchWidget::get_AllowChangingFiltersOnUI()
0x262d2  brtrue.s loc_262E1
0x262d4  ldarg.1
0x262d5  ldstr    aStyleBorderLef// " style=\"border-left: 0px;border-right:"...
0x262da  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x262df  br.s     loc_262EC
0x262e1  ldarg.1
0x262e2  ldstr    asc_3033C// ">"
0x262e7  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x262ec  ldarg.0
0x262ed  ldfld    class Microsoft.Crm.Application.Components.Sdk.FormControls.Web.ILanguageFilter Microsoft.Crm.Application.Components.Sdk.FormControls.Web.SearchWidget::inlineActivityWallFilterLanguageButton
0x262f2  ldarg.1
0x262f3  callvirt instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.ILanguageFilter::RenderControl(class [System.Web]System.Web.UI.HtmlTextWriter output)
0x262f8  ldarg.1
0x262f9  ldstr    aDiv_0// "</div>"
0x262fe  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x26303  br.s     loc_2633B
0x26305  ldarg.1
0x26306  ldstr    aDivId0ClassKmw_0// "<div id=\"{0}\" class=\"kmwall-div-tabl"...
0x2630b  ldarg.0
0x2630c  callvirt instance string [System.Web]System.Web.UI.Control::get_ClientID()
0x26311  ldstr    aKmwalllanguage// "_kmwallLanguageFilterButton"
0x26316  call     string [mscorlib]System.String::Concat(string, string)
0x2631b  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string)
0x26320  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string, object)
0x26325  ldarg.1
0x26326  ldstr    aNbsp// "&nbsp;"
0x2632b  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x26330  ldarg.1
0x26331  ldstr    aDiv_0// "</div>"
0x26336  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x2633b  ldarg.0
0x2633c  call     instance bool Microsoft.Crm.Application.Components.Sdk.FormControls.Web.SearchWidget::get_ShowDepartmentFilter()
0x26341  brfalse.s loc_26399
0x26343  ldarg.1
0x26344  ldstr    aDivClassKmwall_5// "<div class=\"kmwall-div-textdisplaynone"...
0x26349  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x2634e  ldarg.1
0x2634f  ldloc.3
0x26350  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x26355  ldarg.1
0x26356  ldstr    aDiv_0// "</div>"
0x2635b  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x26360  ldarg.1
0x26361  ldstr    aDivId0ClassKmw_2// "<div id=\"{0}\" class=\"kmwall-div-tabl"...
0x26366  ldarg.0
0x26367  callvirt instance string [System.Web]System.Web.UI.Control::get_ClientID()
0x2636c  ldstr    aKmwalldepartme// "_kmwallDepartmentFilterButton"
0x26371  call     string [mscorlib]System.String::Concat(string, string)
0x26376  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string)
0x2637b  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string, object)
0x26380  ldarg.0
0x26381  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.DepartmentFilter Microsoft.Crm.Application.Components.Sdk.FormControls.Web.SearchWidget::inlineActivityWallFilterDepartmentButton
0x26386  ldarg.1
0x26387  callvirt instance void [System.Web]System.Web.UI.Control::RenderControl(class [System.Web]System.Web.UI.HtmlTextWriter)
0x2638c  ldarg.1
0x2638d  ldstr    aDiv_0// "</div>"
0x26392  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x26397  br.s     loc_263CF
0x26399  ldarg.1
0x2639a  ldstr    aDivId0ClassKmw_3// "<div id=\"{0}\" class=\"kmwall-div-tabl"...
0x2639f  ldarg.0
0x263a0  callvirt instance string [System.Web]System.Web.UI.Control::get_ClientID()
0x263a5  ldstr    aKmwalldepartme// "_kmwallDepartmentFilterButton"
0x263aa  call     string [mscorlib]System.String::Concat(string, string)
0x263af  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string)
0x263b4  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string, object)
0x263b9  ldarg.1
0x263ba  ldstr    aNbsp// "&nbsp;"
0x263bf  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x263c4  ldarg.1
0x263c5  ldstr    aDiv_0// "</div>"
0x263ca  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x263cf  ldarg.1
0x263d0  ldstr    aDivDiv// "</div></div>"
0x263d5  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x263da  ldarg.1
0x263db  ldstr    aDivClassKmwall_6// "<div class=\"kmwall-div-table filterdiv"...
0x263e0  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x263e5  ldarg.1
0x263e6  ldstr    aDivClassKmwall_7// "<div class=\"kmwall-div-table-row sortF"...
0x263eb  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x263f0  ldarg.1
0x263f1  ldstr    aDivClassKmwall_8// "<div class=\"kmwall-div-table-cell sort"...
0x263f6  ldarg.0
0x263f7  callvirt instance string [System.Web]System.Web.UI.Control::get_ClientID()
0x263fc  ldstr    aKmwallsearchre// "_kmWallSearchResultsCount"
0x26401  call     string [mscorlib]System.String::Concat(string, string)
0x26406  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string)
0x2640b  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string, object)
0x26410  ldarg.1
0x26411  ldstr    aDivId0ClassKmw_4// "<div id=\"{0}\" class=\"kmwall-div-tabl"...
0x26416  ldarg.0
0x26417  callvirt instance string [System.Web]System.Web.UI.Control::get_ClientID()
0x2641c  ldstr    aKmwallsortfilt// "_kmwallSortFilterButton"
0x26421  call     string [mscorlib]System.String::Concat(string, string)
0x26426  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string)
0x2642b  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string, object)
0x26430  ldarg.0
  ... truncated ...
```
