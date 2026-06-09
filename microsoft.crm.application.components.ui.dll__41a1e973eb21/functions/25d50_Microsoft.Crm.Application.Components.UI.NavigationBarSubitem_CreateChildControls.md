# Microsoft.Crm.Application.Components.UI.NavigationBarSubitem::CreateChildControls

- ea: `0x25d50`
- end: `0x25e1d`
- name: `Microsoft.Crm.Application.Components.UI.NavigationBarSubitem::CreateChildControls`
- size: `205`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x25cc0`
- `0x25d20`

## string_xrefs

- `0x25d81`: `ms-crm-Nav-Subitem-Link`

## pseudocode

```c

```

## disassembly

```asm
0x25d50  ldarg.0
0x25d51  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0x25d56  callvirt instance void [System.Web]System.Web.UI.ControlCollection::Clear()
0x25d5b  ldarg.0
0x25d5c  call     instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0x25d61  ldstr    aClass_1// "class"
0x25d66  ldstr    aMsCrmNavSubare_1// "ms-crm-Nav-Subarea"
0x25d6b  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::set_Item(string, string)
0x25d70  newobj   instance void [System.Web]System.Web.UI.HtmlControls.HtmlAnchor::.ctor()
0x25d75  stloc.0
0x25d76  ldloc.0
0x25d77  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0x25d7c  ldstr    aClass_1// "class"
0x25d81  ldstr    aMsCrmNavSubite// "ms-crm-Nav-Subitem-Link"
0x25d86  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::set_Item(string, string)
0x25d8b  ldloc.0
0x25d8c  ldstr    aJavascript// "javascript:;"
0x25d91  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlAnchor::set_HRef(string)
0x25d96  ldloc.0
0x25d97  ldarg.0
0x25d98  ldfld    string Microsoft.Crm.Application.Components.UI.NavigationBarSubitem::_id
0x25d9d  callvirt instance void [System.Web]System.Web.UI.Control::set_ID(string)
0x25da2  ldloc.0
0x25da3  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0x25da8  ldstr    aOnclick_0// "onclick"
0x25dad  ldarg.0
0x25dae  call     instance string Microsoft.Crm.Application.Components.UI.NavigationBarSubitem::get_Action()
0x25db3  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::set_Item(string, string)
0x25db8  ldloc.0
0x25db9  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0x25dbe  ldstr    aTabindex// "tabindex"
0x25dc3  ldstr    a0// "0"
0x25dc8  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::set_Item(string, string)
0x25dcd  ldloc.0
0x25dce  ldstr    aSelf// "_self"
0x25dd3  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlAnchor::set_Target(string)
0x25dd8  ldarg.0
0x25dd9  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0x25dde  ldloc.0
0x25ddf  callvirt instance void [System.Web]System.Web.UI.ControlCollection::Add(class [System.Web]System.Web.UI.Control)
0x25de4  ldstr    aNobr_4// "nobr"
0x25de9  newobj   instance void [System.Web]System.Web.UI.HtmlControls.HtmlGenericControl::.ctor(string)
0x25dee  stloc.1
0x25def  ldloc.1
0x25df0  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0x25df5  ldstr    aClass_1// "class"
0x25dfa  ldstr    aMsCrmNavSubite_0// "ms-crm-Nav-Subitem-Title"
0x25dff  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::set_Item(string, string)
0x25e04  ldloc.1
0x25e05  ldarg.0
0x25e06  call     instance string Microsoft.Crm.Application.Components.UI.NavigationBarSubitem::get_Title()
0x25e0b  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlContainerControl::set_InnerText(string)
0x25e10  ldloc.0
0x25e11  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0x25e16  ldloc.1
0x25e17  callvirt instance void [System.Web]System.Web.UI.ControlCollection::Add(class [System.Web]System.Web.UI.Control)
0x25e1c  ret
```
