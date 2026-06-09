# Microsoft.Crm.Web.Tools.Admin.OptionalFeaturesPage::ConfigurePage

- ea: `0x891e0`
- end: `0x8946b`
- name: `Microsoft.Crm.Web.Tools.Admin.OptionalFeaturesPage::ConfigurePage`
- size: `651`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x89150`

## string_xrefs

- `0x891fd`: `OptionalFeatures.aspx_Link_11`
- `0x8921d`: `OptionalFeatures.aspx_Link_11`
- `0x8923d`: `OptionalFeatures.aspx_Link_LearnMore`
- `0x892bb`: `/_imgs/tools/UXScreenshots/UXScreenshotServiceSetupPreview.{0}.png`
- `0x89328`: `/_imgs/tools/UXScreenshots/UXScreenshotServiceSetupFull.{0}.png`
- `0x8936d`: `OptionalFeatures.aspx_Link_12`
- `0x893c8`: `OptionalFeatures.aspx_Link_12`
- `0x8938d`: `OptionalFeatures.aspx_Link_13`
- `0x893e8`: `OptionalFeatures.aspx_Link_13`
- `0x89408`: `OptionalFeatures.aspx_Link_41`
- `0x89428`: `OptionalFeatures.aspx_Link_61`
- `0x89443`: `OptionalFeatures.aspx_Link_31`

## pseudocode

```c

```

## disassembly

```asm
0x891e0  ldarg.0
0x891e1  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::ConfigurePage()
0x891e6  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentUICulture()
0x891eb  callvirt instance int32 [mscorlib]System.Globalization.CultureInfo::get_LCID()
0x891f0  stloc.0
0x891f1  ldarg.0
0x891f2  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlAnchor Microsoft.Crm.Web.Tools.Admin.OptionalFeaturesPage::whatIsNewLink1
0x891f7  ldarg.0
0x891f8  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x891fd  ldstr    aOptionalfeatur_1// "OptionalFeatures.aspx_Link_11"
0x89202  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x89207  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string)
0x8920c  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlAnchor::set_HRef(string)
0x89211  ldarg.0
0x89212  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlAnchor Microsoft.Crm.Web.Tools.Admin.OptionalFeaturesPage::whatIsNewLink2
0x89217  ldarg.0
0x89218  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x8921d  ldstr    aOptionalfeatur_1// "OptionalFeatures.aspx_Link_11"
0x89222  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x89227  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string)
0x8922c  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlAnchor::set_HRef(string)
0x89231  ldarg.0
0x89232  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlAnchor Microsoft.Crm.Web.Tools.Admin.OptionalFeaturesPage::learnMoreLink
0x89237  ldarg.0
0x89238  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x8923d  ldstr    aOptionalfeatur_2// "OptionalFeatures.aspx_Link_LearnMore"
0x89242  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x89247  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string)
0x8924c  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlAnchor::set_HRef(string)
0x89251  ldarg.0
0x89252  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlImage Microsoft.Crm.Web.Tools.Admin.OptionalFeaturesPage::previewImageThumbnail
0x89257  ldarg.0
0x89258  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x8925d  ldstr    aOptionalfeatur_3// "OptionalFeatures.aspx_Preview_12"
0x89262  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x89267  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlImage::set_Alt(string)
0x8926c  ldarg.0
0x8926d  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlImage Microsoft.Crm.Web.Tools.Admin.OptionalFeaturesPage::previewImageThumbnail
0x89272  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x89277  ldstr    aImgsToolsUxscr// "/_imgs/tools/UXScreenshots/UXScreenshot"...
0x8927c  ldc.i4.1
0x8927d  newarr   [mscorlib]System.Object
0x89282  dup
0x89283  ldc.i4.0
0x89284  ldloc.0
0x89285  box      [mscorlib]System.Int32
0x8928a  stelem.ref
0x8928b  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x89290  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlImage::set_Src(string)
0x89295  ldarg.0
0x89296  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlImage Microsoft.Crm.Web.Tools.Admin.OptionalFeaturesPage::previewImageThumbnail1
0x8929b  ldarg.0
0x8929c  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x892a1  ldstr    aOptionalfeatur_3// "OptionalFeatures.aspx_Preview_12"
0x892a6  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x892ab  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlImage::set_Alt(string)
0x892b0  ldarg.0
0x892b1  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlImage Microsoft.Crm.Web.Tools.Admin.OptionalFeaturesPage::previewImageThumbnail1
0x892b6  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x892bb  ldstr    aImgsToolsUxscr_0// "/_imgs/tools/UXScreenshots/UXScreenshot"...
0x892c0  ldc.i4.1
0x892c1  newarr   [mscorlib]System.Object
0x892c6  dup
0x892c7  ldc.i4.0
0x892c8  ldloc.0
0x892c9  box      [mscorlib]System.Int32
0x892ce  stelem.ref
0x892cf  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x892d4  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlImage::set_Src(string)
0x892d9  ldarg.0
0x892da  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlImage Microsoft.Crm.Web.Tools.Admin.OptionalFeaturesPage::previewImage
0x892df  ldarg.0
0x892e0  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x892e5  ldstr    aOptionalfeatur_3// "OptionalFeatures.aspx_Preview_12"
0x892ea  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x892ef  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlImage::set_Alt(string)
0x892f4  ldarg.0
0x892f5  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlImage Microsoft.Crm.Web.Tools.Admin.OptionalFeaturesPage::previewImage
0x892fa  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x892ff  ldstr    aImgsToolsUxscr_1// "/_imgs/tools/UXScreenshots/UXScreenshot"...
0x89304  ldc.i4.1
0x89305  newarr   [mscorlib]System.Object
0x8930a  dup
0x8930b  ldc.i4.0
0x8930c  ldloc.0
0x8930d  box      [mscorlib]System.Int32
0x89312  stelem.ref
0x89313  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x89318  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlImage::set_Src(string)
0x8931d  ldarg.0
0x8931e  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlImage Microsoft.Crm.Web.Tools.Admin.OptionalFeaturesPage::previewImage1
0x89323  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x89328  ldstr    aImgsToolsUxscr_2// "/_imgs/tools/UXScreenshots/UXScreenshot"...
0x8932d  ldc.i4.1
0x8932e  newarr   [mscorlib]System.Object
0x89333  dup
0x89334  ldc.i4.0
0x89335  ldloc.0
0x89336  box      [mscorlib]System.Int32
0x8933b  stelem.ref
0x8933c  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x89341  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlImage::set_Src(string)
0x89346  ldarg.0
0x89347  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlImage Microsoft.Crm.Web.Tools.Admin.OptionalFeaturesPage::previewImage1
0x8934c  ldarg.0
0x8934d  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x89352  ldstr    aOptionalfeatur_3// "OptionalFeatures.aspx_Preview_12"
0x89357  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x8935c  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlImage::set_Alt(string)
0x89361  ldarg.0
0x89362  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlAnchor Microsoft.Crm.Web.Tools.Admin.OptionalFeaturesPage::lookAndFeelExampleLink
0x89367  ldarg.0
0x89368  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x8936d  ldstr    aOptionalfeatur_4// "OptionalFeatures.aspx_Link_12"
0x89372  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x89377  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string)
0x8937c  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlAnchor::set_HRef(string)
0x89381  ldarg.0
0x89382  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlAnchor Microsoft.Crm.Web.Tools.Admin.OptionalFeaturesPage::salesAndServiceExampleLink
0x89387  ldarg.0
0x89388  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x8938d  ldstr    aOptionalfeatur_5// "OptionalFeatures.aspx_Link_13"
0x89392  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x89397  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string)
0x8939c  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlAnchor::set_HRef(string)
0x893a1  ldarg.0
0x893a2  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlImage Microsoft.Crm.Web.Tools.Admin.OptionalFeaturesPage::hidePreviewLinkImage
0x893a7  ldarg.0
0x893a8  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x893ad  ldstr    aOptionalfeatur_6// "OptionalFeatures.aspx_Preview_110"
0x893b2  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x893b7  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlImage::set_Alt(string)
0x893bc  ldarg.0
0x893bd  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlAnchor Microsoft.Crm.Web.Tools.Admin.OptionalFeaturesPage::previewLookAndFeelExampleLink
0x893c2  ldarg.0
0x893c3  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x893c8  ldstr    aOptionalfeatur_4// "OptionalFeatures.aspx_Link_12"
0x893cd  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x893d2  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string)
0x893d7  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlAnchor::set_HRef(string)
0x893dc  ldarg.0
0x893dd  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlAnchor Microsoft.Crm.Web.Tools.Admin.OptionalFeaturesPage::previewLookAndFeelExampleLink1
0x893e2  ldarg.0
0x893e3  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x893e8  ldstr    aOptionalfeatur_5// "OptionalFeatures.aspx_Link_13"
0x893ed  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x893f2  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string)
0x893f7  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlAnchor::set_HRef(string)
0x893fc  ldarg.0
0x893fd  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlAnchor Microsoft.Crm.Web.Tools.Admin.OptionalFeaturesPage::customizationMigrationLink2
0x89402  ldarg.0
0x89403  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x89408  ldstr    aOptionalfeatur_7// "OptionalFeatures.aspx_Link_41"
0x8940d  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x89412  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string)
0x89417  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlAnchor::set_HRef(string)
0x8941c  ldarg.0
0x8941d  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlAnchor Microsoft.Crm.Web.Tools.Admin.OptionalFeaturesPage::supportLink
0x89422  ldarg.0
0x89423  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x89428  ldstr    aOptionalfeatur_8// "OptionalFeatures.aspx_Link_61"
0x8942d  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x89432  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string)
0x89437  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlAnchor::set_HRef(string)
0x8943c  ldarg.0
0x8943d  ldarg.0
0x8943e  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x89443  ldstr    aOptionalfeatur_9// "OptionalFeatures.aspx_Link_31"
0x89448  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x8944d  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string)
0x89452  call     instance void Microsoft.Crm.Web.Tools.Admin.OptionalFeaturesPage::set_VideoLink(string value)
0x89457  ldarg.0
0x89458  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlGenericControl Microsoft.Crm.Web.Tools.Admin.OptionalFeaturesPage::videoSectionDiv
0x8945d  ldloc.0
0x8945e  ldc.i4   0x409
0x89463  ceq
0x89465  callvirt instance void [System.Web]System.Web.UI.Control::set_Visible(bool)
0x8946a  ret
```
