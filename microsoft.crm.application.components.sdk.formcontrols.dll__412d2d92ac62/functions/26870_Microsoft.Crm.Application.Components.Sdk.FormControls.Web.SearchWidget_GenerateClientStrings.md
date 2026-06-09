# Microsoft.Crm.Application.Components.Sdk.FormControls.Web.SearchWidget::GenerateClientStrings

- ea: `0x26870`
- end: `0x26fba`
- name: `Microsoft.Crm.Application.Components.Sdk.FormControls.Web.SearchWidget::GenerateClientStrings`
- size: `1866`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x25890`

## callees

- `0x26870`
- `0x26fc0`
- `0x27550`

## string_xrefs

- `0x26a41`: `KMWALL_COPY_ARTICLE_ICON_TOOLTIP_STRING`
- `0x26a4b`: `KMControl.SearchKMArticles.CopyArticleIconToolTip`
- `0x26a5b`: `KMWALL_COPY_ARTICLE_ICON_ALT_STRING`
- `0x26a65`: `KMControl.SearchKMArticles.CopyArticleIconAltText`
- `0x26c57`: `KMWALL_ERROR_SEARCH_COMPLETED_CAUSE_STRING`
- `0x26c61`: `SearchWidget.Completed.ErrorCause`
- `0x26c71`: `KMWALL_ERROR_SEARCH_COMPLETED_ACTION_STRING`
- `0x26c7b`: `SearchWidget.Completed.ErrorAction`
- `0x26deb`: `KMWALL_ARTICLES_SCHEDULED`
- `0x26df5`: `SearchWidget.Articles.Scheduled`
- `0x26f85`: `KMWALL_AUTOSUGGESTION_ANALYTICSSERVICE_GENERICERROR`
- `0x26f8f`: `SearchWidget.AutoSuggestion.AnalyticsService.GenericError`
- `0x26f9f`: `KMWALL_TEXTANALYTICSCONFIGURE_ERROR_STRING`

## pseudocode

```c

```

## disassembly

```asm
0x26870  ldsfld   string [mscorlib]System.String::Empty
0x26875  stloc.0
0x26876  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::.ctor()
0x2687b  stloc.1
0x2687c  ldarg.0
0x2687d  call     instance int32 Microsoft.Crm.Application.Components.Sdk.FormControls.Web.SearchWidget::get_EntityTypeCode()
0x26882  ldc.i4.0
0x26883  ble.s    loc_26892
0x26885  ldarg.0
0x26886  ldarg.0
0x26887  call     instance int32 Microsoft.Crm.Application.Components.Sdk.FormControls.Web.SearchWidget::get_EntityTypeCode()
0x2688c  call     instance string Microsoft.Crm.Application.Components.Sdk.FormControls.Web.SearchWidget::GetDisplayNameFromTypeCode(int32 objectTypeCode)
0x26891  stloc.0
0x26892  ldloc.1
0x26893  ldstr    aKmwallIconAsso// "KMWALL_ICON_ASSOCIATE_IMG_STRING"
0x26898  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x2689d  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x268a2  ldstr    aKmcontrolSearc_0// "KMControl.SearchKMArticles.Associated"
0x268a7  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x268ac  ldc.i4.1
0x268ad  newarr   [mscorlib]System.Object
0x268b2  dup
0x268b3  ldc.i4.0
0x268b4  ldloc.0
0x268b5  stelem.ref
0x268b6  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x268bb  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x268c0  ldloc.1
0x268c1  ldstr    aKmwallAssociat// "KMWALL_ASSOCIATE_ARTICLE_ICON_TOOLTIP_S"...
0x268c6  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x268cb  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x268d0  ldstr    aKmcontrolSearc_1// "KMControl.SearchKMArticles.AssociateArt"...
0x268d5  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x268da  ldc.i4.1
0x268db  newarr   [mscorlib]System.Object
0x268e0  dup
0x268e1  ldc.i4.0
0x268e2  ldloc.0
0x268e3  stelem.ref
0x268e4  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x268e9  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x268ee  ldloc.1
0x268ef  ldstr    aKmwallIconAltS// "KMWALL_ICON_ALT_STRING"
0x268f4  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x268f9  ldstr    aKmcontrolSearc_2// "KMControl.SearchKMArticles.ArticleIconA"...
0x268fe  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x26903  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x26908  ldloc.1
0x26909  ldstr    aKmwallPrivateA// "KMWALL_PRIVATE_ARTICLE_ICON_TOOLTIP_STR"...
0x2690e  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x26913  ldstr    aKmcontrolSearc_3// "KMControl.SearchKMArticles.PrivateArtic"...
0x26918  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x2691d  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x26922  ldloc.1
0x26923  ldstr    aKmwallPrivateA_0// "KMWALL_PRIVATE_ARTICLE_ICON_ALT_STRING"
0x26928  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x2692d  ldstr    aKmcontrolSearc_4// "KMControl.SearchKMArticles.PrivateArtic"...
0x26932  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x26937  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x2693c  ldloc.1
0x2693d  ldstr    aKmwallPublicAr// "KMWALL_PUBLIC_ARTICLE_ICON_TOOLTIP_STRI"...
0x26942  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x26947  ldstr    aKmcontrolSearc_5// "KMControl.SearchKMArticles.PublicArticl"...
0x2694c  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x26951  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x26956  ldloc.1
0x26957  ldstr    aKmwallPublicAr_0// "KMWALL_PUBLIC_ARTICLE_ICON_ALT_STRING"
0x2695c  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x26961  ldstr    aKmcontrolSearc_6// "KMControl.SearchKMArticles.PublicArticl"...
0x26966  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x2696b  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x26970  ldloc.1
0x26971  ldstr    aKmwallLastModi// "KMWALL_LAST_MODIFIED_ICON_TOOLTIP_STRIN"...
0x26976  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x2697b  ldstr    aKmcontrolSearc_7// "KMControl.SearchKMArticles.LastModified"...
0x26980  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x26985  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x2698a  ldloc.1
0x2698b  ldstr    aKmwallRatingIc// "KMWALL_RATING_ICON_TOOLTIP_STRING"
0x26990  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x26995  ldstr    aKmcontrolSearc_8// "KMControl.SearchKMArticles.RatingIconTo"...
0x2699a  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x2699f  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x269a4  ldloc.1
0x269a5  ldstr    aKmwallAttachme// "KMWALL_ATTACHMENTS_ICON_TOOLTIP_STRING"
0x269aa  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x269af  ldstr    aKmcontrolSearc_9// "KMControl.SearchKMArticles.AttachmentIc"...
0x269b4  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x269b9  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x269be  ldloc.1
0x269bf  ldstr    aKmwallNoofview// "KMWALL_NOOFVIEWS_ICON_TOOLTIP_STRING"
0x269c4  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x269c9  ldstr    aKmcontrolSearc_10// "KMControl.SearchKMArticles.NumberOfView"...
0x269ce  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x269d3  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x269d8  ldloc.1
0x269d9  ldstr    aKmwallNoofview_0// "KMWALL_NOOFVIEWS_ICON_ALT_STRING"
0x269de  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x269e3  ldstr    aKmcontrolSearc_11// "KMControl.SearchKMArticles.NumberOfView"...
0x269e8  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x269ed  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x269f2  ldloc.1
0x269f3  ldstr    aKmwallAssociat_0// "KMWALL_ASSOCIATE_ARTICLE_ICON_ALT_STRIN"...
0x269f8  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x269fd  ldstr    aKmcontrolSearc_12// "KMControl.SearchKMArticles.AssociateArt"...
0x26a02  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x26a07  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x26a0c  ldloc.1
0x26a0d  ldstr    aKmwallDisassoc// "KMWALL_DISASSOCIATE_ARTICLE_ICON_TOOLTI"...
0x26a12  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x26a17  ldstr    aKmcontrolSearc_13// "KMControl.SearchKMArticles.Disassociate"...
0x26a1c  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x26a21  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x26a26  ldloc.1
0x26a27  ldstr    aKmwallDisassoc_0// "KMWALL_DISASSOCIATE_ARTICLE_ICON_ALT_ST"...
0x26a2c  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x26a31  ldstr    aKmcontrolSearc_14// "KMControl.SearchKMArticles.Disassociate"...
0x26a36  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x26a3b  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x26a40  ldloc.1
0x26a41  ldstr    aKmwallCopyArti// "KMWALL_COPY_ARTICLE_ICON_TOOLTIP_STRING"
0x26a46  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x26a4b  ldstr    aKmcontrolSearc_15// "KMControl.SearchKMArticles.CopyArticleI"...
0x26a50  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x26a55  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x26a5a  ldloc.1
0x26a5b  ldstr    aKmwallCopyArti_0// "KMWALL_COPY_ARTICLE_ICON_ALT_STRING"
0x26a60  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x26a65  ldstr    aKmcontrolSearc_16// "KMControl.SearchKMArticles.CopyArticleI"...
0x26a6a  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x26a6f  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x26a74  ldloc.1
0x26a75  ldstr    aKmwallEmailArt// "KMWALL_EMAIL_ARTICLE_ICON_TOOLTIP_STRIN"...
0x26a7a  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x26a7f  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x26a84  ldstr    aKmcontrolSearc_17// "KMControl.SearchKMArticles.EmailArticle"...
0x26a89  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x26a8e  ldc.i4.1
0x26a8f  newarr   [mscorlib]System.Object
0x26a94  dup
0x26a95  ldc.i4.0
0x26a96  ldloc.0
0x26a97  stelem.ref
0x26a98  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x26a9d  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x26aa2  ldloc.1
0x26aa3  ldstr    aKmwallEmailArt_0// "KMWALL_EMAIL_ARTICLE_CONTENT_ICON_TOOLT"...
0x26aa8  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x26aad  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x26ab2  ldstr    aKmcontrolSearc_18// "KMControl.SearchKMArticles.EmailArticle"...
0x26ab7  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x26abc  ldc.i4.1
0x26abd  newarr   [mscorlib]System.Object
0x26ac2  dup
0x26ac3  ldc.i4.0
0x26ac4  ldloc.0
0x26ac5  stelem.ref
0x26ac6  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x26acb  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x26ad0  ldloc.1
0x26ad1  ldstr    aKmwallEmailArt_1// "KMWALL_EMAIL_ARTICLE_ICON_ALT_STRING"
0x26ad6  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x26adb  ldstr    aKmcontrolSearc_19// "KMControl.SearchKMArticles.EmailArticle"...
0x26ae0  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x26ae5  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x26aea  ldloc.1
0x26aeb  ldstr    aKmwallEmailArt_2// "KMWALL_EMAIL_ARTICLE_CONTENT_ICON_ALT_S"...
0x26af0  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x26af5  ldstr    aKmcontrolSearc_20// "KMControl.SearchKMArticles.EmailArticle"...
0x26afa  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x26aff  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x26b04  ldloc.1
0x26b05  ldstr    aKmwallPopoutAr// "KMWALL_POPOUT_ARTICLE_ICON_TOOLTIP_STRI"...
0x26b0a  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x26b0f  ldstr    aKmcontrolSearc_21// "KMControl.SearchKMArticles.PopOutToolTi"...
0x26b14  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x26b19  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x26b1e  ldloc.1
0x26b1f  ldstr    aKmwallPopoutAr_0// "KMWALL_POPOUT_ARTICLE_ICON_ALT_STRING"
0x26b24  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x26b29  ldstr    aKmcontrolSearc_22// "KMControl.SearchKMArticles.PopOutAltTex"...
0x26b2e  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x26b33  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x26b38  ldloc.1
0x26b39  ldstr    aKmwallNoSearch// "KMWALL_NO_SEARCH_RESULTS_STRING"
0x26b3e  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x26b43  ldstr    aKmcontrolSearc_23// "KMControl.SearchKMArticles.NoResults"
0x26b48  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x26b4d  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x26b52  ldloc.1
0x26b53  ldstr    aKmwallMoreSear// "KMWALL_MORE_SEARCH_RESULTS_STRING"
0x26b58  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x26b5d  ldstr    aKmcontrolSearc_24// "KMControl.SearchKMArticles.MoreResults"
0x26b62  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x26b67  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x26b6c  ldloc.1
0x26b6d  ldstr    aKmwallPopoutPr// "KMWALL_POPOUT_PRIVATE_ARTICLE"
0x26b72  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x26b77  ldstr    aKmcontrolPriva// "KMControl.PrivateArticles"
0x26b7c  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x26b81  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x26b86  ldloc.1
0x26b87  ldstr    aKmwallPopoutUn// "KMWALL_POPOUT_UNPUBLISHED_ARTICLE"
0x26b8c  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x26b91  ldstr    aKmcontrolUnpub// "KMControl.UnpublishedArticles"
0x26b96  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x26b9b  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x26ba0  ldloc.1
0x26ba1  ldstr    aKmwallPopoutDr// "KMWALL_POPOUT_DRAFT_ARTICLE"
0x26ba6  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x26bab  ldstr    aKmcontrolDraft// "KMControl.DraftArticles"
0x26bb0  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x26bb5  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x26bba  ldloc.1
0x26bbb  ldstr    aKmwallShowmore// "KMWALL_SHOWMORE_TOOLTIP"
0x26bc0  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x26bc5  ldstr    aKmcontrolSearc_25// "KMControl.SearchKMArticles.ShowMoreArti"...
0x26bca  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x26bcf  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x26bd4  ldloc.1
0x26bd5  ldstr    aKmwallShowmore_0// "KMWALL_SHOWMORE_TEXT"
0x26bda  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x26bdf  ldstr    aKmcontrolSearc_26// "KMControl.SearchKMArticles.ShowMoreArti"...
0x26be4  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x26be9  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x26bee  ldloc.1
0x26bef  ldstr    aKmwallShowmore_1// "KMWALL_SHOWMOREPROGRESS_ALT"
0x26bf4  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x26bf9  ldstr    aKmcontrolLoadi// "KMControl.Loading"
0x26bfe  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x26c03  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x26c08  ldloc.1
0x26c09  ldstr    aKmwallLastModi_0// "KMWALL_LAST_MODIFIED_LABEL_STRING"
0x26c0e  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x26c13  ldstr    aKmcontrolSearc_27// "KMControl.SearchKMArticles.LastModified"...
0x26c18  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x26c1d  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x26c22  ldloc.1
0x26c23  ldstr    aKmwallErrorSea// "KMWALL_ERROR_SEARCH_ENABLED_CAUSE_STRIN"...
0x26c28  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x26c2d  ldstr    aSearchwidgetEn// "SearchWidget.Enabled.ErrorCause"
0x26c32  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x26c37  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x26c3c  ldloc.1
0x26c3d  ldstr    aKmwallErrorSea_0// "KMWALL_ERROR_SEARCH_ENABLED_ACTION_STRI"...
0x26c42  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x26c47  ldstr    aSearchwidgetEn_0// "SearchWidget.Enabled.ErrorAction"
0x26c4c  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x26c51  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x26c56  ldloc.1
0x26c57  ldstr    aKmwallErrorSea_1// "KMWALL_ERROR_SEARCH_COMPLETED_CAUSE_STR"...
0x26c5c  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x26c61  ldstr    aSearchwidgetCo// "SearchWidget.Completed.ErrorCause"
0x26c66  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x26c6b  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x26c70  ldloc.1
0x26c71  ldstr    aKmwallErrorSea_2// "KMWALL_ERROR_SEARCH_COMPLETED_ACTION_ST"...
0x26c76  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x26c7b  ldstr    aSearchwidgetCo_0// "SearchWidget.Completed.ErrorAction"
0x26c80  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x26c85  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x26c8a  ldloc.1
0x26c8b  ldstr    aKmwallMaxRatin// "KMWALL_MAX_RATING_VALUE_STRING"
0x26c90  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x26c95  ldstr    aKmcontrolMaxra// "KMControl.MaxRatingValue"
0x26c9a  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x26c9f  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x26ca4  ldloc.1
0x26ca5  ldstr    aKmwallMaxRatin_0// "KMWALL_MAX_RATING_VALUE_RTL_STRING"
0x26caa  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x26caf  ldstr    aKmcontrolRtlMa// "KMControl.RTL.MaxRatingValue"
0x26cb4  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x26cb9  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x26cbe  ldloc.1
0x26cbf  ldstr    aKmwallArticleT// "KMWALL_ARTICLE_TYPE_TOOLTIP_STRING"
0x26cc4  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x26cc9  ldstr    aSearchwidgetFi// "SearchWidget.Filters.ArticleTooltip"
0x26cce  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x26cd3  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x26cd8  ldloc.1
0x26cd9  ldstr    aKmwallParature// "KMWALL_PARATURE_CONNECTION_ERROR_STRING"
0x26cde  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x26ce3  ldstr    aSearchwidgetPa// "SearchWidget.Parature.ConnectionError"
0x26ce8  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x26ced  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x26cf2  ldloc.1
0x26cf3  ldstr    aKmwallParature_0// "KMWALL_PARATURE_OUTLOOK_ERROR_STRING"
0x26cf8  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x26cfd  ldstr    aSearchwidgetPa_0// "SearchWidget.Parature.OutlookError"
0x26d02  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x26d07  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x26d0c  ldloc.1
0x26d0d  ldstr    aKmwallParature_1// "KMWALL_PARATURE_CONNECTION_GENERIC_ERRO"...
0x26d12  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x26d17  ldstr    aSearchwidgetPa_1// "SearchWidget.Parature.ConnectionGeneric"...
0x26d1c  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x26d21  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x26d26  ldloc.1
0x26d27  ldstr    aKmwallParature_2// "KMWALL_PARATURE_PERMISSION_ERROR_STRING"
0x26d2c  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
  ... truncated ...
```
