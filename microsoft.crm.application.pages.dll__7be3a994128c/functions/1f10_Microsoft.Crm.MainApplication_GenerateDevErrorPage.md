# Microsoft.Crm.MainApplication::GenerateDevErrorPage

- ea: `0x1f10`
- end: `0x20de`
- name: `Microsoft.Crm.MainApplication::GenerateDevErrorPage`
- size: `462`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callees

- `0x1d80`
- `0x1da0`
- `0x1f10`
- `0x20e0`

## string_xrefs

- `0x201b`: `position:absolute;\n		top:12px;\n		bottom:12px;\n		min-width:500px;\n	}\n	#ifmDebug\n	{\n		width: 100%;\n		height: 100%;\n	}\n	.ifrmContainerDiv\n	{\n		padding-top: 16px;\n		border: #999999 1px solid;\n		position: absolute;\n		top: 48px;\n		bottom: 0px;\n		left: 0px;\n		right: 0px;\n		overflow: hidden;\n	}\n</style>\n<script type="text/javascript" src="/_common/global.ashx"></script>\n<script language="JavaScript" type="text/javascript">\n	var _o;\n\n	window.onload = fu`
- `0x2024`: `/_common/error/devError.aspx`
- `0x2041`: `,"errInfo","width=620,height=420,menubar=1,status=1,resizable=1");\n	}\n\n	function copyToClipboard()\n	{\n		var iframeDubug = XUI.Html.DomUtils.GetFirstChild(document.getElementById("ifrmDebug").contentWindow.document);\n		var debugInfo = XUI.Html.GetText(iframeDubug);\n		var generalInfo = XUI.Html.GetText(document.getElementById("tabGeneral"));\n		var detailInfo = XUI.Html.GetText(document.getElementById("tabDetails"));\n		var divider = "\r\n\r\n----------------------------------\r\n\`
- `0x205e`: `;load(this);" style="cursor:pointer;" src="/_imgs/error/error_ico_userview_0.gif" vspace="6" alt="View the Error that the End User would see">\n			<img tab="tabClipboard" onmouseover="glow(this);" onmouseout="glow(this);" onclick="copyToClipboard();load(this);" style="cursor:pointer;" src="/_imgs/error/error_ico_details_0.gif" id="imgCopy" vspace="6" alt="Copy Error Data to Clipboard"><br>\n	</div>\n	<div id="spacerBar">\n		&nbsp;\n	</div>\n	<div id="contentDiv">\n			<!-- Detailed Error I`
- `0x20d2`: `"></iframe>\n				</div>\n\n			</div>\n\n			<!-- Copy to Clipboard Notification Page -->\n			<div id="tabClipboard" style="display:none;">\n\n				<table width="100%" height="100%" cellspacing="0" cellpadding="0">\n					<tr height=20>\n						<td class="header" nowrap>Copy to Clipboard:</td>\n					</tr>\n					<tr>\n						<td style="padding-top:16px;">\n							<b>The error information has been copied to the clipboard.</b>\n						</td>\n					</tr>\n				</table>\n			</div>\n	</div>`

## pseudocode

```c

```

## disassembly

```asm
0x1f10  ldarg.0
0x1f11  ldarg.1
0x1f12  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri Microsoft.Crm.MainApplication::BuildErrorHandlerUri(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Errors.ErrorInformation errorInformation)
0x1f17  stloc.0
0x1f18  ldc.i4.s 0x1B
0x1f1a  newarr   [mscorlib]System.String
0x1f1f  dup
0x1f20  ldc.i4.0
0x1f21  ldstr    aDoctypeHtmlHtm// "<!DOCTYPE html >\r\n<html>\r\n<head>\r"...
0x1f26  stelem.ref
0x1f27  dup
0x1f28  ldc.i4.1
0x1f29  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x1f2e  ldstr    aGeneral16pxFon// "General.16px.font_size"
0x1f33  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x1f38  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlEncode(string)
0x1f3d  stelem.ref
0x1f3e  dup
0x1f3f  ldc.i4.2
0x1f40  ldstr    aColorAa0000TdD// ";\r\n\t\tcolor: #aa0000;\r\n\t}\r\n\r\n"...
0x1f45  stelem.ref
0x1f46  dup
0x1f47  ldc.i4.3
0x1f48  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x1f4d  ldstr    aGeneral11pxFon// "General.11px.font_size"
0x1f52  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x1f57  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlEncode(string)
0x1f5c  stelem.ref
0x1f5d  dup
0x1f5e  ldc.i4.4
0x1f5f  ldstr    aVerticalAlignT// ";\r\n\t\tvertical-align: top;\r\n\t}\r"...
0x1f64  stelem.ref
0x1f65  dup
0x1f66  ldc.i4.5
0x1f67  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x1f6c  ldstr    aGeneral22pxFon// "General.22px.font_size"
0x1f71  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x1f76  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlEncode(string)
0x1f7b  stelem.ref
0x1f7c  dup
0x1f7d  ldc.i4.6
0x1f7e  ldstr    aFontFamilyAria// ";\r\n\t\tfont-family: Arial Black;\r\n"...
0x1f83  stelem.ref
0x1f84  dup
0x1f85  ldc.i4.7
0x1f86  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x1f8b  ldstr    aGeneral12pxFon// "General.12px.font_size"
0x1f90  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x1f95  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlEncode(string)
0x1f9a  stelem.ref
0x1f9b  dup
0x1f9c  ldc.i4.8
0x1f9d  ldstr    aColor003300Lef// ";\r\n\t\tcolor: #003300;\r\n\t}\r\n\r\n"...
0x1fa2  stelem.ref
0x1fa3  dup
0x1fa4  ldc.i4.s 9
0x1fa6  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentUICulture()
0x1fab  callvirt instance class [mscorlib]System.Globalization.TextInfo [mscorlib]System.Globalization.CultureInfo::get_TextInfo()
0x1fb0  callvirt instance bool [mscorlib]System.Globalization.TextInfo::get_IsRightToLeft()
0x1fb5  brtrue.s loc_1FBE
0x1fb7  ldstr    aBorderTopSolid// "border-top: solid 1px #BAD7BC;\r\n\t\tb"...
0x1fbc  br.s     loc_1FC3
0x1fbe  ldstr    aBorderTopSolid_0// "border-top: solid 1px #BAD7BC;\r\n\t\tb"...
0x1fc3  stelem.ref
0x1fc4  dup
0x1fc5  ldc.i4.s 0xA
0x1fc7  ldstr    aWidth76pxHeigh// "width:76px;\r\n\t\theight:98%;\r\n\t\tp"...
0x1fcc  stelem.ref
0x1fcd  dup
0x1fce  ldc.i4.s 0xB
0x1fd0  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentUICulture()
0x1fd5  callvirt instance class [mscorlib]System.Globalization.TextInfo [mscorlib]System.Globalization.CultureInfo::get_TextInfo()
0x1fda  callvirt instance bool [mscorlib]System.Globalization.TextInfo::get_IsRightToLeft()
0x1fdf  brtrue.s loc_1FE8
0x1fe1  ldstr    aBorderRightSol// "border-right: solid 1px #969693;\r\n\t"...
0x1fe6  br.s     loc_1FED
0x1fe8  ldstr    aBorderLeftSoli// "border-left: solid 1px #969693;\r\n\t\t"...
0x1fed  stelem.ref
0x1fee  dup
0x1fef  ldc.i4.s 0xC
0x1ff1  ldstr    aWidth2pxHeight// "width:2px;\r\n\t\theight:100%;\r\n\t\tp"...
0x1ff6  stelem.ref
0x1ff7  dup
0x1ff8  ldc.i4.s 0xD
0x1ffa  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentUICulture()
0x1fff  callvirt instance class [mscorlib]System.Globalization.TextInfo [mscorlib]System.Globalization.CultureInfo::get_TextInfo()
0x2004  callvirt instance bool [mscorlib]System.Globalization.TextInfo::get_IsRightToLeft()
0x2009  brtrue.s loc_2012
0x200b  ldstr    aLeft88pxRight1// "left:88px;\r\n\t\tright:12px;"
0x2010  br.s     loc_2017
0x2012  ldstr    aRight88pxLeft1// "right:88px;\r\n\t\tleft:12px;"
0x2017  stelem.ref
0x2018  dup
0x2019  ldc.i4.s 0xE
0x201b  ldstr    aPositionAbsolu// "position:absolute;\r\n\t\ttop:12px;\r\n"...
0x2020  stelem.ref
0x2021  dup
0x2022  ldc.i4.s 0xF
0x2024  ldstr    aCommonErrorDev// "/_common/error/devError.aspx"
0x2029  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x202e  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x2033  callvirt instance string [mscorlib]System.Object::ToString()
0x2038  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmJavaScriptEncode(string)
0x203d  stelem.ref
0x203e  dup
0x203f  ldc.i4.s 0x10
0x2041  ldstr    aErrinfoWidth62// ",\"errInfo\",\"width=620,height=420,men"...
0x2046  stelem.ref
0x2047  dup
0x2048  ldc.i4.s 0x11
0x204a  ldloc.0
0x204b  callvirt instance string [mscorlib]System.Object::ToString()
0x2050  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmJavaScriptEncode(string)
0x2055  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string)
0x205a  stelem.ref
0x205b  dup
0x205c  ldc.i4.s 0x12
0x205e  ldstr    aLoadThisStyleC// ";load(this);\" style=\"cursor:pointer;"...
0x2063  stelem.ref
0x2064  dup
0x2065  ldc.i4.s 0x13
0x2067  ldarg.0
0x2068  ldarg.1
0x2069  call     instance string Microsoft.Crm.MainApplication::getDevErrorDetailedInformationHtml(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Errors.ErrorInformation errorInformation)
0x206e  stelem.ref
0x206f  dup
0x2070  ldc.i4.s 0x14
0x2072  ldstr    aHttpErrorInfor// "\r\n\r\n\t\t\t<!-- HTTP Error Informati"...
0x2077  stelem.ref
0x2078  dup
0x2079  ldc.i4.s 0x15
0x207b  ldarg.0
0x207c  ldarg.1
0x207d  call     instance string Microsoft.Crm.MainApplication::getDevErrorHttpInformationHtml(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Errors.ErrorInformation errorInformation)
0x2082  stelem.ref
0x2083  dup
0x2084  ldc.i4.s 0x16
0x2086  ldstr    aDebugInformati// "\r\n\r\n\t\t\t<!-- Debug Information Pa"...
0x208b  stelem.ref
0x208c  dup
0x208d  ldc.i4.s 0x17
0x208f  ldstr    aHomeHomeDebugA// "/home/home_debug.aspx"
0x2094  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x2099  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x209e  callvirt instance string [mscorlib]System.Object::ToString()
0x20a3  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string)
0x20a8  stelem.ref
0x20a9  dup
0x20aa  ldc.i4.s 0x18
0x20ac  ldstr    aIframeDivDivEn// "\"></iframe>\r\n\t\t\t\t\t</div>\r\n\r"...
0x20b1  stelem.ref
0x20b2  dup
0x20b3  ldc.i4.s 0x19
0x20b5  ldstr    aStaticBlankHtm// "/_static/blank.htm"
0x20ba  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x20bf  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x20c4  callvirt instance string [mscorlib]System.Object::ToString()
0x20c9  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string)
0x20ce  stelem.ref
0x20cf  dup
0x20d0  ldc.i4.s 0x1A
0x20d2  ldstr    aIframeDivDivCo// "\"></iframe>\r\n\t\t\t\t</div>\r\n\r\n"...
0x20d7  stelem.ref
0x20d8  call     string [mscorlib]System.String::Concat(string[])
0x20dd  ret
```
