# Microsoft.Crm.Common.Web.Activities.CreateDialog::AddListItem

- ea: `0xb830`
- end: `0xb9b6`
- name: `Microsoft.Crm.Common.Web.Activities.CreateDialog::AddListItem`
- size: `390`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0xb670`

## callees

- `0xb830`
- `0xb9c0`

## string_xrefs

- `0xb948`: `dlg_create_RenderListItem_img`

## pseudocode

```c

```

## disassembly

```asm
0xb830  ldarg.0
0xb831  ldarg.3
0xb832  call     instance bool Microsoft.Crm.Common.Web.Activities.CreateDialog::CheckUserHasPrivilege(class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition[] privileges)
0xb837  brfalse  loc_B9B5
0xb83c  ldarga.s 2
0xb83e  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xb843  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0xb848  stloc.0
0xb849  ldstr    aLi// "li"
0xb84e  newobj   instance void [System.Web]System.Web.UI.HtmlControls.HtmlGenericControl::.ctor(string)
0xb853  stloc.1
0xb854  ldloc.1
0xb855  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0xb85a  ldstr    aClass// "class"
0xb85f  ldstr    aMsCrmDialogLis_0// "ms-crm-Dialog-ListItem"
0xb864  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::Add(string, string)
0xb869  ldloc.1
0xb86a  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0xb86f  ldstr    aItem// "item"
0xb874  ldloc.0
0xb875  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::Add(string, string)
0xb87a  ldloc.1
0xb87b  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0xb880  ldstr    aOnmouseover// "onmouseover"
0xb885  ldstr    aOnThis// "On(this)"
0xb88a  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::Add(string, string)
0xb88f  ldloc.1
0xb890  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0xb895  ldstr    aOnmouseout// "onmouseout"
0xb89a  ldstr    aOffThis// "Off(this)"
0xb89f  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::Add(string, string)
0xb8a4  ldloc.1
0xb8a5  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0xb8aa  ldstr    aOnclick// "onclick"
0xb8af  ldstr    aSelectitemThis// "SelectItem(this)"
0xb8b4  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::Add(string, string)
0xb8b9  ldloc.1
0xb8ba  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0xb8bf  ldstr    aOndblclick// "ondblclick"
0xb8c4  ldstr    aApplychanges_0// "applychanges()"
0xb8c9  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::Add(string, string)
0xb8ce  ldloc.1
0xb8cf  ldstr    aItem// "item"
0xb8d4  ldloc.0
0xb8d5  call     string [mscorlib]System.String::Concat(string, string)
0xb8da  callvirt instance void [System.Web]System.Web.UI.Control::set_ID(string)
0xb8df  newobj   instance void [System.Web]System.Web.UI.HtmlControls.HtmlInputRadioButton::.ctor()
0xb8e4  stloc.2
0xb8e5  ldloc.2
0xb8e6  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0xb8eb  ldstr    aClass// "class"
0xb8f0  ldstr    aMsCrmDialogLis_1// "ms-crm-Dialog-ListItemSelect"
0xb8f5  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::Add(string, string)
0xb8fa  ldloc.2
0xb8fb  ldstr    aType// "type_"
0xb900  ldloc.0
0xb901  call     string [mscorlib]System.String::Concat(string, string)
0xb906  callvirt instance void [System.Web]System.Web.UI.Control::set_ID(string)
0xb90b  ldloc.1
0xb90c  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0xb911  ldloc.2
0xb912  callvirt instance void [System.Web]System.Web.UI.ControlCollection::Add(class [System.Web]System.Web.UI.Control)
0xb917  newobj   instance void [System.Web]System.Web.UI.HtmlControls.HtmlImage::.ctor()
0xb91c  stloc.3
0xb91d  ldloc.3
0xb91e  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0xb923  ldstr    aAlt// "alt"
0xb928  ldsfld   string [mscorlib]System.String::Empty
0xb92d  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::set_Item(string, string)
0xb932  ldloc.3
0xb933  ldstr    aAbsmiddle// "absmiddle"
0xb938  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlImage::set_Align(string)
0xb93d  ldloc.3
0xb93e  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0xb943  ldstr    aClass// "class"
0xb948  ldstr    aDlgCreateRende// "dlg_create_RenderListItem_img"
0xb94d  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::Add(string, string)
0xb952  ldloc.3
0xb953  ldarg.2
0xb954  ldc.i4.0
0xb955  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xb95a  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.IconUtil::GetIconPath(int32, valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.IconType, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xb95f  callvirt instance string [mscorlib]System.Object::ToString()
0xb964  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlImage::set_Src(string)
0xb969  ldloc.1
0xb96a  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0xb96f  ldloc.3
0xb970  callvirt instance void [System.Web]System.Web.UI.ControlCollection::Add(class [System.Web]System.Web.UI.Control)
0xb975  newobj   instance void [System.Web]System.Web.UI.WebControls.Label::.ctor()
0xb97a  stloc.s  4
0xb97c  ldloc.s  4
0xb97e  ldloc.2
0xb97f  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0xb984  callvirt instance void [System.Web]System.Web.UI.WebControls.Label::set_AssociatedControlID(string)
0xb989  ldloc.s  4
0xb98b  ldarg.2
0xb98c  ldc.i4.1
0xb98d  call     string [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Utility.WebUtility::GetFmtObjName(int32, valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.NameFormatStyle)
0xb992  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlEncode(string)
0xb997  callvirt instance void [System.Web]System.Web.UI.WebControls.Label::set_Text(string)
0xb99c  ldloc.1
0xb99d  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0xb9a2  ldloc.s  4
0xb9a4  callvirt instance void [System.Web]System.Web.UI.ControlCollection::Add(class [System.Web]System.Web.UI.Control)
0xb9a9  ldarg.1
0xb9aa  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0xb9af  ldloc.1
0xb9b0  callvirt instance void [System.Web]System.Web.UI.ControlCollection::Add(class [System.Web]System.Web.UI.Control)
0xb9b5  ret
```
