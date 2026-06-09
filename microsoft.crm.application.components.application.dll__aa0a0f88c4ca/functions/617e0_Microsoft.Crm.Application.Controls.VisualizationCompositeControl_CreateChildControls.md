# Microsoft.Crm.Application.Controls.VisualizationCompositeControl::CreateChildControls

- ea: `0x617e0`
- end: `0x61f5d`
- name: `Microsoft.Crm.Application.Controls.VisualizationCompositeControl::CreateChildControls`
- size: `1917`
- prototype: ``
- caller_count: `0`
- callee_count: `20`
- tags: `broker_com_uri`

## callees

- `0xa1f0`
- `0x610d0`
- `0x61250`
- `0x61290`
- `0x613f0`
- `0x61460`
- `0x614a0`
- `0x617c0`
- `0x617e0`
- `0x61f60`
- `0x62280`
- `0x62750`
- `0x62980`
- `0x629a0`
- `0x629f0`
- `0x63ff0`
- `0x64190`
- `0x641d0`
- `0x64300`
- `0x64a30`

## string_xrefs

- `0x61808`: `compositeControl`
- `0x61c5f`: `window.Mscrm && Mscrm.CompositeControl && Mscrm.CompositeControl.mouseAction(new Sys.UI.DomEvent(event),'`
- `0x61cc1`: `Mscrm.CompositeControlResizeControl`
- `0x61f3d`: `compositeControlParams`

## pseudocode

```c

```

## disassembly

```asm
0x617e0  ldarg.0
0x617e1  call     instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::CreateChildControls()
0x617e6  ldarg.0
0x617e7  call     instance class [System.Web]System.Web.UI.CssStyleCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Style()
0x617ec  ldstr    aHeight// "height"
0x617f1  ldstr    a100// "100%"
0x617f6  callvirt instance void [System.Web]System.Web.UI.CssStyleCollection::Add(string, string)
0x617fb  ldstr    aDiv// "DIV"
0x61800  newobj   instance void [System.Web]System.Web.UI.HtmlControls.HtmlGenericControl::.ctor(string)
0x61805  stloc.0
0x61806  ldloc.0
0x61807  ldarg.0
0x61808  ldstr    aCompositecontr// "compositeControl"
0x6180d  call     instance string Microsoft.Crm.Application.Controls.VisualizationCompositeControl::AppendCrmGridId(string id)
0x61812  callvirt instance void [System.Web]System.Web.UI.Control::set_ID(string)
0x61817  ldloc.0
0x61818  callvirt instance class [System.Web]System.Web.UI.CssStyleCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Style()
0x6181d  ldstr    aHeight// "height"
0x61822  ldstr    a100// "100%"
0x61827  callvirt instance void [System.Web]System.Web.UI.CssStyleCollection::Add(string, string)
0x6182c  ldloc.0
0x6182d  callvirt instance class [System.Web]System.Web.UI.CssStyleCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Style()
0x61832  ldstr    aWidth// "width"
0x61837  ldstr    a100// "100%"
0x6183c  callvirt instance void [System.Web]System.Web.UI.CssStyleCollection::Add(string, string)
0x61841  ldarg.0
0x61842  call     instance string Microsoft.Crm.Application.Controls.VisualizationCompositeControl::get_StylePosition()
0x61847  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x6184c  brtrue.s loc_6186C
0x6184e  ldarg.0
0x6184f  ldfld    bool Microsoft.Crm.Application.Controls.VisualizationCompositeControl::_isSubGridLite
0x61854  brtrue.s loc_6186C
0x61856  ldloc.0
0x61857  callvirt instance class [System.Web]System.Web.UI.CssStyleCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Style()
0x6185c  ldstr    aPosition// "position"
0x61861  ldarg.0
0x61862  call     instance string Microsoft.Crm.Application.Controls.VisualizationCompositeControl::get_StylePosition()
0x61867  callvirt instance void [System.Web]System.Web.UI.CssStyleCollection::Add(string, string)
0x6186c  ldarg.0
0x6186d  call     instance bool Microsoft.Crm.Application.Controls.VisualizationCompositeControl::get_IsOutlookProxyControl()
0x61872  brtrue.s loc_6188D
0x61874  ldarg.0
0x61875  call     instance valuetype Microsoft.Crm.Application.Controls.RequiredElementsMask Microsoft.Crm.Application.Controls.VisualizationCompositeControl::get_RequiredElements()
0x6187a  ldc.i4.2
0x6187b  bne.un.s loc_6188D
0x6187d  ldarg.0
0x6187e  ldfld    class Microsoft.Crm.Application.Controls.VisualizationPane Microsoft.Crm.Application.Controls.VisualizationCompositeControl::pane
0x61883  ldstr    a2_0// "2"
0x61888  callvirt instance void Microsoft.Crm.Application.Controls.VisualizationPane::set_VisualizationPaneSize(string value)
0x6188d  ldarg.0
0x6188e  ldfld    class Microsoft.Crm.Application.Controls.VisualizationPane Microsoft.Crm.Application.Controls.VisualizationCompositeControl::pane
0x61893  brfalse.s loc_618A6
0x61895  ldarg.0
0x61896  ldfld    class Microsoft.Crm.Application.Controls.VisualizationPane Microsoft.Crm.Application.Controls.VisualizationCompositeControl::pane
0x6189b  ldarg.0
0x6189c  call     instance bool Microsoft.Crm.Application.Controls.VisualizationCompositeControl::get_EnableJumpBar()
0x618a1  callvirt instance void Microsoft.Crm.Application.Controls.VisualizationPane::set_ShowTwoRowFooter(bool value)
0x618a6  ldarg.0
0x618a7  ldfld    class Microsoft.Crm.Application.Controls.VisualizationPane Microsoft.Crm.Application.Controls.VisualizationCompositeControl::pane
0x618ac  brfalse.s loc_618BE
0x618ae  ldarg.0
0x618af  ldfld    class Microsoft.Crm.Application.Controls.VisualizationPane Microsoft.Crm.Application.Controls.VisualizationCompositeControl::pane
0x618b4  callvirt instance valuetype Microsoft.Crm.Application.Controls.LayoutType Microsoft.Crm.Application.Controls.VisualizationPane::get_PaneLayout()
0x618b9  ldc.i4.0
0x618ba  ceq
0x618bc  br.s     loc_618BF
0x618be  ldc.i4.1
0x618bf  stloc.1
0x618c0  ldloc.1
0x618c1  brtrue.s loc_618CA
0x618c3  ldstr    aTb// "TB"
0x618c8  br.s     loc_618CF
0x618ca  ldstr    aLr// "LR"
0x618cf  stloc.2
0x618d0  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class [System.Web]System.Web.UI.HtmlControls.HtmlGenericControl>::.ctor()
0x618d5  stloc.3
0x618d6  ldarg.0
0x618d7  call     instance valuetype Microsoft.Crm.Application.Controls.RequiredElementsMask Microsoft.Crm.Application.Controls.VisualizationCompositeControl::get_RequiredElements()
0x618dc  ldc.i4.3
0x618dd  and
0x618de  ldc.i4.3
0x618df  bne.un   loc_61979
0x618e4  ldstr    aDiv// "DIV"
0x618e9  newobj   instance void [System.Web]System.Web.UI.HtmlControls.HtmlGenericControl::.ctor(string)
0x618ee  stloc.s  5
0x618f0  ldloc.s  5
0x618f2  ldarg.0
0x618f3  ldstr    aCrmgridstrip// "crmGridStrip"
0x618f8  call     instance string Microsoft.Crm.Application.Controls.VisualizationCompositeControl::AppendCrmGridId(string id)
0x618fd  callvirt instance void [System.Web]System.Web.UI.Control::set_ID(string)
0x61902  ldloc.s  5
0x61904  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0x61909  ldloc.1
0x6190a  ldc.i4.1
0x6190b  ldarg.0
0x6190c  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x61911  ldarg.0
0x61912  call     instance string Microsoft.Crm.Application.Controls.VisualizationCompositeControl::get_GridId()
0x61917  call     class [System.Web]System.Web.UI.HtmlControls.HtmlGenericControl Microsoft.Crm.Application.Controls.CollapsedStripHelper::GetCollapsedStripContents(bool leftRight, bool layoutForGrid, string compositeControlId, string crmGridId)
0x6191c  callvirt instance void [System.Web]System.Web.UI.ControlCollection::Add(class [System.Web]System.Web.UI.Control)
0x61921  ldloc.s  5
0x61923  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0x61928  ldstr    aClass_0// "class"
0x6192d  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x61932  ldstr    aMsCrmCcGridss0// "ms-crm-CC-GridSS-{0}-{1}-{2}"
0x61937  ldc.i4.3
0x61938  newarr   [mscorlib]System.Object
0x6193d  dup
0x6193e  ldc.i4.0
0x6193f  ldarg.0
0x61940  call     instance valuetype Microsoft.Crm.Application.Controls.RequiredElementsMask Microsoft.Crm.Application.Controls.VisualizationCompositeControl::get_RequiredElements()
0x61945  stloc.s  6
0x61947  ldloca.s 6
0x61949  constrained. Microsoft.Crm.Application.Controls.RequiredElementsMask
0x6194f  callvirt instance string [mscorlib]System.Object::ToString()
0x61954  stelem.ref
0x61955  dup
0x61956  ldc.i4.1
0x61957  ldarg.0
0x61958  ldfld    class Microsoft.Crm.Application.Controls.VisualizationPane Microsoft.Crm.Application.Controls.VisualizationCompositeControl::pane
0x6195d  callvirt instance string Microsoft.Crm.Application.Controls.VisualizationPane::get_VisualizationPaneSize()
0x61962  stelem.ref
0x61963  dup
0x61964  ldc.i4.2
0x61965  ldloc.2
0x61966  stelem.ref
0x61967  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x6196c  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::Add(string, string)
0x61971  ldloc.3
0x61972  ldloc.s  5
0x61974  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<class [System.Web]System.Web.UI.HtmlControls.HtmlGenericControl>::Add(var<u1>)
0x61979  ldarg.0
0x6197a  call     instance bool Microsoft.Crm.Application.Controls.VisualizationCompositeControl::get_IsOutlookProxyControl()
0x6197f  brtrue   loc_61B0B
0x61984  ldarg.0
0x61985  call     instance bool Microsoft.Crm.Application.Controls.VisualizationCompositeControl::get_IsAppGridRequired()
0x6198a  brfalse  loc_61B0B
0x6198f  ldstr    aDiv// "DIV"
0x61994  newobj   instance void [System.Web]System.Web.UI.HtmlControls.HtmlGenericControl::.ctor(string)
0x61999  stloc.s  7
0x6199b  ldloc.s  7
0x6199d  ldarg.0
0x6199e  ldstr    aCrmgridtd// "crmGridTD"
0x619a3  call     instance string Microsoft.Crm.Application.Controls.VisualizationCompositeControl::AppendCrmGridId(string id)
0x619a8  callvirt instance void [System.Web]System.Web.UI.Control::set_ID(string)
0x619ad  ldloc.s  7
0x619af  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0x619b4  ldstr    aClass_0// "class"
0x619b9  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x619be  ldstr    aMsCrmCcGrid012// "ms-crm-CC-grid-{0}-{1}-{2}"
0x619c3  ldc.i4.3
0x619c4  newarr   [mscorlib]System.Object
0x619c9  dup
0x619ca  ldc.i4.0
0x619cb  ldarg.0
0x619cc  call     instance valuetype Microsoft.Crm.Application.Controls.RequiredElementsMask Microsoft.Crm.Application.Controls.VisualizationCompositeControl::get_RequiredElements()
0x619d1  stloc.s  6
0x619d3  ldloca.s 6
0x619d5  constrained. Microsoft.Crm.Application.Controls.RequiredElementsMask
0x619db  callvirt instance string [mscorlib]System.Object::ToString()
0x619e0  stelem.ref
0x619e1  dup
0x619e2  ldc.i4.1
0x619e3  ldarg.0
0x619e4  ldfld    class Microsoft.Crm.Application.Controls.VisualizationPane Microsoft.Crm.Application.Controls.VisualizationCompositeControl::pane
0x619e9  callvirt instance string Microsoft.Crm.Application.Controls.VisualizationPane::get_VisualizationPaneSize()
0x619ee  stelem.ref
0x619ef  dup
0x619f0  ldc.i4.2
0x619f1  ldloc.2
0x619f2  stelem.ref
0x619f3  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x619f8  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::Add(string, string)
0x619fd  ldarg.0
0x619fe  call     instance bool Microsoft.Crm.Application.Controls.VisualizationCompositeControl::get_RenderGridAsync()
0x61a03  brfalse  loc_61ABE
0x61a08  ldarg.0
0x61a09  callvirt instance class [System.Web]System.Web.UI.Page [System.Web]System.Web.UI.Control::get_Page()
0x61a0e  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x61a13  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x61a18  ldstr    aDialogname// "DialogName"
0x61a1d  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x61a22  brtrue.s loc_61A61
0x61a24  ldarg.0
0x61a25  callvirt instance class [System.Web]System.Web.UI.Page [System.Web]System.Web.UI.Control::get_Page()
0x61a2a  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x61a2f  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x61a34  ldstr    aIsturboform// "isTurboForm"
0x61a39  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x61a3e  brfalse.s loc_61AB4
0x61a40  ldarg.0
0x61a41  callvirt instance class [System.Web]System.Web.UI.Page [System.Web]System.Web.UI.Control::get_Page()
0x61a46  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x61a4b  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x61a50  ldstr    aIsturboform// "isTurboForm"
0x61a55  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x61a5a  call     bool [mscorlib]System.Boolean::Parse(string)
0x61a5f  brfalse.s loc_61AB4
0x61a61  ldarg.0
0x61a62  callvirt instance class [System.Web]System.Web.UI.Page [System.Web]System.Web.UI.Control::get_Page()
0x61a67  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x61a6c  callvirt instance class [System]System.Uri [System.Web]System.Web.HttpRequest::get_Url()
0x61a71  callvirt instance string [System]System.Uri::get_AbsolutePath()
0x61a76  ldstr    aDialogAspx// "/Dialog.aspx"
0x61a7b  callvirt instance bool [mscorlib]System.String::Contains(string)
0x61a80  brfalse.s loc_61A9B
0x61a82  ldloc.s  7
0x61a84  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0x61a89  ldarg.0
0x61a8a  ldstr    a1// "-1"
0x61a8f  call     instance class Microsoft.Crm.Application.Controls.AppGrid Microsoft.Crm.Application.Controls.VisualizationCompositeControl::GetAppGridLite([opt] string maxSelectableItems)
0x61a94  callvirt instance void [System.Web]System.Web.UI.ControlCollection::Add(class [System.Web]System.Web.UI.Control)
0x61a99  br.s     loc_61AE5
0x61a9b  ldloc.s  7
0x61a9d  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0x61aa2  ldarg.0
0x61aa3  ldstr    a1_0// "1"
0x61aa8  call     instance class Microsoft.Crm.Application.Controls.AppGrid Microsoft.Crm.Application.Controls.VisualizationCompositeControl::GetAppGridLite([opt] string maxSelectableItems)
0x61aad  callvirt instance void [System.Web]System.Web.UI.ControlCollection::Add(class [System.Web]System.Web.UI.Control)
0x61ab2  br.s     loc_61AE5
0x61ab4  ldarg.0
0x61ab5  ldloc.s  7
0x61ab7  call     instance void Microsoft.Crm.Application.Controls.VisualizationCompositeControl::InsertGridLoadingScript(class [System.Web]System.Web.UI.HtmlControls.HtmlGenericControl gridCell)
0x61abc  br.s     loc_61AE5
0x61abe  call     class [System.Web]System.Web.UI.HtmlControls.HtmlGenericControl Microsoft.Crm.Application.Controls.VisualizationCompositeControl::GetIE7HeightFixControl()
0x61ac3  stloc.s  8
0x61ac5  ldloc.s  8
0x61ac7  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0x61acc  ldarg.0
0x61acd  ldfld    class Microsoft.Crm.Application.Controls.AppGrid Microsoft.Crm.Application.Controls.VisualizationCompositeControl::crmGrid
0x61ad2  callvirt instance void [System.Web]System.Web.UI.ControlCollection::Add(class [System.Web]System.Web.UI.Control)
0x61ad7  ldloc.s  7
0x61ad9  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0x61ade  ldloc.s  8
0x61ae0  callvirt instance void [System.Web]System.Web.UI.ControlCollection::Add(class [System.Web]System.Web.UI.Control)
0x61ae5  ldloc.3
0x61ae6  ldloc.s  7
0x61ae8  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<class [System.Web]System.Web.UI.HtmlControls.HtmlGenericControl>::Add(var<u1>)
0x61aed  ldarg.0
0x61aee  call     instance valuetype Microsoft.Crm.Application.Controls.RequiredElementsMask Microsoft.Crm.Application.Controls.VisualizationCompositeControl::get_RequiredElements()
0x61af3  ldc.i4.1
0x61af4  and
0x61af5  ldc.i4.1
0x61af6  beq.s    loc_61B0B
0x61af8  ldloc.s  7
0x61afa  callvirt instance class [System.Web]System.Web.UI.CssStyleCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Style()
0x61aff  ldc.i4.s 0x12
0x61b01  ldstr    aNone// "none"
0x61b06  callvirt instance void [System.Web]System.Web.UI.CssStyleCollection::Add(valuetype [System.Web]System.Web.UI.HtmlTextWriterStyle, string)
0x61b0b  ldarg.0
0x61b0c  call     instance valuetype Microsoft.Crm.Application.Controls.RequiredElementsMask Microsoft.Crm.Application.Controls.VisualizationCompositeControl::get_RequiredElements()
0x61b11  ldc.i4.3
0x61b12  and
0x61b13  ldc.i4.3
0x61b14  beq.s    loc_61B21
0x61b16  ldarg.0
0x61b17  call     instance bool Microsoft.Crm.Application.Controls.VisualizationCompositeControl::get_IsOutlookProxyControl()
0x61b1c  brfalse  loc_61CD6
0x61b21  ldstr    aDiv// "DIV"
0x61b26  newobj   instance void [System.Web]System.Web.UI.HtmlControls.HtmlGenericControl::.ctor(string)
0x61b2b  stloc.s  9
0x61b2d  ldloc.s  9
0x61b2f  ldarg.0
0x61b30  ldstr    aSplittd// "splitTD"
0x61b35  call     instance string Microsoft.Crm.Application.Controls.VisualizationCompositeControl::AppendCrmGridId(string id)
0x61b3a  callvirt instance void [System.Web]System.Web.UI.Control::set_ID(string)
0x61b3f  ldloc.s  9
0x61b41  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0x61b46  ldstr    aClass_0// "class"
0x61b4b  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x61b50  ldstr    aMsCrmCcSplitte// "ms-crm-CC-splitter-{0}-{1}-{2} {3}"
0x61b55  ldc.i4.4
0x61b56  newarr   [mscorlib]System.Object
0x61b5b  dup
0x61b5c  ldc.i4.0
0x61b5d  ldarg.0
0x61b5e  call     instance valuetype Microsoft.Crm.Application.Controls.RequiredElementsMask Microsoft.Crm.Application.Controls.VisualizationCompositeControl::get_RequiredElements()
0x61b63  stloc.s  6
0x61b65  ldloca.s 6
0x61b67  constrained. Microsoft.Crm.Application.Controls.RequiredElementsMask
0x61b6d  callvirt instance string [mscorlib]System.Object::ToString()
0x61b72  stelem.ref
0x61b73  dup
0x61b74  ldc.i4.1
0x61b75  ldarg.0
0x61b76  ldfld    class Microsoft.Crm.Application.Controls.VisualizationPane Microsoft.Crm.Application.Controls.VisualizationCompositeControl::pane
0x61b7b  callvirt instance string Microsoft.Crm.Application.Controls.VisualizationPane::get_VisualizationPaneSize()
0x61b80  stelem.ref
0x61b81  dup
0x61b82  ldc.i4.2
0x61b83  ldloc.2
0x61b84  stelem.ref
0x61b85  dup
0x61b86  ldc.i4.3
0x61b87  ldstr    aMsCrmCcSplitte_0// "ms-crm-CC-splitter"
0x61b8c  stelem.ref
0x61b8d  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x61b92  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::Add(string, string)
0x61b97  ldloc.s  9
0x61b99  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
  ... truncated ...
```
