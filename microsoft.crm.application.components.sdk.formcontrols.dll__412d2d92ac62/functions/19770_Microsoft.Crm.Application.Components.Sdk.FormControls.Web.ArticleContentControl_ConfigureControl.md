# Microsoft.Crm.Application.Components.Sdk.FormControls.Web.ArticleContentControl::ConfigureControl

- ea: `0x19770`
- end: `0x19a6c`
- name: `Microsoft.Crm.Application.Components.Sdk.FormControls.Web.ArticleContentControl::ConfigureControl`
- size: `764`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callees

- `0x178c0`
- `0x19770`
- `0x19b80`

## pseudocode

```c

```

## disassembly

```asm
0x19770  ldarg.0
0x19771  call     instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormControlBase::ConfigureControl()
0x19776  ldarg.0
0x19777  newobj   instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppHtmlBarControl::.ctor()
0x1977c  stfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppHtmlBarControl Microsoft.Crm.Application.Components.Sdk.FormControls.Web.ArticleContentControl::crmHtmlBar
0x19781  ldarg.0
0x19782  ldarg.0
0x19783  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppHtmlBarControl Microsoft.Crm.Application.Components.Sdk.FormControls.Web.ArticleContentControl::crmHtmlBar
0x19788  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::ConfigureChildControl(class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase)
0x1978d  ldarg.0
0x1978e  callvirt instance class [System.Web]System.Web.UI.Page [System.Web]System.Web.UI.Control::get_Page()
0x19793  isinst   [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage
0x19798  stloc.0
0x19799  ldloc.0
0x1979a  brfalse  loc_19A6B
0x1979f  ldloc.0
0x197a0  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentType()
0x197a5  ldnull
0x197a6  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::op_Inequality(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType, class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType)
0x197ab  brfalse  loc_19A6B
0x197b0  ldarg.0
0x197b1  newobj   instance void [System.Web]System.Web.UI.HtmlControls.HtmlTable::.ctor()
0x197b6  stfld    class [System.Web]System.Web.UI.HtmlControls.HtmlContainerControl Microsoft.Crm.Application.Components.Sdk.FormControls.Web.ArticleContentControl::viewDesign
0x197bb  ldarg.0
0x197bc  ldloc.0
0x197bd  callvirt instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentForm()
0x197c2  stfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm Microsoft.Crm.Application.Components.Sdk.FormControls.Web.ArticleContentControl::appForm
0x197c7  ldarg.0
0x197c8  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm Microsoft.Crm.Application.Components.Sdk.FormControls.Web.ArticleContentControl::appForm
0x197cd  callvirt instance bool [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_Disabled()
0x197d2  brtrue.s loc_197DF
0x197d4  ldarg.0
0x197d5  callvirt instance bool [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_Disabled()
0x197da  brtrue   loc_19A54
0x197df  ldarg.0
0x197e0  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlContainerControl Microsoft.Crm.Application.Components.Sdk.FormControls.Web.ArticleContentControl::viewDesign
0x197e5  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0x197ea  ldstr    aHeight// "height"
0x197ef  ldstr    a100// "100%"
0x197f4  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::Add(string, string)
0x197f9  ldarg.0
0x197fa  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlContainerControl Microsoft.Crm.Application.Components.Sdk.FormControls.Web.ArticleContentControl::viewDesign
0x197ff  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0x19804  ldstr    aWidth// "width"
0x19809  ldstr    a100// "100%"
0x1980e  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::Add(string, string)
0x19813  newobj   instance void [System.Web]System.Web.UI.HtmlControls.HtmlTableCell::.ctor()
0x19818  stloc.1
0x19819  newobj   instance void [System.Web]System.Web.UI.HtmlControls.HtmlTableRow::.ctor()
0x1981e  stloc.2
0x1981f  ldloc.2
0x19820  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0x19825  ldstr    aStyle// "style"
0x1982a  ldstr    aVerticalAlignT_0// "vertical-align:top"
0x1982f  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::Add(string, string)
0x19834  ldarg.0
0x19835  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlContainerControl Microsoft.Crm.Application.Components.Sdk.FormControls.Web.ArticleContentControl::viewDesign
0x1983a  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0x1983f  ldloc.2
0x19840  callvirt instance void [System.Web]System.Web.UI.ControlCollection::Add(class [System.Web]System.Web.UI.Control)
0x19845  ldloc.1
0x19846  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0x1984b  ldstr    aWidth// "width"
0x19850  ldstr    a100// "100%"
0x19855  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::Add(string, string)
0x1985a  ldloc.2
0x1985b  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0x19860  ldloc.1
0x19861  callvirt instance void [System.Web]System.Web.UI.ControlCollection::Add(class [System.Web]System.Web.UI.Control)
0x19866  ldarg.0
0x19867  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm Microsoft.Crm.Application.Components.Sdk.FormControls.Web.ArticleContentControl::appForm
0x1986c  callvirt instance bool [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_Disabled()
0x19871  brtrue.s loc_198D7
0x19873  ldarg.0
0x19874  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm Microsoft.Crm.Application.Components.Sdk.FormControls.Web.ArticleContentControl::appForm
0x19879  callvirt instance string [mscorlib]System.Object::ToString()
0x1987e  ldstr    aMicrosoftCrmAp_3// "Microsoft.Crm.Application.Forms.PrintFo"...
0x19883  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x19888  brfalse.s loc_198D7
0x1988a  ldarg.0
0x1988b  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppHtmlBarControl Microsoft.Crm.Application.Components.Sdk.FormControls.Web.ArticleContentControl::crmHtmlBar
0x19890  ldc.i4   0xF3
0x19895  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.HtmlBar::set_Options(valuetype [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.HtmlBar/HtmlBarParam)
0x1989a  ldarg.0
0x1989b  callvirt instance class [System.Web]System.Web.UI.Page [System.Web]System.Web.UI.Control::get_Page()
0x198a0  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x198a5  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::IsIosDevice(class [System.Web]System.Web.HttpRequest)
0x198aa  brtrue.s loc_198C6
0x198ac  ldarg.0
0x198ad  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppHtmlBarControl Microsoft.Crm.Application.Components.Sdk.FormControls.Web.ArticleContentControl::crmHtmlBar
0x198b2  ldarg.0
0x198b3  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppHtmlBarControl Microsoft.Crm.Application.Components.Sdk.FormControls.Web.ArticleContentControl::crmHtmlBar
0x198b8  callvirt instance valuetype [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.HtmlBar/HtmlBarParam [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.HtmlBar::get_Options()
0x198bd  ldc.i4.8
0x198be  or
0x198bf  ldc.i4.4
0x198c0  or
0x198c1  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.HtmlBar::set_Options(valuetype [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.HtmlBar/HtmlBarParam)
0x198c6  ldloc.1
0x198c7  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0x198cc  ldarg.0
0x198cd  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppHtmlBarControl Microsoft.Crm.Application.Components.Sdk.FormControls.Web.ArticleContentControl::crmHtmlBar
0x198d2  callvirt instance void [System.Web]System.Web.UI.ControlCollection::Add(class [System.Web]System.Web.UI.Control)
0x198d7  newobj   instance void [System.Web]System.Web.UI.HtmlControls.HtmlTableRow::.ctor()
0x198dc  stloc.3
0x198dd  newobj   instance void [System.Web]System.Web.UI.HtmlControls.HtmlTableCell::.ctor()
0x198e2  stloc.s  4
0x198e4  ldloc.3
0x198e5  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0x198ea  ldstr    aStyle// "style"
0x198ef  ldstr    aVerticalAlignT_0// "vertical-align:top"
0x198f4  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::Add(string, string)
0x198f9  ldarg.0
0x198fa  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlContainerControl Microsoft.Crm.Application.Components.Sdk.FormControls.Web.ArticleContentControl::viewDesign
0x198ff  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0x19904  ldloc.3
0x19905  callvirt instance void [System.Web]System.Web.UI.ControlCollection::Add(class [System.Web]System.Web.UI.Control)
0x1990a  ldloc.2
0x1990b  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0x19910  ldloc.s  4
0x19912  callvirt instance void [System.Web]System.Web.UI.ControlCollection::Add(class [System.Web]System.Web.UI.Control)
0x19917  leave.s  loc_19939
0x19919  ldloc.s  4
0x1991b  brfalse.s loc_19924
0x1991d  ldloc.s  4
0x1991f  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x19924  endfinally
0x19925  ldloc.3
0x19926  brfalse.s loc_1992E
0x19928  ldloc.3
0x19929  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1992e  endfinally
0x1992f  ldloc.2
0x19930  brfalse.s loc_19938
0x19932  ldloc.2
0x19933  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x19938  endfinally
0x19939  ldstr    aDiv// "div"
0x1993e  newobj   instance void [System.Web]System.Web.UI.HtmlControls.HtmlGenericControl::.ctor(string)
0x19943  stloc.s  5
0x19945  ldloc.s  5
0x19947  ldstr    aContenteditor// "ContentEditor"
0x1994c  callvirt instance void [System.Web]System.Web.UI.Control::set_ID(string)
0x19951  ldloc.s  5
0x19953  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0x19958  ldstr    aClass// "class"
0x1995d  ldstr    aEditpage// "editPage"
0x19962  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::set_Item(string, string)
0x19967  ldloc.s  5
0x19969  callvirt instance class [System.Web]System.Web.UI.CssStyleCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Style()
0x1996e  ldc.i4.0
0x1996f  ldstr    aFfffff// "#FFFFFF"
0x19974  callvirt instance void [System.Web]System.Web.UI.CssStyleCollection::Add(valuetype [System.Web]System.Web.UI.HtmlTextWriterStyle, string)
0x19979  ldloc.s  5
0x1997b  callvirt instance class [System.Web]System.Web.UI.CssStyleCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Style()
0x19980  ldc.i4.s 0x1C
0x19982  ldstr    aAuto// "auto"
0x19987  callvirt instance void [System.Web]System.Web.UI.CssStyleCollection::Add(valuetype [System.Web]System.Web.UI.HtmlTextWriterStyle, string)
0x1998c  ldloc.s  5
0x1998e  callvirt instance class [System.Web]System.Web.UI.CssStyleCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Style()
0x19993  ldc.i4.5
0x19994  ldstr    a1px// "1px"
0x19999  callvirt instance void [System.Web]System.Web.UI.CssStyleCollection::Add(valuetype [System.Web]System.Web.UI.HtmlTextWriterStyle, string)
0x1999e  ldloc.s  5
0x199a0  callvirt instance class [System.Web]System.Web.UI.CssStyleCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Style()
0x199a5  ldc.i4.4
0x199a6  ldstr    aSolid// "solid"
0x199ab  callvirt instance void [System.Web]System.Web.UI.CssStyleCollection::Add(valuetype [System.Web]System.Web.UI.HtmlTextWriterStyle, string)
0x199b0  ldloc.s  5
0x199b2  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0x199b7  ldstr    aOnselectstart// "onselectstart"
0x199bc  ldstr    aWindowEventCan// "window.event.cancelBubble=true;return t"...
0x199c1  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::set_Item(string, string)
0x199c6  ldloc.s  5
0x199c8  ldarg.0
0x199c9  ldarg.0
0x199ca  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm Microsoft.Crm.Application.Components.Sdk.FormControls.Web.ArticleContentControl::appForm
0x199cf  callvirt instance bool [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_Disabled()
0x199d4  brtrue.s loc_199ED
0x199d6  ldarg.0
0x199d7  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm Microsoft.Crm.Application.Components.Sdk.FormControls.Web.ArticleContentControl::appForm
0x199dc  callvirt instance string [mscorlib]System.Object::ToString()
0x199e1  ldstr    aMicrosoftCrmAp_3// "Microsoft.Crm.Application.Forms.PrintFo"...
0x199e6  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x199eb  br.s     loc_199EE
0x199ed  ldc.i4.0
0x199ee  call     instance string Microsoft.Crm.Application.Components.Sdk.FormControls.Web.ArticleContentControl::GetArticleHtml(bool designMode)
0x199f3  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlContainerControl::set_InnerHtml(string)
0x199f8  ldarg.0
0x199f9  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm Microsoft.Crm.Application.Components.Sdk.FormControls.Web.ArticleContentControl::appForm
0x199fe  callvirt instance bool [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_Disabled()
0x19a03  brtrue.s loc_19A2F
0x19a05  ldarg.0
0x19a06  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm Microsoft.Crm.Application.Components.Sdk.FormControls.Web.ArticleContentControl::appForm
0x19a0b  callvirt instance string [mscorlib]System.Object::ToString()
0x19a10  ldstr    aMicrosoftCrmAp_4// "Microsoft.Crm.Application.Forms.FormEdi"...
0x19a15  call     bool [mscorlib]System.String::op_Equality(string, string)
0x19a1a  brfalse.s loc_19A2F
0x19a1c  ldloc.s  5
0x19a1e  callvirt instance class [System.Web]System.Web.UI.CssStyleCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Style()
0x19a23  ldc.i4.s 0xB
0x19a25  ldstr    a100px// "100px"
0x19a2a  callvirt instance void [System.Web]System.Web.UI.CssStyleCollection::Add(valuetype [System.Web]System.Web.UI.HtmlTextWriterStyle, string)
0x19a2f  ldloc.1
0x19a30  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0x19a35  ldloc.s  5
0x19a37  callvirt instance void [System.Web]System.Web.UI.ControlCollection::Add(class [System.Web]System.Web.UI.Control)
0x19a3c  leave.s  loc_19A54
0x19a3e  ldloc.s  5
0x19a40  brfalse.s loc_19A49
0x19a42  ldloc.s  5
0x19a44  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x19a49  endfinally
0x19a4a  ldloc.1
0x19a4b  brfalse.s loc_19A53
0x19a4d  ldloc.1
0x19a4e  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x19a53  endfinally
0x19a54  ldarg.0
0x19a55  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlContainerControl Microsoft.Crm.Application.Components.Sdk.FormControls.Web.ArticleContentControl::viewDesign
0x19a5a  callvirt instance class [System.Web]System.Web.UI.CssStyleCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Style()
0x19a5f  ldc.i4.s 0xF
0x19a61  ldstr    aDisc// "disc"
0x19a66  callvirt instance void [System.Web]System.Web.UI.CssStyleCollection::Add(valuetype [System.Web]System.Web.UI.HtmlTextWriterStyle, string)
0x19a6b  ret
```
