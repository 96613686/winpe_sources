# Microsoft.Crm.Service.Web.Tools.ServiceManagement.KBContentPage::GenerateClientStrings

- ea: `0x8130`
- end: `0x8262`
- name: `Microsoft.Crm.Service.Web.Tools.ServiceManagement.KBContentPage::GenerateClientStrings`
- size: `306`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x7fe0`

## callees

- `0x8130`

## pseudocode

```c

```

## disassembly

```asm
0x8130  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::.ctor()
0x8135  dup
0x8136  ldstr    aKmwallIconAltS// "KMWALL_ICON_ALT_STRING"
0x813b  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x8140  ldstr    aKmcontrolSearc// "KMControl.SearchKMArticles.ArticleIconA"...
0x8145  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x814a  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x814f  dup
0x8150  ldstr    aKmwallLastModi// "KMWALL_LAST_MODIFIED_ICON_TOOLTIP_STRIN"...
0x8155  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x815a  ldstr    aKmcontrolSearc_0// "KMControl.SearchKMArticles.LastModified"...
0x815f  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x8164  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x8169  dup
0x816a  ldstr    aKmwallRatingIc// "KMWALL_RATING_ICON_TOOLTIP_STRING"
0x816f  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x8174  ldstr    aKmcontrolSearc_1// "KMControl.SearchKMArticles.RatingIconTo"...
0x8179  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x817e  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x8183  dup
0x8184  ldstr    aKmwallAttachme// "KMWALL_ATTACHMENTS_ICON_TOOLTIP_STRING"
0x8189  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x818e  ldstr    aKmcontrolSearc_2// "KMControl.SearchKMArticles.AttachmentIc"...
0x8193  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x8198  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x819d  dup
0x819e  ldstr    aKmwallNoofview// "KMWALL_NOOFVIEWS_ICON_TOOLTIP_STRING"
0x81a3  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x81a8  ldstr    aKmcontrolSearc_3// "KMControl.SearchKMArticles.NumberOfView"...
0x81ad  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x81b2  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x81b7  dup
0x81b8  ldstr    aKmwallNoofview_0// "KMWALL_NOOFVIEWS_ICON_ALT_STRING"
0x81bd  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x81c2  ldstr    aKmcontrolSearc_4// "KMControl.SearchKMArticles.NumberOfView"...
0x81c7  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x81cc  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x81d1  dup
0x81d2  ldstr    aKmwallLastModi_0// "KMWALL_LAST_MODIFIED_LABEL_STRING"
0x81d7  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x81dc  ldstr    aKmcontrolSearc_5// "KMControl.SearchKMArticles.LastModified"...
0x81e1  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x81e6  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x81eb  dup
0x81ec  ldstr    aKmwallMaxRatin// "KMWALL_MAX_RATING_VALUE_STRING"
0x81f1  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x81f6  ldstr    aKmcontrolMaxra// "KMControl.MaxRatingValue"
0x81fb  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x8200  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x8205  dup
0x8206  ldstr    aKmwallMaxRatin_0// "KMWALL_MAX_RATING_VALUE_RTL_STRING"
0x820b  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x8210  ldstr    aKmcontrolRtlMa// "KMControl.RTL.MaxRatingValue"
0x8215  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x821a  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x821f  dup
0x8220  ldstr    aKmwallArticleT// "KMWALL_ARTICLE_TYPE_TOOLTIP_STRING"
0x8225  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x822a  ldstr    aSearchwidgetFi// "SearchWidget.Filters.ArticleTooltip"
0x822f  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x8234  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x8239  dup
0x823a  ldstr    aKmwallLocidUiD// "KMWALL_LOCID_UI_DIR"
0x823f  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentUICulture()
0x8244  callvirt instance class [mscorlib]System.Globalization.TextInfo [mscorlib]System.Globalization.CultureInfo::get_TextInfo()
0x8249  callvirt instance bool [mscorlib]System.Globalization.TextInfo::get_IsRightToLeft()
0x824e  brtrue.s loc_8257
0x8250  ldstr    aLtr// "LTR"
0x8255  br.s     loc_825C
0x8257  ldstr    aRtl// "RTL"
0x825c  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x8261  ret
```
