# Microsoft.Crm.Application.Controls.VisualizationRuntimeContentProvider::RenderAllNonContentSpans

- ea: `0x6f270`
- end: `0x6f57e`
- name: `Microsoft.Crm.Application.Controls.VisualizationRuntimeContentProvider::RenderAllNonContentSpans`
- size: `782`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x63f00`
- `0x64270`
- `0x64410`
- `0x64530`
- `0x65010`
- `0x6cfc0`
- `0x6f270`

## string_xrefs

- `0x6f3b7`: `openDesignerLink`
- `0x6f404`: `ms-crm-VisualizationPaneDesigner-NewChartLink`
- `0x6f41c`: `Web.Visualization.Designer.NewChartLink`

## pseudocode

```c

```

## disassembly

```asm
0x6f270  ldarg.1
0x6f271  ldstr    aSpan_1// "span"
0x6f276  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteBeginTag(string)
0x6f27b  ldarg.1
0x6f27c  ldstr    aId_1// "id"
0x6f281  ldstr    aEmptyvizspan// "emptyVizSpan"
0x6f286  ldc.i4.0
0x6f287  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x6f28c  ldarg.1
0x6f28d  ldstr    aClass_0// "class"
0x6f292  ldstr    aMsCrmEmptyvizp// "ms-crm-emptyvizpane"
0x6f297  ldc.i4.0
0x6f298  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x6f29d  ldarg.0
0x6f29e  call     instance class Microsoft.Crm.Application.Controls.VisualizationPane Microsoft.Crm.Application.Controls.PaneContentProviderBase::get_VisualizationPane()
0x6f2a3  callvirt instance class Microsoft.Crm.Application.Controls.VisualizationSelector Microsoft.Crm.Application.Controls.VisualizationPane::get_VisualizationList()
0x6f2a8  callvirt instance int32 Microsoft.Crm.Application.Controls.VisualizationSelector::get_Count()
0x6f2ad  ldc.i4.0
0x6f2ae  bgt.s    loc_6F2BD
0x6f2b0  ldarg.0
0x6f2b1  call     instance class Microsoft.Crm.Application.Controls.VisualizationPane Microsoft.Crm.Application.Controls.PaneContentProviderBase::get_VisualizationPane()
0x6f2b6  callvirt instance bool Microsoft.Crm.Application.Controls.VisualizationPane::get_LoadOnDemand()
0x6f2bb  brfalse.s loc_6F2CE
0x6f2bd  ldarg.1
0x6f2be  ldstr    aStyle_0// "style"
0x6f2c3  ldstr    aDisplayNone// "display:none"
0x6f2c8  ldc.i4.0
0x6f2c9  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x6f2ce  ldarg.1
0x6f2cf  ldc.i4.s 0x3E
0x6f2d1  callvirt instance void [mscorlib]System.IO.TextWriter::Write(char)
0x6f2d6  ldarg.1
0x6f2d7  ldstr    aTable_0// "table"
0x6f2dc  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteBeginTag(string)
0x6f2e1  ldarg.1
0x6f2e2  ldstr    aStyle_0// "style"
0x6f2e7  ldstr    aTextAlignCente_0// "text-align:center;height:100%"
0x6f2ec  ldc.i4.0
0x6f2ed  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x6f2f2  ldarg.1
0x6f2f3  ldc.i4.s 0x3E
0x6f2f5  callvirt instance void [mscorlib]System.IO.TextWriter::Write(char)
0x6f2fa  ldarg.1
0x6f2fb  ldstr    aTr_0// "tr"
0x6f300  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteFullBeginTag(string)
0x6f305  ldarg.1
0x6f306  ldstr    aTd_0// "td"
0x6f30b  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteFullBeginTag(string)
0x6f310  ldarg.1
0x6f311  ldstr    aLabel_3// "label"
0x6f316  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteBeginTag(string)
0x6f31b  ldarg.1
0x6f31c  ldstr    aId_1// "id"
0x6f321  ldstr    aEmptymessage// "emptymessage"
0x6f326  ldc.i4.0
0x6f327  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x6f32c  ldarg.1
0x6f32d  ldstr    aClass_0// "class"
0x6f332  ldstr    aMsCrmInfoLabel// "ms-crm-Info-Label"
0x6f337  ldc.i4.0
0x6f338  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x6f33d  ldarg.1
0x6f33e  ldc.i4.s 0x3E
0x6f340  callvirt instance void [mscorlib]System.IO.TextWriter::Write(char)
0x6f345  ldarg.0
0x6f346  call     instance class Microsoft.Crm.Application.Controls.VisualizationPane Microsoft.Crm.Application.Controls.PaneContentProviderBase::get_VisualizationPane()
0x6f34b  callvirt instance string Microsoft.Crm.Application.Controls.VisualizationPane::get_EmptyPaneMessage()
0x6f350  ldarg.1
0x6f351  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlEncode(string, class [mscorlib]System.IO.TextWriter)
0x6f356  ldarg.1
0x6f357  ldstr    aLabel_3// "label"
0x6f35c  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteEndTag(string)
0x6f361  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::IsOnline()
0x6f366  brfalse  loc_6F437
0x6f36b  ldarg.0
0x6f36c  call     instance class Microsoft.Crm.Application.Controls.VisualizationPane Microsoft.Crm.Application.Controls.PaneContentProviderBase::get_VisualizationPane()
0x6f371  callvirt instance bool Microsoft.Crm.Application.Controls.VisualizationPane::get_IsSubGridMode()
0x6f376  brtrue   loc_6F437
0x6f37b  ldstr    aUserqueryvisua// "userqueryvisualization"
0x6f380  ldc.i4.s 0x20
0x6f382  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x6f387  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::HasPrivilege(string, valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.AccessRights, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x6f38c  brfalse  loc_6F437
0x6f391  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x6f396  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::UseTabletExperience(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x6f39b  brtrue   loc_6F437
0x6f3a0  ldarg.1
0x6f3a1  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteBreak()
0x6f3a6  ldarg.1
0x6f3a7  ldstr    aA_0// "a"
0x6f3ac  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteBeginTag(string)
0x6f3b1  ldarg.1
0x6f3b2  ldstr    aId_1// "id"
0x6f3b7  ldstr    aOpendesignerli// "openDesignerLink"
0x6f3bc  ldc.i4.0
0x6f3bd  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x6f3c2  ldarg.1
0x6f3c3  ldstr    aOnclick// "onclick"
0x6f3c8  ldstr    aFind_1// "$find("
0x6f3cd  ldarg.0
0x6f3ce  call     instance class Microsoft.Crm.Application.Controls.VisualizationPane Microsoft.Crm.Application.Controls.PaneContentProviderBase::get_VisualizationPane()
0x6f3d3  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x6f3d8  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmJavaScriptEncode(string)
0x6f3dd  ldstr    aSwitchmode1// ").switchMode(1);"
0x6f3e2  call     string [mscorlib]System.String::Concat(string, string, string)
0x6f3e7  ldc.i4.0
0x6f3e8  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x6f3ed  ldarg.1
0x6f3ee  ldstr    aHref// "href"
0x6f3f3  ldstr    asc_12FEF0// "#"
0x6f3f8  ldc.i4.0
0x6f3f9  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x6f3fe  ldarg.1
0x6f3ff  ldstr    aClass_0// "class"
0x6f404  ldstr    aMsCrmVisualiza_9// "ms-crm-VisualizationPaneDesigner-NewCha"...
0x6f409  ldc.i4.0
0x6f40a  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x6f40f  ldarg.1
0x6f410  ldc.i4.s 0x3E
0x6f412  callvirt instance void [mscorlib]System.IO.TextWriter::Write(char)
0x6f417  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x6f41c  ldstr    aWebVisualizati_90// "Web.Visualization.Designer.NewChartLink"
0x6f421  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x6f426  ldarg.1
0x6f427  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlEncode(string, class [mscorlib]System.IO.TextWriter)
0x6f42c  ldarg.1
0x6f42d  ldstr    aA_0// "a"
0x6f432  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteEndTag(string)
0x6f437  ldarg.1
0x6f438  ldstr    aTd_0// "td"
0x6f43d  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteEndTag(string)
0x6f442  ldarg.1
0x6f443  ldstr    aTr_0// "tr"
0x6f448  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteEndTag(string)
0x6f44d  ldarg.1
0x6f44e  ldstr    aTable_0// "table"
0x6f453  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteEndTag(string)
0x6f458  ldarg.1
0x6f459  ldstr    aSpan_1// "span"
0x6f45e  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteEndTag(string)
0x6f463  ldarg.0
0x6f464  call     instance class Microsoft.Crm.Application.Controls.VisualizationPane Microsoft.Crm.Application.Controls.PaneContentProviderBase::get_VisualizationPane()
0x6f469  callvirt instance bool Microsoft.Crm.Application.Controls.VisualizationPane::get_LoadOnDemand()
0x6f46e  brfalse  loc_6F57D
0x6f473  ldarg.1
0x6f474  ldstr    aSpan_1// "span"
0x6f479  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteBeginTag(string)
0x6f47e  ldarg.1
0x6f47f  ldstr    aId_1// "id"
0x6f484  ldstr    aLoadondemandme// "loadOnDemandMessage"
0x6f489  ldc.i4.0
0x6f48a  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x6f48f  ldarg.1
0x6f490  ldstr    aHeight// "height"
0x6f495  ldstr    a100// "100%"
0x6f49a  ldc.i4.0
0x6f49b  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x6f4a0  ldarg.1
0x6f4a1  ldc.i4.s 0x3E
0x6f4a3  callvirt instance void [mscorlib]System.IO.TextWriter::Write(char)
0x6f4a8  ldarg.1
0x6f4a9  ldstr    aTable_0// "table"
0x6f4ae  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteBeginTag(string)
0x6f4b3  ldarg.1
0x6f4b4  ldstr    aStyle_0// "style"
0x6f4b9  ldstr    aTextAlignCente_0// "text-align:center;height:100%"
0x6f4be  ldc.i4.0
0x6f4bf  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x6f4c4  ldarg.1
0x6f4c5  ldc.i4.s 0x3E
0x6f4c7  callvirt instance void [mscorlib]System.IO.TextWriter::Write(char)
0x6f4cc  ldarg.1
0x6f4cd  ldstr    aTr_0// "tr"
0x6f4d2  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteFullBeginTag(string)
0x6f4d7  ldarg.1
0x6f4d8  ldstr    aTd_0// "td"
0x6f4dd  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteFullBeginTag(string)
0x6f4e2  ldarg.1
0x6f4e3  ldstr    aA_0// "a"
0x6f4e8  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteBeginTag(string)
0x6f4ed  ldarg.1
0x6f4ee  ldstr    aOnclick// "onclick"
0x6f4f3  ldstr    aFind_1// "$find("
0x6f4f8  ldarg.0
0x6f4f9  call     instance class Microsoft.Crm.Application.Controls.VisualizationPane Microsoft.Crm.Application.Controls.PaneContentProviderBase::get_VisualizationPane()
0x6f4fe  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x6f503  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmJavaScriptEncode(string)
0x6f508  ldstr    aLoadvisualizat// ").loadVisualizationOnDemand();"
0x6f50d  call     string [mscorlib]System.String::Concat(string, string, string)
0x6f512  ldc.i4.0
0x6f513  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x6f518  ldarg.1
0x6f519  ldstr    aHref// "href"
0x6f51e  ldstr    asc_12FEF0// "#"
0x6f523  ldc.i4.0
0x6f524  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x6f529  ldarg.1
0x6f52a  ldc.i4.s 0x3E
0x6f52c  callvirt instance void [mscorlib]System.IO.TextWriter::Write(char)
0x6f531  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x6f536  ldstr    aVisualizationL// "Visualization_LoadOnDemand"
0x6f53b  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x6f540  ldarg.1
0x6f541  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlEncode(string, class [mscorlib]System.IO.TextWriter)
0x6f546  ldarg.1
0x6f547  ldstr    aA_0// "a"
0x6f54c  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteEndTag(string)
0x6f551  ldarg.1
0x6f552  ldstr    aTd_0// "td"
0x6f557  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteEndTag(string)
0x6f55c  ldarg.1
0x6f55d  ldstr    aTr_0// "tr"
0x6f562  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteEndTag(string)
0x6f567  ldarg.1
0x6f568  ldstr    aTable_0// "table"
0x6f56d  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteEndTag(string)
0x6f572  ldarg.1
0x6f573  ldstr    aSpan_1// "span"
0x6f578  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteEndTag(string)
0x6f57d  ret
```
