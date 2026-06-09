# Microsoft.Crm.Application.Components.UI.HtmlBar::AddButton

- ea: `0x196d0`
- end: `0x19a8c`
- name: `Microsoft.Crm.Application.Components.UI.HtmlBar::AddButton`
- size: `956`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x19cb0`

## callees

- `0x196d0`
- `0x224d0`
- `0x2a390`

## pseudocode

```c

```

## disassembly

```asm
0x196d0  ldc.i4.1
0x196d1  stloc.0
0x196d2  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x196d7  brfalse.s loc_1971F
0x196d9  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x196de  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.HttpContext::get_Request()
0x196e3  brfalse.s loc_1971F
0x196e5  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x196ea  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.HttpContext::get_Request()
0x196ef  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::IsInternetExplorer(class [System.Web]System.Web.HttpRequest)
0x196f4  brtrue.s loc_1971F
0x196f6  ldarg.2
0x196f7  ldstr    aCut// "cut"
0x196fc  call     bool [mscorlib]System.String::op_Equality(string, string)
0x19701  brtrue.s loc_1971D
0x19703  ldarg.2
0x19704  ldstr    aCopy// "copy"
0x19709  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1970e  brtrue.s loc_1971D
0x19710  ldarg.2
0x19711  ldstr    aPaste// "paste"
0x19716  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1971b  brfalse.s loc_1971F
0x1971d  ldc.i4.0
0x1971e  stloc.0
0x1971f  ldarg.1
0x19720  ldstr    aTdNowrapClass// "<td nowrap class=\""
0x19725  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x1972a  ldloc.0
0x1972b  brfalse  loc_197C3
0x19730  ldarg.2
0x19731  ldstr    aBold// "bold"
0x19736  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1973b  brtrue.s loc_19757
0x1973d  ldarg.2
0x1973e  ldstr    aItalic// "italic"
0x19743  call     bool [mscorlib]System.String::op_Equality(string, string)
0x19748  brtrue.s loc_19757
0x1974a  ldarg.2
0x1974b  ldstr    aUnderline// "underline"
0x19750  call     bool [mscorlib]System.String::op_Equality(string, string)
0x19755  brfalse.s loc_19764
0x19757  ldarg.1
0x19758  ldstr    aHtmlbtnstyle// "htmlBtnStyle"
0x1975d  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x19762  br.s     loc_1976F
0x19764  ldarg.1
0x19765  ldstr    aHtmlbtn// "htmlBtn"
0x1976a  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x1976f  ldarg.2
0x19770  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string)
0x19775  stloc.1
0x19776  ldc.i4.5
0x19777  newarr   [mscorlib]System.String
0x1977c  dup
0x1977d  ldc.i4.0
0x1977e  ldstr    aTryFindGet// "try{ $find($get('"
0x19783  stelem.ref
0x19784  dup
0x19785  ldc.i4.1
0x19786  ldstr    aHtmlbar// "HTMLBAR"
0x1978b  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmJavaScriptEncodeNoQuotes(string)
0x19790  stelem.ref
0x19791  dup
0x19792  ldc.i4.2
0x19793  ldstr    aIdHtmlexecute// "').id).htmlExecute('"
0x19798  stelem.ref
0x19799  dup
0x1979a  ldc.i4.3
0x1979b  ldloc.1
0x1979c  stelem.ref
0x1979d  dup
0x1979e  ldc.i4.4
0x1979f  ldstr    aNullCatchE// "', null); }catch(e){}"
0x197a4  stelem.ref
0x197a5  call     string [mscorlib]System.String::Concat(string[])
0x197aa  stloc.2
0x197ab  ldarg.1
0x197ac  ldstr    aOnclick// "\" onclick=\""
0x197b1  ldloc.2
0x197b2  ldstr    asc_32802// "\""
0x197b7  call     string [mscorlib]System.String::Concat(string, string, string)
0x197bc  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x197c1  br.s     loc_197CE
0x197c3  ldarg.1
0x197c4  ldstr    aHtmlbtndisable// "htmlBtnDisabled"
0x197c9  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x197ce  ldarg.1
0x197cf  ldstr    aStyleWidth24px// "\" style=\"width:24px;\"><a class=\"htm"...
0x197d4  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x197d9  ldarg.3
0x197da  ldarg.1
0x197db  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string, class [mscorlib]System.IO.TextWriter)
0x197e0  ldarg.1
0x197e1  ldstr    asc_42682// "\">"
0x197e6  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x197eb  ldarg.2
0x197ec  call     unsigned int32 <PrivateImplementationDetails>::ComputeStringHash(string s)
0x197f1  stloc.3
0x197f2  ldloc.3
0x197f3  ldc.i4   0x8681767C
0x197f8  bgt.un.s loc_1981D
0x197fa  ldloc.3
0x197fb  ldc.i4   0x16FF7DBB
0x19800  beq      loc_198BB
0x19805  ldloc.3
0x19806  ldc.i4   0x60E9FB6D
0x1980b  beq.s    loc_19867
0x1980d  ldloc.3
0x1980e  ldc.i4   0x8681767C
0x19813  beq      loc_198A6
0x19818  br       loc_19A51
0x1981d  ldloc.3
0x1981e  ldc.i4   0xDE96F676
0x19823  bgt.un.s loc_1983A
0x19825  ldloc.3
0x19826  ldc.i4   0xBD3A7AAD
0x1982b  beq.s    loc_19891
0x1982d  ldloc.3
0x1982e  ldc.i4   0xDE96F676
0x19833  beq.s    loc_19852
0x19835  br       loc_19A51
0x1983a  ldloc.3
0x1983b  ldc.i4   0xE582347F
0x19840  beq.s    loc_1987C
0x19842  ldloc.3
0x19843  ldc.i4   0xE8039176
0x19848  beq      loc_198D0
0x1984d  br       loc_19A51
0x19852  ldarg.2
0x19853  ldstr    aBold// "bold"
0x19858  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1985d  brtrue   loc_198E5
0x19862  br       loc_19A51
0x19867  ldarg.2
0x19868  ldstr    aItalic// "italic"
0x1986d  call     bool [mscorlib]System.String::op_Equality(string, string)
0x19872  brtrue   loc_19916
0x19877  br       loc_19A51
0x1987c  ldarg.2
0x1987d  ldstr    aUnderline// "underline"
0x19882  call     bool [mscorlib]System.String::op_Equality(string, string)
0x19887  brtrue   loc_19947
0x1988c  br       loc_19A51
0x19891  ldarg.2
0x19892  ldstr    aInsertorderedl// "insertOrderedList"
0x19897  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1989c  brtrue   loc_19978
0x198a1  br       loc_19A51
0x198a6  ldarg.2
0x198a7  ldstr    aInsertunordere// "insertUnorderedList"
0x198ac  call     bool [mscorlib]System.String::op_Equality(string, string)
0x198b1  brtrue   loc_199D5
0x198b6  br       loc_19A51
0x198bb  ldarg.2
0x198bc  ldstr    aIndent// "indent"
0x198c1  call     bool [mscorlib]System.String::op_Equality(string, string)
0x198c6  brtrue   loc_199D5
0x198cb  br       loc_19A51
0x198d0  ldarg.2
0x198d1  ldstr    aOutdent// "outdent"
0x198d6  call     bool [mscorlib]System.String::op_Equality(string, string)
0x198db  brtrue   loc_199D5
0x198e0  br       loc_19A51
0x198e5  ldarg.1
0x198e6  ldstr    aBClassHtmlimgs// "<b class='htmlImgStyle' style ='display"...
0x198eb  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x198f0  ldarg.0
0x198f1  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Components.UI.HtmlBar::_rm
0x198f6  ldstr    aHtmlbarLabelBo// "HtmlBar_Label_Bold"
0x198fb  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x19900  ldarg.1
0x19901  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlEncode(string, class [mscorlib]System.IO.TextWriter)
0x19906  ldarg.1
0x19907  ldstr    aB// "</b>"
0x1990c  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x19911  br       loc_19A80
0x19916  ldarg.1
0x19917  ldstr    aBClassHtmlimgs_0// "<b class='htmlImgStyle' style ='display"...
0x1991c  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x19921  ldarg.0
0x19922  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Components.UI.HtmlBar::_rm
0x19927  ldstr    aHtmlbarLabelIt// "HtmlBar_Label_Italic"
0x1992c  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x19931  ldarg.1
0x19932  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlEncode(string, class [mscorlib]System.IO.TextWriter)
0x19937  ldarg.1
0x19938  ldstr    aIB// "</i></b>"
0x1993d  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x19942  br       loc_19A80
0x19947  ldarg.1
0x19948  ldstr    aBClassHtmlimgs_1// "<b class='htmlImgStyle' style ='display"...
0x1994d  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x19952  ldarg.0
0x19953  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Components.UI.HtmlBar::_rm
0x19958  ldstr    aHtmlbarLabelUn// "HtmlBar_Label_Underline"
0x1995d  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x19962  ldarg.1
0x19963  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlEncode(string, class [mscorlib]System.IO.TextWriter)
0x19968  ldarg.1
0x19969  ldstr    aUB// "</u></b>"
0x1996e  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x19973  br       loc_19A80
0x19978  ldarg.1
0x19979  ldstr    aImgClassHtmlim// "<img class='htmlImgStyle' alt=\""
0x1997e  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x19983  ldarg.3
0x19984  ldarg.1
0x19985  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string, class [mscorlib]System.IO.TextWriter)
0x1998a  ldarg.1
0x1998b  ldstr    aSrcImgsHtmlbar// "\" src=\"/_imgs/htmlbar/cmd-"
0x19990  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x19995  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentUICulture()
0x1999a  callvirt instance class [mscorlib]System.Globalization.TextInfo [mscorlib]System.Globalization.CultureInfo::get_TextInfo()
0x1999f  callvirt instance bool [mscorlib]System.Globalization.TextInfo::get_IsRightToLeft()
0x199a4  brfalse.s loc_199B3
0x199a6  ldstr    aInsertorderedl_0// "insertOrderedListRTL"
0x199ab  ldarg.1
0x199ac  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string, class [mscorlib]System.IO.TextWriter)
0x199b1  br.s     loc_199BA
0x199b3  ldarg.2
0x199b4  ldarg.1
0x199b5  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string, class [mscorlib]System.IO.TextWriter)
0x199ba  ldarg.1
0x199bb  ldstr    aGif// ".gif\""
0x199c0  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x199c5  ldarg.1
0x199c6  ldstr    asc_52770// "/>"
0x199cb  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x199d0  br       loc_19A80
0x199d5  ldarg.1
0x199d6  ldstr    aImgClassHtmlim// "<img class='htmlImgStyle' alt=\""
0x199db  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x199e0  ldarg.3
0x199e1  ldarg.1
0x199e2  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string, class [mscorlib]System.IO.TextWriter)
0x199e7  ldarg.1
0x199e8  ldstr    aSrcImgsHtmlbar// "\" src=\"/_imgs/htmlbar/cmd-"
0x199ed  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x199f2  ldarg.2
0x199f3  ldarg.1
0x199f4  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string, class [mscorlib]System.IO.TextWriter)
0x199f9  ldarg.1
0x199fa  ldstr    aGif// ".gif\""
0x199ff  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x19a04  ldarg.1
0x19a05  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentUICulture()
0x19a0a  callvirt instance class [mscorlib]System.Globalization.TextInfo [mscorlib]System.Globalization.CultureInfo::get_TextInfo()
0x19a0f  callvirt instance bool [mscorlib]System.Globalization.TextInfo::get_IsRightToLeft()
0x19a14  brtrue.s loc_19A1D
0x19a16  ldsfld   string [mscorlib]System.String::Empty
0x19a1b  br.s     loc_19A36
0x19a1d  ldstr    aStyle_1// "style=\""
0x19a22  ldstr    aH// "h"
0x19a27  call     string Microsoft.Crm.Application.Components.UI.SharedMethods::FlipImage(string direction)
0x19a2c  ldstr    asc_32802// "\""
0x19a31  call     string [mscorlib]System.String::Concat(string, string, string)
0x19a36  dup
0x19a37  brtrue.s loc_19A3F
0x19a39  pop
0x19a3a  ldstr    asc_3280A// ""
0x19a3f  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x19a44  ldarg.1
0x19a45  ldstr    asc_52770// "/>"
0x19a4a  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x19a4f  br.s     loc_19A80
0x19a51  ldarg.1
0x19a52  ldstr    aImgClassHtmlim// "<img class='htmlImgStyle' alt=\""
0x19a57  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x19a5c  ldarg.3
0x19a5d  ldarg.1
0x19a5e  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string, class [mscorlib]System.IO.TextWriter)
0x19a63  ldarg.1
0x19a64  ldstr    aSrcImgsHtmlbar// "\" src=\"/_imgs/htmlbar/cmd-"
0x19a69  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x19a6e  ldarg.2
0x19a6f  ldarg.1
0x19a70  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string, class [mscorlib]System.IO.TextWriter)
0x19a75  ldarg.1
0x19a76  ldstr    aGif_0// ".gif\"/>"
0x19a7b  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x19a80  ldarg.1
0x19a81  ldstr    aATd// "</a></td>"
0x19a86  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x19a8b  ret
```
