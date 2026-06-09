# Microsoft.Crm.Application.Components.UI.HtmlBar::Render

- ea: `0x19cb0`
- end: `0x1a005`
- name: `Microsoft.Crm.Application.Components.UI.HtmlBar::Render`
- size: `853`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x196d0`
- `0x19a90`
- `0x19ab0`
- `0x19bc0`
- `0x19bd0`
- `0x19cb0`

## string_xrefs

- `0x19d12`: `HtmlBar_Title_Copy`

## pseudocode

```c

```

## disassembly

```asm
0x19cb0  ldarg.1
0x19cb1  callvirt instance class [mscorlib]System.IO.TextWriter [System.Web]System.Web.UI.HtmlTextWriter::get_InnerWriter()
0x19cb6  stloc.0
0x19cb7  ldloc.0
0x19cb8  ldstr    aDivSpanIdHtmlb// "<div><span id=\"htmlBarSpan\" contentEd"...
0x19cbd  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x19cc2  ldarg.0
0x19cc3  ldc.i4.0
0x19cc4  stfld    bool Microsoft.Crm.Application.Components.UI.HtmlBar::_allowSpacer
0x19cc9  ldarg.0
0x19cca  ldarg.1
0x19ccb  callvirt instance void Microsoft.Crm.Application.Components.UI.HtmlBar::RenderPreControls(class [System.Web]System.Web.UI.HtmlTextWriter output)
0x19cd0  ldarg.0
0x19cd1  ldfld    valuetype HtmlBarParam Microsoft.Crm.Application.Components.UI.HtmlBar::_options
0x19cd6  ldc.i4   0x80
0x19cdb  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.General::CheckBit(unsigned int32, unsigned int32)
0x19ce0  brfalse.s loc_19D44
0x19ce2  ldarg.0
0x19ce3  ldloc.0
0x19ce4  call     instance void Microsoft.Crm.Application.Components.UI.HtmlBar::AddSpacer(class [mscorlib]System.IO.TextWriter output)
0x19ce9  ldarg.0
0x19cea  ldloc.0
0x19ceb  ldstr    aCut// "cut"
0x19cf0  ldarg.0
0x19cf1  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Components.UI.HtmlBar::_rm
0x19cf6  ldstr    aHtmlbarTitleCu// "HtmlBar_Title_Cut"
0x19cfb  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x19d00  call     instance void Microsoft.Crm.Application.Components.UI.HtmlBar::AddButton(class [mscorlib]System.IO.TextWriter output, string command, string title)
0x19d05  ldarg.0
0x19d06  ldloc.0
0x19d07  ldstr    aCopy// "copy"
0x19d0c  ldarg.0
0x19d0d  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Components.UI.HtmlBar::_rm
0x19d12  ldstr    aHtmlbarTitleCo// "HtmlBar_Title_Copy"
0x19d17  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x19d1c  call     instance void Microsoft.Crm.Application.Components.UI.HtmlBar::AddButton(class [mscorlib]System.IO.TextWriter output, string command, string title)
0x19d21  ldarg.0
0x19d22  ldloc.0
0x19d23  ldstr    aPaste// "paste"
0x19d28  ldarg.0
0x19d29  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Components.UI.HtmlBar::_rm
0x19d2e  ldstr    aHtmlbarTitlePa// "HtmlBar_Title_Paste"
0x19d33  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x19d38  call     instance void Microsoft.Crm.Application.Components.UI.HtmlBar::AddButton(class [mscorlib]System.IO.TextWriter output, string command, string title)
0x19d3d  ldarg.0
0x19d3e  ldc.i4.1
0x19d3f  stfld    bool Microsoft.Crm.Application.Components.UI.HtmlBar::_allowSpacer
0x19d44  ldarg.0
0x19d45  ldfld    valuetype HtmlBarParam Microsoft.Crm.Application.Components.UI.HtmlBar::_options
0x19d4a  ldc.i4.1
0x19d4b  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.General::CheckBit(unsigned int32, unsigned int32)
0x19d50  brfalse.s loc_19DB4
0x19d52  ldarg.0
0x19d53  ldloc.0
0x19d54  call     instance void Microsoft.Crm.Application.Components.UI.HtmlBar::AddSpacer(class [mscorlib]System.IO.TextWriter output)
0x19d59  ldarg.0
0x19d5a  ldloc.0
0x19d5b  ldstr    aBold// "bold"
0x19d60  ldarg.0
0x19d61  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Components.UI.HtmlBar::_rm
0x19d66  ldstr    aHtmlbarTitleBo// "HtmlBar_Title_Bold"
0x19d6b  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x19d70  call     instance void Microsoft.Crm.Application.Components.UI.HtmlBar::AddButton(class [mscorlib]System.IO.TextWriter output, string command, string title)
0x19d75  ldarg.0
0x19d76  ldloc.0
0x19d77  ldstr    aItalic// "italic"
0x19d7c  ldarg.0
0x19d7d  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Components.UI.HtmlBar::_rm
0x19d82  ldstr    aHtmlbarTitleIt// "HtmlBar_Title_Italic"
0x19d87  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x19d8c  call     instance void Microsoft.Crm.Application.Components.UI.HtmlBar::AddButton(class [mscorlib]System.IO.TextWriter output, string command, string title)
0x19d91  ldarg.0
0x19d92  ldloc.0
0x19d93  ldstr    aUnderline// "underline"
0x19d98  ldarg.0
0x19d99  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Components.UI.HtmlBar::_rm
0x19d9e  ldstr    aHtmlbarTitleUn// "HtmlBar_Title_Underline"
0x19da3  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x19da8  call     instance void Microsoft.Crm.Application.Components.UI.HtmlBar::AddButton(class [mscorlib]System.IO.TextWriter output, string command, string title)
0x19dad  ldarg.0
0x19dae  ldc.i4.1
0x19daf  stfld    bool Microsoft.Crm.Application.Components.UI.HtmlBar::_allowSpacer
0x19db4  ldarg.0
0x19db5  ldfld    valuetype HtmlBarParam Microsoft.Crm.Application.Components.UI.HtmlBar::_options
0x19dba  ldc.i4.s 0x40
0x19dbc  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.General::CheckBit(unsigned int32, unsigned int32)
0x19dc1  brfalse  loc_19E8F
0x19dc6  ldarg.0
0x19dc7  ldloc.0
0x19dc8  call     instance void Microsoft.Crm.Application.Components.UI.HtmlBar::AddSpacer(class [mscorlib]System.IO.TextWriter output)
0x19dcd  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentUICulture()
0x19dd2  callvirt instance class [mscorlib]System.Globalization.TextInfo [mscorlib]System.Globalization.CultureInfo::get_TextInfo()
0x19dd7  callvirt instance bool [mscorlib]System.Globalization.TextInfo::get_IsRightToLeft()
0x19ddc  brfalse.s loc_19E34
0x19dde  ldarg.0
0x19ddf  ldloc.0
0x19de0  ldstr    aJustifyright// "justifyRight"
0x19de5  ldarg.0
0x19de6  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Components.UI.HtmlBar::_rm
0x19deb  ldstr    aHtmlbarTitleAl// "HtmlBar_Title_AlignRight"
0x19df0  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x19df5  call     instance void Microsoft.Crm.Application.Components.UI.HtmlBar::AddButton(class [mscorlib]System.IO.TextWriter output, string command, string title)
0x19dfa  ldarg.0
0x19dfb  ldloc.0
0x19dfc  ldstr    aJustifycenter// "justifyCenter"
0x19e01  ldarg.0
0x19e02  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Components.UI.HtmlBar::_rm
0x19e07  ldstr    aHtmlbarTitleAl_0// "HtmlBar_Title_AlignCenter"
0x19e0c  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x19e11  call     instance void Microsoft.Crm.Application.Components.UI.HtmlBar::AddButton(class [mscorlib]System.IO.TextWriter output, string command, string title)
0x19e16  ldarg.0
0x19e17  ldloc.0
0x19e18  ldstr    aJustifyleft// "justifyLeft"
0x19e1d  ldarg.0
0x19e1e  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Components.UI.HtmlBar::_rm
0x19e23  ldstr    aHtmlbarTitleAl_1// "HtmlBar_Title_AlignLeft"
0x19e28  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x19e2d  call     instance void Microsoft.Crm.Application.Components.UI.HtmlBar::AddButton(class [mscorlib]System.IO.TextWriter output, string command, string title)
0x19e32  br.s     loc_19E88
0x19e34  ldarg.0
0x19e35  ldloc.0
0x19e36  ldstr    aJustifyleft// "justifyLeft"
0x19e3b  ldarg.0
0x19e3c  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Components.UI.HtmlBar::_rm
0x19e41  ldstr    aHtmlbarTitleAl_1// "HtmlBar_Title_AlignLeft"
0x19e46  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x19e4b  call     instance void Microsoft.Crm.Application.Components.UI.HtmlBar::AddButton(class [mscorlib]System.IO.TextWriter output, string command, string title)
0x19e50  ldarg.0
0x19e51  ldloc.0
0x19e52  ldstr    aJustifycenter// "justifyCenter"
0x19e57  ldarg.0
0x19e58  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Components.UI.HtmlBar::_rm
0x19e5d  ldstr    aHtmlbarTitleAl_0// "HtmlBar_Title_AlignCenter"
0x19e62  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x19e67  call     instance void Microsoft.Crm.Application.Components.UI.HtmlBar::AddButton(class [mscorlib]System.IO.TextWriter output, string command, string title)
0x19e6c  ldarg.0
0x19e6d  ldloc.0
0x19e6e  ldstr    aJustifyright// "justifyRight"
0x19e73  ldarg.0
0x19e74  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Components.UI.HtmlBar::_rm
0x19e79  ldstr    aHtmlbarTitleAl// "HtmlBar_Title_AlignRight"
0x19e7e  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x19e83  call     instance void Microsoft.Crm.Application.Components.UI.HtmlBar::AddButton(class [mscorlib]System.IO.TextWriter output, string command, string title)
0x19e88  ldarg.0
0x19e89  ldc.i4.1
0x19e8a  stfld    bool Microsoft.Crm.Application.Components.UI.HtmlBar::_allowSpacer
0x19e8f  ldarg.0
0x19e90  ldfld    valuetype HtmlBarParam Microsoft.Crm.Application.Components.UI.HtmlBar::_options
0x19e95  ldc.i4.s 0x20
0x19e97  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.General::CheckBit(unsigned int32, unsigned int32)
0x19e9c  brfalse.s loc_19EE4
0x19e9e  ldarg.0
0x19e9f  ldloc.0
0x19ea0  call     instance void Microsoft.Crm.Application.Components.UI.HtmlBar::AddSpacer(class [mscorlib]System.IO.TextWriter output)
0x19ea5  ldarg.0
0x19ea6  ldloc.0
0x19ea7  ldstr    aInsertorderedl// "insertOrderedList"
0x19eac  ldarg.0
0x19ead  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Components.UI.HtmlBar::_rm
0x19eb2  ldstr    aHtmlbarTitleIn// "HtmlBar_Title_InsertOrderedList"
0x19eb7  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x19ebc  call     instance void Microsoft.Crm.Application.Components.UI.HtmlBar::AddButton(class [mscorlib]System.IO.TextWriter output, string command, string title)
0x19ec1  ldarg.0
0x19ec2  ldloc.0
0x19ec3  ldstr    aInsertunordere// "insertUnorderedList"
0x19ec8  ldarg.0
0x19ec9  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Components.UI.HtmlBar::_rm
0x19ece  ldstr    aHtmlbarTitleIn_0// "HtmlBar_Title_InsertUnorderedList"
0x19ed3  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x19ed8  call     instance void Microsoft.Crm.Application.Components.UI.HtmlBar::AddButton(class [mscorlib]System.IO.TextWriter output, string command, string title)
0x19edd  ldarg.0
0x19ede  ldc.i4.1
0x19edf  stfld    bool Microsoft.Crm.Application.Components.UI.HtmlBar::_allowSpacer
0x19ee4  ldarg.0
0x19ee5  ldfld    valuetype HtmlBarParam Microsoft.Crm.Application.Components.UI.HtmlBar::_options
0x19eea  ldc.i4.s 0x10
0x19eec  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.General::CheckBit(unsigned int32, unsigned int32)
0x19ef1  brfalse.s loc_19F39
0x19ef3  ldarg.0
0x19ef4  ldloc.0
0x19ef5  call     instance void Microsoft.Crm.Application.Components.UI.HtmlBar::AddSpacer(class [mscorlib]System.IO.TextWriter output)
0x19efa  ldarg.0
0x19efb  ldloc.0
0x19efc  ldstr    aIndent// "indent"
0x19f01  ldarg.0
0x19f02  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Components.UI.HtmlBar::_rm
0x19f07  ldstr    aHtmlbarTitleIn_1// "HtmlBar_Title_Indent"
0x19f0c  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x19f11  call     instance void Microsoft.Crm.Application.Components.UI.HtmlBar::AddButton(class [mscorlib]System.IO.TextWriter output, string command, string title)
0x19f16  ldarg.0
0x19f17  ldloc.0
0x19f18  ldstr    aOutdent// "outdent"
0x19f1d  ldarg.0
0x19f1e  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Components.UI.HtmlBar::_rm
0x19f23  ldstr    aHtmlbarTitleOu// "HtmlBar_Title_Outdent"
0x19f28  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x19f2d  call     instance void Microsoft.Crm.Application.Components.UI.HtmlBar::AddButton(class [mscorlib]System.IO.TextWriter output, string command, string title)
0x19f32  ldarg.0
0x19f33  ldc.i4.1
0x19f34  stfld    bool Microsoft.Crm.Application.Components.UI.HtmlBar::_allowSpacer
0x19f39  ldarg.0
0x19f3a  ldfld    valuetype HtmlBarParam Microsoft.Crm.Application.Components.UI.HtmlBar::_options
0x19f3f  ldc.i4.8
0x19f40  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.General::CheckBit(unsigned int32, unsigned int32)
0x19f45  brtrue.s loc_19F66
0x19f47  ldarg.0
0x19f48  ldfld    valuetype HtmlBarParam Microsoft.Crm.Application.Components.UI.HtmlBar::_options
0x19f4d  ldc.i4.4
0x19f4e  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.General::CheckBit(unsigned int32, unsigned int32)
0x19f53  brtrue.s loc_19F66
0x19f55  ldarg.0
0x19f56  ldfld    valuetype HtmlBarParam Microsoft.Crm.Application.Components.UI.HtmlBar::_options
0x19f5b  ldc.i4.2
0x19f5c  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.General::CheckBit(unsigned int32, unsigned int32)
0x19f61  brfalse  loc_19FF2
0x19f66  ldarg.0
0x19f67  ldloc.0
0x19f68  call     instance void Microsoft.Crm.Application.Components.UI.HtmlBar::AddSpacer(class [mscorlib]System.IO.TextWriter output)
0x19f6d  ldarg.0
0x19f6e  ldfld    valuetype HtmlBarParam Microsoft.Crm.Application.Components.UI.HtmlBar::_options
0x19f73  ldc.i4.8
0x19f74  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.General::CheckBit(unsigned int32, unsigned int32)
0x19f79  brfalse.s loc_19F97
0x19f7b  ldarg.0
0x19f7c  ldloc.0
0x19f7d  ldstr    aFontname// "fontName"
0x19f82  ldarg.0
0x19f83  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Components.UI.HtmlBar::_rm
0x19f88  ldstr    aHtmlbarTitleFo// "HtmlBar_Title_FontName"
0x19f8d  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x19f92  call     instance void Microsoft.Crm.Application.Components.UI.HtmlBar::AddDropdown(class [mscorlib]System.IO.TextWriter output, string command, string title)
0x19f97  ldarg.0
0x19f98  ldfld    valuetype HtmlBarParam Microsoft.Crm.Application.Components.UI.HtmlBar::_options
0x19f9d  ldc.i4.4
0x19f9e  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.General::CheckBit(unsigned int32, unsigned int32)
0x19fa3  brfalse.s loc_19FC1
0x19fa5  ldarg.0
0x19fa6  ldloc.0
0x19fa7  ldstr    aFontsize// "fontSize"
0x19fac  ldarg.0
0x19fad  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Components.UI.HtmlBar::_rm
0x19fb2  ldstr    aHtmlbarTitleFo_0// "HtmlBar_Title_FontSize"
0x19fb7  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x19fbc  call     instance void Microsoft.Crm.Application.Components.UI.HtmlBar::AddDropdown(class [mscorlib]System.IO.TextWriter output, string command, string title)
0x19fc1  ldarg.0
0x19fc2  ldfld    valuetype HtmlBarParam Microsoft.Crm.Application.Components.UI.HtmlBar::_options
0x19fc7  ldc.i4.2
0x19fc8  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.General::CheckBit(unsigned int32, unsigned int32)
0x19fcd  brfalse.s loc_19FEB
0x19fcf  ldarg.0
0x19fd0  ldloc.0
0x19fd1  ldstr    aForecolor// "foreColor"
0x19fd6  ldarg.0
0x19fd7  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Components.UI.HtmlBar::_rm
0x19fdc  ldstr    aHtmlbarTitleFo_1// "HtmlBar_Title_FontColor"
0x19fe1  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x19fe6  call     instance void Microsoft.Crm.Application.Components.UI.HtmlBar::AddDropdown(class [mscorlib]System.IO.TextWriter output, string command, string title)
0x19feb  ldarg.0
0x19fec  ldc.i4.1
0x19fed  stfld    bool Microsoft.Crm.Application.Components.UI.HtmlBar::_allowSpacer
0x19ff2  ldarg.0
0x19ff3  ldarg.1
0x19ff4  callvirt instance void Microsoft.Crm.Application.Components.UI.HtmlBar::RenderPostControls(class [System.Web]System.Web.UI.HtmlTextWriter output)
0x19ff9  ldloc.0
0x19ffa  ldstr    aTrTableSpanDiv// "</tr></table></span></div>"
0x19fff  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x1a004  ret
```
