# Microsoft.Crm.Application.Components.Sdk.FormControls.Web.TabsControl::CreateChildControls

- ea: `0x2a1b0`
- end: `0x2a4d3`
- name: `Microsoft.Crm.Application.Components.Sdk.FormControls.Web.TabsControl::CreateChildControls`
- size: `803`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x28820`

## callees

- `0x29e60`
- `0x29e80`
- `0x29ea0`
- `0x29ec0`
- `0x29ee0`
- `0x29f60`
- `0x2a1b0`

## string_xrefs

- `0x2a2f1`: `tabLink ms-crm-PanelHeader-Color`
- `0x2a2f8`: `tabLink ms-crm-PanelHeader-Color active`
- `0x2a314`: `tabLink`
- `0x2a31b`: `tabLink active`
- `0x2a4b1`: `OAuthTokenExpiredAlertIcon`

## pseudocode

```c

```

## disassembly

```asm
0x2a1b0  ldarg.0
0x2a1b1  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0x2a1b6  callvirt instance int32 [System.Web]System.Web.UI.ControlCollection::get_Count()
0x2a1bb  brtrue.s loc_2A1DF
0x2a1bd  ldarg.0
0x2a1be  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0x2a1c3  ldarg.0
0x2a1c4  ldfld    class [System.Web]System.Web.UI.WebControls.Panel Microsoft.Crm.Application.Components.Sdk.FormControls.Web.TabsControl::HeaderPlaceholder
0x2a1c9  callvirt instance void [System.Web]System.Web.UI.ControlCollection::Add(class [System.Web]System.Web.UI.Control)
0x2a1ce  ldarg.0
0x2a1cf  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0x2a1d4  ldarg.0
0x2a1d5  ldfld    class [System.Web]System.Web.UI.WebControls.Panel Microsoft.Crm.Application.Components.Sdk.FormControls.Web.TabsControl::contentPlaceHolder
0x2a1da  callvirt instance void [System.Web]System.Web.UI.ControlCollection::Add(class [System.Web]System.Web.UI.Control)
0x2a1df  ldarg.0
0x2a1e0  ldfld    class [System.Web]System.Web.UI.WebControls.Panel Microsoft.Crm.Application.Components.Sdk.FormControls.Web.TabsControl::HeaderPlaceholder
0x2a1e5  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0x2a1ea  callvirt instance int32 [System.Web]System.Web.UI.ControlCollection::get_Count()
0x2a1ef  brtrue   loc_2A4CC
0x2a1f4  ldarg.0
0x2a1f5  ldfld    class [System.Web]System.Web.UI.WebControls.Panel Microsoft.Crm.Application.Components.Sdk.FormControls.Web.TabsControl::contentPlaceHolder
0x2a1fa  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0x2a1ff  callvirt instance int32 [System.Web]System.Web.UI.ControlCollection::get_Count()
0x2a204  brtrue   loc_2A4CC
0x2a209  ldarg.0
0x2a20a  call     instance class [mscorlib]System.Collections.Generic.IList`1<class Microsoft.Crm.Application.Components.Sdk.FormControls.Web.TabDataContainer> Microsoft.Crm.Application.Components.Sdk.FormControls.Web.TabsControl::get_Items()
0x2a20f  callvirt instance int32 class [mscorlib]System.Collections.Generic.ICollection`1<class Microsoft.Crm.Application.Components.Sdk.FormControls.Web.TabDataContainer>::get_Count()
0x2a214  ldc.i4.0
0x2a215  ble      loc_2A4CC
0x2a21a  ldarg.0
0x2a21b  call     instance class [mscorlib]System.Collections.Generic.IList`1<class Microsoft.Crm.Application.Components.Sdk.FormControls.Web.TabDataContainer> Microsoft.Crm.Application.Components.Sdk.FormControls.Web.TabsControl::get_Items()
0x2a220  ldarg.0
0x2a221  ldftn    instance bool Microsoft.Crm.Application.Components.Sdk.FormControls.Web.TabsControl::<CreateChildControls>b__76_0(class Microsoft.Crm.Application.Components.Sdk.FormControls.Web.TabDataContainer tabDataContainer)
0x2a227  newobj   instance void class [mscorlib]System.Func`2<class Microsoft.Crm.Application.Components.Sdk.FormControls.Web.TabDataContainer, bool>::.ctor(object, native int)
0x2a22c  call     T0x2B000009
0x2a231  stloc.0
0x2a232  ldloc.0
0x2a233  brtrue.s loc_2A241
0x2a235  ldarg.0
0x2a236  call     instance class [mscorlib]System.Collections.Generic.IList`1<class Microsoft.Crm.Application.Components.Sdk.FormControls.Web.TabDataContainer> Microsoft.Crm.Application.Components.Sdk.FormControls.Web.TabsControl::get_Items()
0x2a23b  call     T0x2B00000A
0x2a240  stloc.0
0x2a241  ldarg.0
0x2a242  ldfld    class [System.Web]System.Web.UI.WebControls.Panel Microsoft.Crm.Application.Components.Sdk.FormControls.Web.TabsControl::HeaderPlaceholder
0x2a247  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.WebControls.WebControl::get_Attributes()
0x2a24c  ldstr    aRole// "role"
0x2a251  ldstr    aTablist// "tablist"
0x2a256  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::Add(string, string)
0x2a25b  ldarg.0
0x2a25c  call     instance class [mscorlib]System.Collections.Generic.IList`1<class Microsoft.Crm.Application.Components.Sdk.FormControls.Web.TabDataContainer> Microsoft.Crm.Application.Components.Sdk.FormControls.Web.TabsControl::get_Items()
0x2a261  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.Crm.Application.Components.Sdk.FormControls.Web.TabDataContainer>::GetEnumerator()
0x2a266  stloc.2
0x2a267  br       loc_2A479
0x2a26c  ldloc.2
0x2a26d  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class Microsoft.Crm.Application.Components.Sdk.FormControls.Web.TabDataContainer>::get_Current()
0x2a272  stloc.3
0x2a273  newobj   instance void [System.Web]System.Web.UI.HtmlControls.HtmlAnchor::.ctor()
0x2a278  stloc.s  4
0x2a27a  ldloc.s  4
0x2a27c  ldloc.3
0x2a27d  callvirt instance string Microsoft.Crm.Application.Components.Sdk.FormControls.Web.TabDataContainer::get_TabName()
0x2a282  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlContainerControl::set_InnerText(string)
0x2a287  ldloc.s  4
0x2a289  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0x2a28e  ldstr    aTitle// "title"
0x2a293  ldloc.3
0x2a294  callvirt instance string Microsoft.Crm.Application.Components.Sdk.FormControls.Web.TabDataContainer::get_TabName()
0x2a299  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::Add(string, string)
0x2a29e  ldloc.s  4
0x2a2a0  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0x2a2a5  ldstr    aRole// "role"
0x2a2aa  ldstr    aTab// "tab"
0x2a2af  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::Add(string, string)
0x2a2b4  ldloc.s  4
0x2a2b6  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0x2a2bb  ldstr    aAriaSelected// "aria-selected"
0x2a2c0  ldloc.0
0x2a2c1  ldloc.3
0x2a2c2  beq.s    loc_2A2CB
0x2a2c4  ldstr    aFalse// "false"
0x2a2c9  br.s     loc_2A2D0
0x2a2cb  ldstr    aTrue// "true"
0x2a2d0  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::Add(string, string)
0x2a2d5  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x2a2da  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::IsWebClientVisualRefreshFeatureAvailable(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x2a2df  brfalse.s loc_2A304
0x2a2e1  ldloc.s  4
0x2a2e3  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0x2a2e8  ldstr    aClass// "class"
0x2a2ed  ldloc.0
0x2a2ee  ldloc.3
0x2a2ef  beq.s    loc_2A2F8
0x2a2f1  ldstr    aTablinkMsCrmPa// "tabLink ms-crm-PanelHeader-Color"
0x2a2f6  br.s     loc_2A2FD
0x2a2f8  ldstr    aTablinkMsCrmPa_0// "tabLink ms-crm-PanelHeader-Color active"
0x2a2fd  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::Add(string, string)
0x2a302  br.s     loc_2A325
0x2a304  ldloc.s  4
0x2a306  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0x2a30b  ldstr    aClass// "class"
0x2a310  ldloc.0
0x2a311  ldloc.3
0x2a312  beq.s    loc_2A31B
0x2a314  ldstr    aTablink// "tabLink"
0x2a319  br.s     loc_2A320
0x2a31b  ldstr    aTablinkActive// "tabLink active"
0x2a320  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::Add(string, string)
0x2a325  ldloc.s  4
0x2a327  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0x2a32c  ldstr    aHref// "href"
0x2a331  ldstr    aJavascript// "javascript:;"
0x2a336  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::Add(string, string)
0x2a33b  ldloc.s  4
0x2a33d  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0x2a342  ldstr    aTabid// "tabId"
0x2a347  ldloc.3
0x2a348  callvirt instance string Microsoft.Crm.Application.Components.Sdk.FormControls.Web.TabDataContainer::get_TabId()
0x2a34d  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::Add(string, string)
0x2a352  ldloc.3
0x2a353  callvirt instance bool Microsoft.Crm.Application.Components.Sdk.FormControls.Web.TabDataContainer::get_Hidden()
0x2a358  brfalse.s loc_2A36D
0x2a35a  ldloc.s  4
0x2a35c  callvirt instance class [System.Web]System.Web.UI.CssStyleCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Style()
0x2a361  ldc.i4.s 0x12
0x2a363  ldstr    aNone// "none"
0x2a368  callvirt instance void [System.Web]System.Web.UI.CssStyleCollection::Add(valuetype [System.Web]System.Web.UI.HtmlTextWriterStyle, string)
0x2a36d  ldarg.0
0x2a36e  ldfld    class [System.Web]System.Web.UI.WebControls.Panel Microsoft.Crm.Application.Components.Sdk.FormControls.Web.TabsControl::HeaderPlaceholder
0x2a373  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0x2a378  ldloc.s  4
0x2a37a  callvirt instance void [System.Web]System.Web.UI.ControlCollection::Add(class [System.Web]System.Web.UI.Control)
0x2a37f  ldstr    aDiv_1// "DIV"
0x2a384  newobj   instance void [System.Web]System.Web.UI.HtmlControls.HtmlGenericControl::.ctor(string)
0x2a389  stloc.s  5
0x2a38b  ldloc.3
0x2a38c  callvirt instance string Microsoft.Crm.Application.Components.Sdk.FormControls.Web.TabDataContainer::get_AdditionalCssClass()
0x2a391  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x2a396  brfalse.s loc_2A39F
0x2a398  ldstr    aTabcontainer// "tabContainer"
0x2a39d  br.s     loc_2A3AF
0x2a39f  ldstr    aTabcontainer_0// "tabContainer "
0x2a3a4  ldloc.3
0x2a3a5  callvirt instance string Microsoft.Crm.Application.Components.Sdk.FormControls.Web.TabDataContainer::get_AdditionalCssClass()
0x2a3aa  call     string [mscorlib]System.String::Concat(string, string)
0x2a3af  stloc.s  6
0x2a3b1  ldloc.s  5
0x2a3b3  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0x2a3b8  ldstr    aClass// "class"
0x2a3bd  ldloc.0
0x2a3be  ldloc.3
0x2a3bf  beq.s    loc_2A3C5
0x2a3c1  ldloc.s  6
0x2a3c3  br.s     loc_2A3D1
0x2a3c5  ldloc.s  6
0x2a3c7  ldstr    aActive// " active"
0x2a3cc  call     string [mscorlib]System.String::Concat(string, string)
0x2a3d1  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::Add(string, string)
0x2a3d6  ldloc.s  5
0x2a3d8  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0x2a3dd  ldstr    aShown// "shown"
0x2a3e2  ldstr    aFalse// "false"
0x2a3e7  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::Add(string, string)
0x2a3ec  ldloc.s  5
0x2a3ee  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0x2a3f3  ldstr    aRole// "role"
0x2a3f8  ldstr    aTabpanel// "tabpanel"
0x2a3fd  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::Add(string, string)
0x2a402  ldloc.s  5
0x2a404  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0x2a409  ldstr    aAriaHidden// "aria-hidden"
0x2a40e  ldloc.0
0x2a40f  ldloc.3
0x2a410  beq.s    loc_2A419
0x2a412  ldstr    aTrue// "true"
0x2a417  br.s     loc_2A41E
0x2a419  ldstr    aFalse// "false"
0x2a41e  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::Add(string, string)
0x2a423  ldloc.s  5
0x2a425  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0x2a42a  ldstr    aTabid// "tabId"
0x2a42f  ldloc.3
0x2a430  callvirt instance string Microsoft.Crm.Application.Components.Sdk.FormControls.Web.TabDataContainer::get_TabId()
0x2a435  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::Add(string, string)
0x2a43a  ldloc.s  5
0x2a43c  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0x2a441  ldloc.3
0x2a442  callvirt instance class [System.Web]System.Web.UI.Control Microsoft.Crm.Application.Components.Sdk.FormControls.Web.TabDataContainer::get_Control()
0x2a447  callvirt instance void [System.Web]System.Web.UI.ControlCollection::Add(class [System.Web]System.Web.UI.Control)
0x2a44c  ldloc.3
0x2a44d  callvirt instance bool Microsoft.Crm.Application.Components.Sdk.FormControls.Web.TabDataContainer::get_Hidden()
0x2a452  brfalse.s loc_2A467
0x2a454  ldloc.s  5
0x2a456  callvirt instance class [System.Web]System.Web.UI.CssStyleCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Style()
0x2a45b  ldc.i4.s 0x12
0x2a45d  ldstr    aNone// "none"
0x2a462  callvirt instance void [System.Web]System.Web.UI.CssStyleCollection::Add(valuetype [System.Web]System.Web.UI.HtmlTextWriterStyle, string)
0x2a467  ldarg.0
0x2a468  ldfld    class [System.Web]System.Web.UI.WebControls.Panel Microsoft.Crm.Application.Components.Sdk.FormControls.Web.TabsControl::contentPlaceHolder
0x2a46d  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0x2a472  ldloc.s  5
0x2a474  callvirt instance void [System.Web]System.Web.UI.ControlCollection::Add(class [System.Web]System.Web.UI.Control)
0x2a479  ldloc.2
0x2a47a  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x2a47f  brtrue   loc_2A26C
0x2a484  leave.s  loc_2A490
0x2a486  ldloc.2
0x2a487  brfalse.s loc_2A48F
0x2a489  ldloc.2
0x2a48a  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2a48f  endfinally
0x2a490  ldstr    aDiv_1// "DIV"
0x2a495  newobj   instance void [System.Web]System.Web.UI.HtmlControls.HtmlGenericControl::.ctor(string)
0x2a49a  stloc.1
0x2a49b  ldloc.1
0x2a49c  ldstr    aOauthexpiredal// "OAuthExpiredAlertImageInTabsHeader"
0x2a4a1  callvirt instance void [System.Web]System.Web.UI.Control::set_ID(string)
0x2a4a6  ldloc.1
0x2a4a7  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0x2a4ac  ldstr    aClass// "class"
0x2a4b1  ldstr    aOauthtokenexpi// "OAuthTokenExpiredAlertIcon"
0x2a4b6  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::Add(string, string)
0x2a4bb  ldarg.0
0x2a4bc  ldfld    class [System.Web]System.Web.UI.WebControls.Panel Microsoft.Crm.Application.Components.Sdk.FormControls.Web.TabsControl::HeaderPlaceholder
0x2a4c1  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0x2a4c6  ldloc.1
0x2a4c7  callvirt instance void [System.Web]System.Web.UI.ControlCollection::Add(class [System.Web]System.Web.UI.Control)
0x2a4cc  ldarg.0
0x2a4cd  call     instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::CreateChildControls()
0x2a4d2  ret
```
