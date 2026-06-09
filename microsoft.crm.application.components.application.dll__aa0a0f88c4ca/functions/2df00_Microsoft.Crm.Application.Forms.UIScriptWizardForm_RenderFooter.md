# Microsoft.Crm.Application.Forms.UIScriptWizardForm::RenderFooter

- ea: `0x2df00`
- end: `0x2e187`
- name: `Microsoft.Crm.Application.Forms.UIScriptWizardForm::RenderFooter`
- size: `647`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x2df00`
- `0x2e190`
- `0x2e1e0`

## string_xrefs

- `0x2dfcc`: `scriptCommentsControl`
- `0x2e010`: `scriptCommentsControl`
- `0x2df97`: `CommentsTableHeight`
- `0x2dfbb`: `Comments-Hint`
- `0x2dfe5`: `Web.UIScripts.RunScriptForm.Add_Comments`
- `0x2e021`: `Comments-Textarea`

## pseudocode

```c

```

## disassembly

```asm
0x2df00  ldarg.1
0x2df01  ldstr    aDiv_3// "div"
0x2df06  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteBeginTag(string)
0x2df0b  ldarg.1
0x2df0c  ldstr    aId_1// "id"
0x2df11  ldstr    aWizardformfoot// "wizardFormFooter"
0x2df16  ldc.i4.0
0x2df17  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x2df1c  ldarg.1
0x2df1d  ldstr    aClass_0// "class"
0x2df22  ldstr    aMsCrmWizardfor// "ms-crm-WizardForm-Footer"
0x2df27  ldc.i4.0
0x2df28  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x2df2d  ldarg.1
0x2df2e  ldc.i4.s 0x3E
0x2df30  callvirt instance void [mscorlib]System.IO.TextWriter::Write(char)
0x2df35  ldarg.1
0x2df36  ldstr    aTable_0// "table"
0x2df3b  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteBeginTag(string)
0x2df40  ldarg.1
0x2df41  ldstr    aClass_0// "class"
0x2df46  ldstr    aStdtable// "stdTable"
0x2df4b  ldc.i4.0
0x2df4c  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x2df51  ldarg.1
0x2df52  ldstr    aStyle_0// "style"
0x2df57  ldstr    aHeight120px// "height:120px;"
0x2df5c  ldc.i4.0
0x2df5d  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x2df62  ldarg.1
0x2df63  ldstr    aCellspacing// "cellspacing"
0x2df68  ldstr    a0// "0"
0x2df6d  ldc.i4.0
0x2df6e  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x2df73  ldarg.1
0x2df74  ldc.i4.s 0x3E
0x2df76  callvirt instance void [mscorlib]System.IO.TextWriter::Write(char)
0x2df7b  ldarg.1
0x2df7c  ldstr    aTr_0// "tr"
0x2df81  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteFullBeginTag(string)
0x2df86  ldarg.1
0x2df87  ldstr    aTd_0// "td"
0x2df8c  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteBeginTag(string)
0x2df91  ldarg.1
0x2df92  ldstr    aClass_0// "class"
0x2df97  ldstr    aCommentstableh// "CommentsTableHeight"
0x2df9c  ldc.i4.0
0x2df9d  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x2dfa2  ldarg.1
0x2dfa3  ldc.i4.s 0x3E
0x2dfa5  callvirt instance void [mscorlib]System.IO.TextWriter::Write(char)
0x2dfaa  ldarg.1
0x2dfab  ldstr    aLabel_3// "label"
0x2dfb0  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteBeginTag(string)
0x2dfb5  ldarg.1
0x2dfb6  ldstr    aClass_0// "class"
0x2dfbb  ldstr    aCommentsHint// "Comments-Hint"
0x2dfc0  ldc.i4.0
0x2dfc1  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x2dfc6  ldarg.1
0x2dfc7  ldstr    aFor// "for"
0x2dfcc  ldstr    aScriptcomments// "scriptCommentsControl"
0x2dfd1  ldc.i4.0
0x2dfd2  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x2dfd7  ldarg.1
0x2dfd8  ldc.i4.s 0x3E
0x2dfda  callvirt instance void [mscorlib]System.IO.TextWriter::Write(char)
0x2dfdf  ldarg.1
0x2dfe0  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x2dfe5  ldstr    aWebUiscriptsRu_10// "Web.UIScripts.RunScriptForm.Add_Comment"...
0x2dfea  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x2dfef  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x2dff4  ldarg.1
0x2dff5  ldstr    aLabel_3// "label"
0x2dffa  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteEndTag(string)
0x2dfff  ldarg.1
0x2e000  ldstr    aTextarea// "textarea"
0x2e005  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteBeginTag(string)
0x2e00a  ldarg.1
0x2e00b  ldstr    aId_1// "id"
0x2e010  ldstr    aScriptcomments// "scriptCommentsControl"
0x2e015  ldc.i4.0
0x2e016  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x2e01b  ldarg.1
0x2e01c  ldstr    aClass_0// "class"
0x2e021  ldstr    aCommentsTextar// "Comments-Textarea"
0x2e026  ldc.i4.0
0x2e027  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x2e02c  ldarg.1
0x2e02d  ldstr    aMaxlength_0// "maxlength"
0x2e032  ldstr    a2000// "2000"
0x2e037  ldc.i4.0
0x2e038  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x2e03d  ldarg.1
0x2e03e  ldstr    aTabindex// "tabindex"
0x2e043  ldstr    a10000// "10000"
0x2e048  ldc.i4.0
0x2e049  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x2e04e  ldarg.1
0x2e04f  ldc.i4.s 0x3E
0x2e051  callvirt instance void [mscorlib]System.IO.TextWriter::Write(char)
0x2e056  ldarg.1
0x2e057  ldstr    aTextarea// "textarea"
0x2e05c  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteEndTag(string)
0x2e061  ldarg.1
0x2e062  ldstr    aTd_0// "td"
0x2e067  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteEndTag(string)
0x2e06c  ldarg.1
0x2e06d  ldstr    aTr_0// "tr"
0x2e072  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteEndTag(string)
0x2e077  ldarg.1
0x2e078  ldstr    aTr_0// "tr"
0x2e07d  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteFullBeginTag(string)
0x2e082  ldarg.1
0x2e083  ldstr    aTdStyleHeight4// "td style=\"height:42px;\""
0x2e088  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteFullBeginTag(string)
0x2e08d  ldarg.1
0x2e08e  ldstr    aTable_0// "table"
0x2e093  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteBeginTag(string)
0x2e098  ldarg.1
0x2e099  ldstr    aCellspacing// "cellspacing"
0x2e09e  ldstr    a0// "0"
0x2e0a3  ldc.i4.0
0x2e0a4  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x2e0a9  ldarg.1
0x2e0aa  ldstr    aStyle_0// "style"
0x2e0af  ldstr    aWidth100// "width:100%"
0x2e0b4  ldc.i4.0
0x2e0b5  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x2e0ba  ldarg.1
0x2e0bb  ldc.i4.s 0x3E
0x2e0bd  callvirt instance void [mscorlib]System.IO.TextWriter::Write(char)
0x2e0c2  ldarg.1
0x2e0c3  ldstr    aTr_0// "tr"
0x2e0c8  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteBeginTag(string)
0x2e0cd  ldarg.1
0x2e0ce  ldstr    aStyle_0// "style"
0x2e0d3  ldstr    aWidth100// "width:100%"
0x2e0d8  ldc.i4.0
0x2e0d9  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x2e0de  ldarg.1
0x2e0df  ldc.i4.s 0x3E
0x2e0e1  callvirt instance void [mscorlib]System.IO.TextWriter::Write(char)
0x2e0e6  ldarg.1
0x2e0e7  ldstr    aTd_0// "td"
0x2e0ec  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteBeginTag(string)
0x2e0f1  ldarg.1
0x2e0f2  ldstr    aStyle_0// "style"
0x2e0f7  ldstr    aWidth100// "width:100%"
0x2e0fc  ldc.i4.0
0x2e0fd  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x2e102  ldarg.1
0x2e103  ldc.i4.s 0x3E
0x2e105  callvirt instance void [mscorlib]System.IO.TextWriter::Write(char)
0x2e10a  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentUICulture()
0x2e10f  callvirt instance class [mscorlib]System.Globalization.TextInfo [mscorlib]System.Globalization.CultureInfo::get_TextInfo()
0x2e114  callvirt instance bool [mscorlib]System.Globalization.TextInfo::get_IsRightToLeft()
0x2e119  brtrue.s loc_2E12B
0x2e11b  ldarg.0
0x2e11c  ldarg.1
0x2e11d  call     instance void Microsoft.Crm.Application.Forms.UIScriptWizardForm::RenderLeftFooterButtons(class [System.Web]System.Web.UI.HtmlTextWriter writer)
0x2e122  ldarg.0
0x2e123  ldarg.1
0x2e124  call     instance void Microsoft.Crm.Application.Forms.UIScriptWizardForm::RenderRightFooterButtons(class [System.Web]System.Web.UI.HtmlTextWriter writer)
0x2e129  br.s     loc_2E139
0x2e12b  ldarg.0
0x2e12c  ldarg.1
0x2e12d  call     instance void Microsoft.Crm.Application.Forms.UIScriptWizardForm::RenderRightFooterButtons(class [System.Web]System.Web.UI.HtmlTextWriter writer)
0x2e132  ldarg.0
0x2e133  ldarg.1
0x2e134  call     instance void Microsoft.Crm.Application.Forms.UIScriptWizardForm::RenderLeftFooterButtons(class [System.Web]System.Web.UI.HtmlTextWriter writer)
0x2e139  ldarg.1
0x2e13a  ldstr    aTd_0// "td"
0x2e13f  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteEndTag(string)
0x2e144  ldarg.1
0x2e145  ldstr    aTr_0// "tr"
0x2e14a  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteEndTag(string)
0x2e14f  ldarg.1
0x2e150  ldstr    aTable_0// "table"
0x2e155  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteEndTag(string)
0x2e15a  ldarg.1
0x2e15b  ldstr    aTd_0// "td"
0x2e160  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteEndTag(string)
0x2e165  ldarg.1
0x2e166  ldstr    aTr_0// "tr"
0x2e16b  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteEndTag(string)
0x2e170  ldarg.1
0x2e171  ldstr    aTable_0// "table"
0x2e176  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteEndTag(string)
0x2e17b  ldarg.1
0x2e17c  ldstr    aDiv_3// "div"
0x2e181  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteEndTag(string)
0x2e186  ret
```
