# Microsoft.Crm.Common.Application.Pages.Common.CrmStyles::GetStyleCss

- ea: `0x1ca60`
- end: `0x1cd48`
- name: `Microsoft.Crm.Common.Application.Pages.Common.CrmStyles::GetStyleCss`
- size: `744`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `broker_com_uri`

## callees

- `0x1c9d0`
- `0x1ca60`
- `0x1cdd0`
- `0x1cee0`
- `0x1cf20`
- `0x1cf80`
- `0x1cfc0`
- `0x1d050`
- `0x1d090`

## pseudocode

```c

```

## disassembly

```asm
0x1ca60  ldarg.1
0x1ca61  brtrue.s loc_1CA69
0x1ca63  ldsfld   string [mscorlib]System.String::Empty
0x1ca68  ret
0x1ca69  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x1ca6e  stloc.0
0x1ca6f  ldarg.0
0x1ca70  ldloc.0
0x1ca71  ldstr    aColor// "color"
0x1ca76  ldarg.1
0x1ca77  callvirt instance valuetype [System.Drawing]System.Drawing.Color [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Themes.ThemeStyleBase::get_ForeColor()
0x1ca7c  call     instance void Microsoft.Crm.Common.Application.Pages.Common.CrmStyles::AppendCssColor(class [mscorlib]System.Text.StringBuilder themeCss, string styleName, valuetype [System.Drawing]System.Drawing.Color color)
0x1ca81  ldarg.0
0x1ca82  ldloc.0
0x1ca83  ldstr    aBackgroundColo_0// "background-color"
0x1ca88  ldarg.1
0x1ca89  callvirt instance valuetype [System.Drawing]System.Drawing.Color [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Themes.ThemeStyleBase::get_BackColor()
0x1ca8e  call     instance void Microsoft.Crm.Common.Application.Pages.Common.CrmStyles::AppendCssColor(class [mscorlib]System.Text.StringBuilder themeCss, string styleName, valuetype [System.Drawing]System.Drawing.Color color)
0x1ca93  ldarg.0
0x1ca94  ldloc.0
0x1ca95  ldstr    aBorderColor// "border-color"
0x1ca9a  ldarg.1
0x1ca9b  callvirt instance valuetype [System.Drawing]System.Drawing.Color [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Themes.ThemeStyleBase::get_BorderColor()
0x1caa0  call     instance void Microsoft.Crm.Common.Application.Pages.Common.CrmStyles::AppendCssColor(class [mscorlib]System.Text.StringBuilder themeCss, string styleName, valuetype [System.Drawing]System.Drawing.Color color)
0x1caa5  ldarg.0
0x1caa6  ldloc.0
0x1caa7  ldstr    aBorderWidth// "border-width"
0x1caac  ldarg.1
0x1caad  callvirt instance valuetype [mscorlib]System.Nullable`1<float64> [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Themes.ThemeStyleBase::get_BorderWidth()
0x1cab2  call     instance void Microsoft.Crm.Common.Application.Pages.Common.CrmStyles::AppendCssNumberValue(class [mscorlib]System.Text.StringBuilder themeCss, string styleName, valuetype [mscorlib]System.Nullable`1<float64> number)
0x1cab7  ldarg.0
0x1cab8  ldloc.0
0x1cab9  ldstr    aBorderStyle// "border-style"
0x1cabe  ldarg.1
0x1cabf  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Themes.CssBorderStyle> [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Themes.ThemeStyleBase::get_BorderStyle()
0x1cac4  call     instance void Microsoft.Crm.Common.Application.Pages.Common.CrmStyles::AppendCssBorderStyle(class [mscorlib]System.Text.StringBuilder themeCss, string styleName, valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Themes.CssBorderStyle> borderStyle)
0x1cac9  ldarg.0
0x1caca  ldloc.0
0x1cacb  ldstr    aBorderTopColor// "border-top-color"
0x1cad0  ldarg.1
0x1cad1  callvirt instance valuetype [System.Drawing]System.Drawing.Color [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Themes.ThemeStyleBase::get_BorderTopColor()
0x1cad6  call     instance void Microsoft.Crm.Common.Application.Pages.Common.CrmStyles::AppendCssColor(class [mscorlib]System.Text.StringBuilder themeCss, string styleName, valuetype [System.Drawing]System.Drawing.Color color)
0x1cadb  ldarg.0
0x1cadc  ldloc.0
0x1cadd  ldstr    aBorderTopWidth// "border-top-width"
0x1cae2  ldarg.1
0x1cae3  callvirt instance valuetype [mscorlib]System.Nullable`1<float64> [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Themes.ThemeStyleBase::get_BorderTopWidth()
0x1cae8  call     instance void Microsoft.Crm.Common.Application.Pages.Common.CrmStyles::AppendCssNumberValue(class [mscorlib]System.Text.StringBuilder themeCss, string styleName, valuetype [mscorlib]System.Nullable`1<float64> number)
0x1caed  ldarg.0
0x1caee  ldloc.0
0x1caef  ldstr    aBorderTopStyle// "border-top-style"
0x1caf4  ldarg.1
0x1caf5  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Themes.CssBorderStyle> [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Themes.ThemeStyleBase::get_BorderTopStyle()
0x1cafa  call     instance void Microsoft.Crm.Common.Application.Pages.Common.CrmStyles::AppendCssBorderStyle(class [mscorlib]System.Text.StringBuilder themeCss, string styleName, valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Themes.CssBorderStyle> borderStyle)
0x1caff  ldarg.0
0x1cb00  ldloc.0
0x1cb01  ldstr    aBorderBottomCo// "border-bottom-color"
0x1cb06  ldarg.1
0x1cb07  callvirt instance valuetype [System.Drawing]System.Drawing.Color [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Themes.ThemeStyleBase::get_BorderBottomColor()
0x1cb0c  call     instance void Microsoft.Crm.Common.Application.Pages.Common.CrmStyles::AppendCssColor(class [mscorlib]System.Text.StringBuilder themeCss, string styleName, valuetype [System.Drawing]System.Drawing.Color color)
0x1cb11  ldarg.0
0x1cb12  ldloc.0
0x1cb13  ldstr    aBorderBottomWi// "border-bottom-width"
0x1cb18  ldarg.1
0x1cb19  callvirt instance valuetype [mscorlib]System.Nullable`1<float64> [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Themes.ThemeStyleBase::get_BorderBottomWidth()
0x1cb1e  call     instance void Microsoft.Crm.Common.Application.Pages.Common.CrmStyles::AppendCssNumberValue(class [mscorlib]System.Text.StringBuilder themeCss, string styleName, valuetype [mscorlib]System.Nullable`1<float64> number)
0x1cb23  ldarg.0
0x1cb24  ldloc.0
0x1cb25  ldstr    aBorderBottomSt// "border-bottom-style"
0x1cb2a  ldarg.1
0x1cb2b  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Themes.CssBorderStyle> [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Themes.ThemeStyleBase::get_BorderBottomStyle()
0x1cb30  call     instance void Microsoft.Crm.Common.Application.Pages.Common.CrmStyles::AppendCssBorderStyle(class [mscorlib]System.Text.StringBuilder themeCss, string styleName, valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Themes.CssBorderStyle> borderStyle)
0x1cb35  call     bool Microsoft.Crm.Common.Application.Pages.Common.CrmStyles::get_IsRightToLeft()
0x1cb3a  brfalse.s loc_1CBAA
0x1cb3c  ldarg.0
0x1cb3d  ldloc.0
0x1cb3e  ldstr    aBorderLeftColo// "border-left-color"
0x1cb43  ldarg.1
0x1cb44  callvirt instance valuetype [System.Drawing]System.Drawing.Color [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Themes.ThemeStyleBase::get_BorderRightColor()
0x1cb49  call     instance void Microsoft.Crm.Common.Application.Pages.Common.CrmStyles::AppendCssColor(class [mscorlib]System.Text.StringBuilder themeCss, string styleName, valuetype [System.Drawing]System.Drawing.Color color)
0x1cb4e  ldarg.0
0x1cb4f  ldloc.0
0x1cb50  ldstr    aBorderLeftWidt// "border-left-width"
0x1cb55  ldarg.1
0x1cb56  callvirt instance valuetype [mscorlib]System.Nullable`1<float64> [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Themes.ThemeStyleBase::get_BorderRightWidth()
0x1cb5b  call     instance void Microsoft.Crm.Common.Application.Pages.Common.CrmStyles::AppendCssNumberValue(class [mscorlib]System.Text.StringBuilder themeCss, string styleName, valuetype [mscorlib]System.Nullable`1<float64> number)
0x1cb60  ldarg.0
0x1cb61  ldloc.0
0x1cb62  ldstr    aBorderLeftStyl// "border-left-style"
0x1cb67  ldarg.1
0x1cb68  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Themes.CssBorderStyle> [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Themes.ThemeStyleBase::get_BorderRightStyle()
0x1cb6d  call     instance void Microsoft.Crm.Common.Application.Pages.Common.CrmStyles::AppendCssBorderStyle(class [mscorlib]System.Text.StringBuilder themeCss, string styleName, valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Themes.CssBorderStyle> borderStyle)
0x1cb72  ldarg.0
0x1cb73  ldloc.0
0x1cb74  ldstr    aBorderRightCol// "border-right-color"
0x1cb79  ldarg.1
0x1cb7a  callvirt instance valuetype [System.Drawing]System.Drawing.Color [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Themes.ThemeStyleBase::get_BorderLeftColor()
0x1cb7f  call     instance void Microsoft.Crm.Common.Application.Pages.Common.CrmStyles::AppendCssColor(class [mscorlib]System.Text.StringBuilder themeCss, string styleName, valuetype [System.Drawing]System.Drawing.Color color)
0x1cb84  ldarg.0
0x1cb85  ldloc.0
0x1cb86  ldstr    aBorderRightWid// "border-right-width"
0x1cb8b  ldarg.1
0x1cb8c  callvirt instance valuetype [mscorlib]System.Nullable`1<float64> [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Themes.ThemeStyleBase::get_BorderLeftWidth()
0x1cb91  call     instance void Microsoft.Crm.Common.Application.Pages.Common.CrmStyles::AppendCssNumberValue(class [mscorlib]System.Text.StringBuilder themeCss, string styleName, valuetype [mscorlib]System.Nullable`1<float64> number)
0x1cb96  ldarg.0
0x1cb97  ldloc.0
0x1cb98  ldstr    aBorderRightSty// "border-right-style"
0x1cb9d  ldarg.1
0x1cb9e  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Themes.CssBorderStyle> [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Themes.ThemeStyleBase::get_BorderLeftStyle()
0x1cba3  call     instance void Microsoft.Crm.Common.Application.Pages.Common.CrmStyles::AppendCssBorderStyle(class [mscorlib]System.Text.StringBuilder themeCss, string styleName, valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Themes.CssBorderStyle> borderStyle)
0x1cba8  br.s     loc_1CC16
0x1cbaa  ldarg.0
0x1cbab  ldloc.0
0x1cbac  ldstr    aBorderLeftColo// "border-left-color"
0x1cbb1  ldarg.1
0x1cbb2  callvirt instance valuetype [System.Drawing]System.Drawing.Color [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Themes.ThemeStyleBase::get_BorderLeftColor()
0x1cbb7  call     instance void Microsoft.Crm.Common.Application.Pages.Common.CrmStyles::AppendCssColor(class [mscorlib]System.Text.StringBuilder themeCss, string styleName, valuetype [System.Drawing]System.Drawing.Color color)
0x1cbbc  ldarg.0
0x1cbbd  ldloc.0
0x1cbbe  ldstr    aBorderLeftWidt// "border-left-width"
0x1cbc3  ldarg.1
0x1cbc4  callvirt instance valuetype [mscorlib]System.Nullable`1<float64> [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Themes.ThemeStyleBase::get_BorderLeftWidth()
0x1cbc9  call     instance void Microsoft.Crm.Common.Application.Pages.Common.CrmStyles::AppendCssNumberValue(class [mscorlib]System.Text.StringBuilder themeCss, string styleName, valuetype [mscorlib]System.Nullable`1<float64> number)
0x1cbce  ldarg.0
0x1cbcf  ldloc.0
0x1cbd0  ldstr    aBorderLeftStyl// "border-left-style"
0x1cbd5  ldarg.1
0x1cbd6  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Themes.CssBorderStyle> [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Themes.ThemeStyleBase::get_BorderLeftStyle()
0x1cbdb  call     instance void Microsoft.Crm.Common.Application.Pages.Common.CrmStyles::AppendCssBorderStyle(class [mscorlib]System.Text.StringBuilder themeCss, string styleName, valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Themes.CssBorderStyle> borderStyle)
0x1cbe0  ldarg.0
0x1cbe1  ldloc.0
0x1cbe2  ldstr    aBorderRightCol// "border-right-color"
0x1cbe7  ldarg.1
0x1cbe8  callvirt instance valuetype [System.Drawing]System.Drawing.Color [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Themes.ThemeStyleBase::get_BorderRightColor()
0x1cbed  call     instance void Microsoft.Crm.Common.Application.Pages.Common.CrmStyles::AppendCssColor(class [mscorlib]System.Text.StringBuilder themeCss, string styleName, valuetype [System.Drawing]System.Drawing.Color color)
0x1cbf2  ldarg.0
0x1cbf3  ldloc.0
0x1cbf4  ldstr    aBorderRightWid// "border-right-width"
0x1cbf9  ldarg.1
0x1cbfa  callvirt instance valuetype [mscorlib]System.Nullable`1<float64> [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Themes.ThemeStyleBase::get_BorderRightWidth()
0x1cbff  call     instance void Microsoft.Crm.Common.Application.Pages.Common.CrmStyles::AppendCssNumberValue(class [mscorlib]System.Text.StringBuilder themeCss, string styleName, valuetype [mscorlib]System.Nullable`1<float64> number)
0x1cc04  ldarg.0
0x1cc05  ldloc.0
0x1cc06  ldstr    aBorderRightSty// "border-right-style"
0x1cc0b  ldarg.1
0x1cc0c  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Themes.CssBorderStyle> [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Themes.ThemeStyleBase::get_BorderRightStyle()
0x1cc11  call     instance void Microsoft.Crm.Common.Application.Pages.Common.CrmStyles::AppendCssBorderStyle(class [mscorlib]System.Text.StringBuilder themeCss, string styleName, valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Themes.CssBorderStyle> borderStyle)
0x1cc16  ldarg.0
0x1cc17  ldloc.0
0x1cc18  ldstr    aScrollbar3dlig// "scrollbar-3dlight-color"
0x1cc1d  ldarg.1
0x1cc1e  callvirt instance valuetype [System.Drawing]System.Drawing.Color [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Themes.ThemeStyleBase::get_ScrollBarThreeDLightColor()
0x1cc23  call     instance void Microsoft.Crm.Common.Application.Pages.Common.CrmStyles::AppendCssColor(class [mscorlib]System.Text.StringBuilder themeCss, string styleName, valuetype [System.Drawing]System.Drawing.Color color)
0x1cc28  ldarg.0
0x1cc29  ldloc.0
0x1cc2a  ldstr    aScrollbarArrow// "scrollbar-arrow-color"
0x1cc2f  ldarg.1
0x1cc30  callvirt instance valuetype [System.Drawing]System.Drawing.Color [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Themes.ThemeStyleBase::get_ScrollBarArrowColor()
0x1cc35  call     instance void Microsoft.Crm.Common.Application.Pages.Common.CrmStyles::AppendCssColor(class [mscorlib]System.Text.StringBuilder themeCss, string styleName, valuetype [System.Drawing]System.Drawing.Color color)
0x1cc3a  ldarg.0
0x1cc3b  ldloc.0
0x1cc3c  ldstr    aScrollbarBaseC// "scrollbar-base-color"
0x1cc41  ldarg.1
0x1cc42  callvirt instance valuetype [System.Drawing]System.Drawing.Color [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Themes.ThemeStyleBase::get_ScrollBarBaseColor()
0x1cc47  call     instance void Microsoft.Crm.Common.Application.Pages.Common.CrmStyles::AppendCssColor(class [mscorlib]System.Text.StringBuilder themeCss, string styleName, valuetype [System.Drawing]System.Drawing.Color color)
0x1cc4c  ldarg.0
0x1cc4d  ldloc.0
0x1cc4e  ldstr    aScrollbarDarks// "scrollbar-darkshadow-color"
0x1cc53  ldarg.1
0x1cc54  callvirt instance valuetype [System.Drawing]System.Drawing.Color [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Themes.ThemeStyleBase::get_ScrollBarDarkShadowColor()
0x1cc59  call     instance void Microsoft.Crm.Common.Application.Pages.Common.CrmStyles::AppendCssColor(class [mscorlib]System.Text.StringBuilder themeCss, string styleName, valuetype [System.Drawing]System.Drawing.Color color)
0x1cc5e  ldarg.0
0x1cc5f  ldloc.0
0x1cc60  ldstr    aScrollbarFaceC// "scrollbar-face-color"
0x1cc65  ldarg.1
0x1cc66  callvirt instance valuetype [System.Drawing]System.Drawing.Color [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Themes.ThemeStyleBase::get_ScrollBarFaceColor()
0x1cc6b  call     instance void Microsoft.Crm.Common.Application.Pages.Common.CrmStyles::AppendCssColor(class [mscorlib]System.Text.StringBuilder themeCss, string styleName, valuetype [System.Drawing]System.Drawing.Color color)
0x1cc70  ldarg.0
0x1cc71  ldloc.0
0x1cc72  ldstr    aScrollbarHighl// "scrollbar-highlight-color"
0x1cc77  ldarg.1
0x1cc78  callvirt instance valuetype [System.Drawing]System.Drawing.Color [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Themes.ThemeStyleBase::get_ScrollBarHighlightColor()
0x1cc7d  call     instance void Microsoft.Crm.Common.Application.Pages.Common.CrmStyles::AppendCssColor(class [mscorlib]System.Text.StringBuilder themeCss, string styleName, valuetype [System.Drawing]System.Drawing.Color color)
0x1cc82  ldarg.0
0x1cc83  ldloc.0
0x1cc84  ldstr    aScrollbarShado// "scrollbar-shadow-color"
0x1cc89  ldarg.1
0x1cc8a  callvirt instance valuetype [System.Drawing]System.Drawing.Color [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Themes.ThemeStyleBase::get_ScrollBarShadowColor()
0x1cc8f  call     instance void Microsoft.Crm.Common.Application.Pages.Common.CrmStyles::AppendCssColor(class [mscorlib]System.Text.StringBuilder themeCss, string styleName, valuetype [System.Drawing]System.Drawing.Color color)
0x1cc94  ldarg.0
0x1cc95  ldloc.0
0x1cc96  ldstr    aScrollbarTrack// "scrollbar-track-color"
0x1cc9b  ldarg.1
0x1cc9c  callvirt instance valuetype [System.Drawing]System.Drawing.Color [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Themes.ThemeStyleBase::get_ScrollBarTrackColor()
0x1cca1  call     instance void Microsoft.Crm.Common.Application.Pages.Common.CrmStyles::AppendCssColor(class [mscorlib]System.Text.StringBuilder themeCss, string styleName, valuetype [System.Drawing]System.Drawing.Color color)
0x1cca6  ldarg.0
0x1cca7  ldloc.0
0x1cca8  ldarg.1
0x1cca9  callvirt instance valuetype [System.Drawing]System.Drawing.Color [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Themes.ThemeStyleBase::get_BackColorGradientTop()
0x1ccae  ldarg.1
0x1ccaf  callvirt instance valuetype [System.Drawing]System.Drawing.Color [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Themes.ThemeStyleBase::get_BackColorGradientBottom()
0x1ccb4  ldc.i4.1
0x1ccb5  call     instance void Microsoft.Crm.Common.Application.Pages.Common.CrmStyles::AppendCssGradient(class [mscorlib]System.Text.StringBuilder themeCss, valuetype [System.Drawing]System.Drawing.Color startColor, valuetype [System.Drawing]System.Drawing.Color endColor, int32 orientation)
0x1ccba  ldarg.0
0x1ccbb  ldloc.0
0x1ccbc  ldarg.1
0x1ccbd  callvirt instance valuetype [System.Drawing]System.Drawing.Color [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Themes.ThemeStyleBase::get_BackColorGradientLeft()
0x1ccc2  ldarg.1
0x1ccc3  callvirt instance valuetype [System.Drawing]System.Drawing.Color [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Themes.ThemeStyleBase::get_BackColorGradientRight()
0x1ccc8  ldc.i4.1
0x1ccc9  call     instance void Microsoft.Crm.Common.Application.Pages.Common.CrmStyles::AppendCssGradient(class [mscorlib]System.Text.StringBuilder themeCss, valuetype [System.Drawing]System.Drawing.Color startColor, valuetype [System.Drawing]System.Drawing.Color endColor, int32 orientation)
0x1ccce  ldarg.0
0x1cccf  ldloc.0
0x1ccd0  ldstr    aBackgroundImag// "background-image"
0x1ccd5  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentUICulture()
0x1ccda  callvirt instance class [mscorlib]System.Globalization.TextInfo [mscorlib]System.Globalization.CultureInfo::get_TextInfo()
0x1ccdf  callvirt instance bool [mscorlib]System.Globalization.TextInfo::get_IsRightToLeft()
0x1cce4  brtrue.s loc_1CCEE
0x1cce6  ldarg.1
0x1cce7  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Themes.ThemeStyleBase::get_BackImagePath()
0x1ccec  br.s     loc_1CCF4
0x1ccee  ldarg.1
0x1ccef  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Themes.ThemeStyleBase::get_BackImagePathRtl()
0x1ccf4  call     instance void Microsoft.Crm.Common.Application.Pages.Common.CrmStyles::AppendCssImage(class [mscorlib]System.Text.StringBuilder themeCss, string styleName, class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri imageUri)
0x1ccf9  ldarg.0
0x1ccfa  ldloc.0
0x1ccfb  ldstr    aTextTransform// "text-transform"
0x1cd00  ldarg.1
0x1cd01  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Themes.CssTextTransformStyle> [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Themes.ThemeStyleBase::get_TextTransformStyle()
0x1cd06  call     instance void Microsoft.Crm.Common.Application.Pages.Common.CrmStyles::AppendCssTextTransformStyle(class [mscorlib]System.Text.StringBuilder themeCss, string styleName, valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Themes.CssTextTransformStyle> style)
0x1cd0b  ldarg.0
0x1cd0c  ldloc.0
0x1cd0d  ldstr    aColor// "color"
0x1cd12  ldarg.1
0x1cd13  callvirt instance valuetype [System.Drawing]System.Drawing.Color [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Themes.ThemeStyleBase::get_ForeColorImportant()
0x1cd18  call     instance void Microsoft.Crm.Common.Application.Pages.Common.CrmStyles::AppendCssColorImportant(class [mscorlib]System.Text.StringBuilder themeCss, string styleName, valuetype [System.Drawing]System.Drawing.Color color)
0x1cd1d  ldarg.0
0x1cd1e  ldloc.0
0x1cd1f  ldstr    aBackgroundColo_0// "background-color"
0x1cd24  ldarg.1
0x1cd25  callvirt instance valuetype [System.Drawing]System.Drawing.Color [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Themes.ThemeStyleBase::get_BackColorImportant()
0x1cd2a  call     instance void Microsoft.Crm.Common.Application.Pages.Common.CrmStyles::AppendCssColorImportant(class [mscorlib]System.Text.StringBuilder themeCss, string styleName, valuetype [System.Drawing]System.Drawing.Color color)
0x1cd2f  ldarg.0
0x1cd30  ldloc.0
0x1cd31  ldstr    aBorderColor// "border-color"
0x1cd36  ldarg.1
0x1cd37  callvirt instance valuetype [System.Drawing]System.Drawing.Color [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Themes.ThemeStyleBase::get_BorderColorImportant()
0x1cd3c  call     instance void Microsoft.Crm.Common.Application.Pages.Common.CrmStyles::AppendCssColorImportant(class [mscorlib]System.Text.StringBuilder themeCss, string styleName, valuetype [System.Drawing]System.Drawing.Color color)
0x1cd41  ldloc.0
0x1cd42  callvirt instance string [mscorlib]System.Object::ToString()
0x1cd47  ret
```
