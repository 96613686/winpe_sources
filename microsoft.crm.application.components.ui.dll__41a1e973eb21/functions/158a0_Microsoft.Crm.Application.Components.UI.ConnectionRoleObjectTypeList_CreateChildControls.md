# Microsoft.Crm.Application.Components.UI.ConnectionRoleObjectTypeList::CreateChildControls

- ea: `0x158a0`
- end: `0x15c8f`
- name: `Microsoft.Crm.Application.Components.UI.ConnectionRoleObjectTypeList::CreateChildControls`
- size: `1007`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `broker_com_uri`

## callees

- `0x154b0`
- `0x154f0`
- `0x15530`
- `0x15820`
- `0x158a0`
- `0x23c30`
- `0x24210`
- `0x24280`
- `0x2ab50`
- `0x2ab70`
- `0x2ab80`

## pseudocode

```c

```

## disassembly

```asm
0x158a0  ldarg.0
0x158a1  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0x158a6  callvirt instance void [System.Web]System.Web.UI.ControlCollection::Clear()
0x158ab  ldarg.0
0x158ac  call     instance class [mscorlib]System.Collections.ObjectModel.Collection`1<string> Microsoft.Crm.Application.Components.UI.ConnectionRoleObjectTypeList::get_ObjectTypes()
0x158b1  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<string>::get_Count()
0x158b6  ldc.i4.1
0x158b7  bne.un.s loc_158D1
0x158b9  ldarg.0
0x158ba  call     instance class [mscorlib]System.Collections.ObjectModel.Collection`1<string> Microsoft.Crm.Application.Components.UI.ConnectionRoleObjectTypeList::get_ObjectTypes()
0x158bf  ldc.i4.0
0x158c0  callvirt instance var<u1> class [mscorlib]System.Collections.ObjectModel.Collection`1<string>::get_Item(!!T0)
0x158c5  ldstr    aNone// "none"
0x158ca  call     bool [mscorlib]System.String::op_Equality(string, string)
0x158cf  brtrue.s loc_158E1
0x158d1  ldarg.0
0x158d2  call     instance class [mscorlib]System.Collections.ObjectModel.Collection`1<string> Microsoft.Crm.Application.Components.UI.ConnectionRoleObjectTypeList::get_ObjectTypes()
0x158d7  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<string>::get_Count()
0x158dc  ldc.i4.0
0x158dd  ceq
0x158df  br.s     loc_158E2
0x158e1  ldc.i4.1
0x158e2  stloc.0
0x158e3  ldstr    aUl_2// "ul"
0x158e8  newobj   instance void [System.Web]System.Web.UI.HtmlControls.HtmlGenericControl::.ctor(string)
0x158ed  stloc.1
0x158ee  ldstr    aLi_1// "li"
0x158f3  newobj   instance void [System.Web]System.Web.UI.HtmlControls.HtmlGenericControl::.ctor(string)
0x158f8  stloc.2
0x158f9  newobj   instance void [System.Web]System.Web.UI.HtmlControls.HtmlInputRadioButton::.ctor()
0x158fe  stloc.3
0x158ff  ldloc.3
0x15900  ldarg.0
0x15901  ldfld    string Microsoft.Crm.Application.Components.UI.ConnectionRoleObjectTypeList::rAllId
0x15906  callvirt instance void [System.Web]System.Web.UI.Control::set_ID(string)
0x1590b  ldloc.3
0x1590c  ldstr    a0// "0"
0x15911  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlInputControl::set_Value(string)
0x15916  ldloc.3
0x15917  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1591c  ldstr    a0Radiogroup// "{0}_RadioGroup"
0x15921  ldc.i4.1
0x15922  newarr   [mscorlib]System.Object
0x15927  dup
0x15928  ldc.i4.0
0x15929  ldarg.0
0x1592a  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x1592f  stelem.ref
0x15930  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x15935  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlInputControl::set_Name(string)
0x1593a  ldloc.3
0x1593b  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0x15940  ldstr    aClass_1// "class"
0x15945  ldstr    aMsCrmRadiobutt// "ms-crm-RadioButton"
0x1594a  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::set_Item(string, string)
0x1594f  ldloc.3
0x15950  ldloc.0
0x15951  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlInputRadioButton::set_Checked(bool)
0x15956  ldloc.3
0x15957  ldarg.0
0x15958  callvirt instance bool Microsoft.Crm.Application.Components.UI.CrmUIControl::get_ReadOnly()
0x1595d  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlControl::set_Disabled(bool)
0x15962  ldloc.2
0x15963  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0x15968  ldloc.3
0x15969  callvirt instance void [System.Web]System.Web.UI.ControlCollection::Add(class [System.Web]System.Web.UI.Control)
0x1596e  ldstr    aSpan_1// "span"
0x15973  newobj   instance void [System.Web]System.Web.UI.HtmlControls.HtmlGenericControl::.ctor(string)
0x15978  stloc.s  4
0x1597a  ldloc.s  4
0x1597c  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x15981  ldstr    aConnectionrole// "ConnectionRoleObjectTypes_All"
0x15986  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x1598b  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlEncode(string)
0x15990  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlContainerControl::set_InnerHtml(string)
0x15995  ldstr    aLabel// "label"
0x1599a  newobj   instance void [System.Web]System.Web.UI.HtmlControls.HtmlGenericControl::.ctor(string)
0x1599f  stloc.s  5
0x159a1  ldloc.s  5
0x159a3  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0x159a8  ldstr    aFor// "for"
0x159ad  ldloc.3
0x159ae  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x159b3  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::Add(string, string)
0x159b8  ldloc.s  5
0x159ba  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0x159bf  ldloc.s  4
0x159c1  callvirt instance void [System.Web]System.Web.UI.ControlCollection::Add(class [System.Web]System.Web.UI.Control)
0x159c6  ldloc.2
0x159c7  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0x159cc  ldloc.s  5
0x159ce  callvirt instance void [System.Web]System.Web.UI.ControlCollection::Add(class [System.Web]System.Web.UI.Control)
0x159d3  ldloc.1
0x159d4  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0x159d9  ldloc.2
0x159da  callvirt instance void [System.Web]System.Web.UI.ControlCollection::Add(class [System.Web]System.Web.UI.Control)
0x159df  ldstr    aLi_1// "li"
0x159e4  newobj   instance void [System.Web]System.Web.UI.HtmlControls.HtmlGenericControl::.ctor(string)
0x159e9  stloc.2
0x159ea  newobj   instance void [System.Web]System.Web.UI.HtmlControls.HtmlInputRadioButton::.ctor()
0x159ef  stloc.s  6
0x159f1  ldloc.s  6
0x159f3  ldarg.0
0x159f4  ldfld    string Microsoft.Crm.Application.Components.UI.ConnectionRoleObjectTypeList::rSelectedId
0x159f9  callvirt instance void [System.Web]System.Web.UI.Control::set_ID(string)
0x159fe  ldloc.s  6
0x15a00  ldstr    a1// "1"
0x15a05  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlInputControl::set_Value(string)
0x15a0a  ldloc.s  6
0x15a0c  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x15a11  ldstr    a0Radiogroup// "{0}_RadioGroup"
0x15a16  ldc.i4.1
0x15a17  newarr   [mscorlib]System.Object
0x15a1c  dup
0x15a1d  ldc.i4.0
0x15a1e  ldarg.0
0x15a1f  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x15a24  stelem.ref
0x15a25  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x15a2a  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlInputControl::set_Name(string)
0x15a2f  ldloc.s  6
0x15a31  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0x15a36  ldstr    aClass_1// "class"
0x15a3b  ldstr    aMsCrmRadiobutt// "ms-crm-RadioButton"
0x15a40  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::set_Item(string, string)
0x15a45  ldloc.s  6
0x15a47  ldloc.0
0x15a48  ldc.i4.0
0x15a49  ceq
0x15a4b  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlInputRadioButton::set_Checked(bool)
0x15a50  ldloc.s  6
0x15a52  ldarg.0
0x15a53  callvirt instance bool Microsoft.Crm.Application.Components.UI.CrmUIControl::get_ReadOnly()
0x15a58  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlControl::set_Disabled(bool)
0x15a5d  ldloc.2
0x15a5e  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0x15a63  ldloc.s  6
0x15a65  callvirt instance void [System.Web]System.Web.UI.ControlCollection::Add(class [System.Web]System.Web.UI.Control)
0x15a6a  ldstr    aSpan_1// "span"
0x15a6f  newobj   instance void [System.Web]System.Web.UI.HtmlControls.HtmlGenericControl::.ctor(string)
0x15a74  stloc.s  4
0x15a76  ldloc.s  4
0x15a78  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x15a7d  ldstr    aConnectionrole_0// "ConnectionRoleObjectTypes_OnlyThese"
0x15a82  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x15a87  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlEncode(string)
0x15a8c  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlContainerControl::set_InnerHtml(string)
0x15a91  ldstr    aLabel// "label"
0x15a96  newobj   instance void [System.Web]System.Web.UI.HtmlControls.HtmlGenericControl::.ctor(string)
0x15a9b  stloc.s  5
0x15a9d  ldloc.s  5
0x15a9f  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0x15aa4  ldstr    aFor// "for"
0x15aa9  ldloc.s  6
0x15aab  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x15ab0  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::Add(string, string)
0x15ab5  ldloc.s  5
0x15ab7  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0x15abc  ldloc.s  4
0x15abe  callvirt instance void [System.Web]System.Web.UI.ControlCollection::Add(class [System.Web]System.Web.UI.Control)
0x15ac3  ldloc.2
0x15ac4  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0x15ac9  ldloc.s  5
0x15acb  callvirt instance void [System.Web]System.Web.UI.ControlCollection::Add(class [System.Web]System.Web.UI.Control)
0x15ad0  ldloc.1
0x15ad1  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0x15ad6  ldloc.2
0x15ad7  callvirt instance void [System.Web]System.Web.UI.ControlCollection::Add(class [System.Web]System.Web.UI.Control)
0x15adc  ldstr    aLi_1// "li"
0x15ae1  newobj   instance void [System.Web]System.Web.UI.HtmlControls.HtmlGenericControl::.ctor(string)
0x15ae6  stloc.2
0x15ae7  ldstr    aDiv_4// "div"
0x15aec  newobj   instance void [System.Web]System.Web.UI.HtmlControls.HtmlGenericControl::.ctor(string)
0x15af1  stloc.s  7
0x15af3  ldloc.s  7
0x15af5  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0x15afa  ldstr    aClass_1// "class"
0x15aff  ldstr    aMsConnectionro// "ms-connectionroleobjecttypecodelist-typ"...
0x15b04  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::set_Item(string, string)
0x15b09  ldstr    aUl_2// "ul"
0x15b0e  newobj   instance void [System.Web]System.Web.UI.HtmlControls.HtmlGenericControl::.ctor(string)
0x15b13  stloc.s  8
0x15b15  ldarg.0
0x15b16  ldfld    class [mscorlib]System.Collections.Generic.List`1<class AllTypes> Microsoft.Crm.Application.Components.UI.ConnectionRoleObjectTypeList::allTypes
0x15b1b  newobj   instance void AllTypesComparer::.ctor()
0x15b20  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class AllTypes>::Sort(class [mscorlib]System.Collections.Generic.IComparer`1<var<u1>>)
0x15b25  ldnull
0x15b26  stloc.s  9
0x15b28  ldc.i4.0
0x15b29  stloc.s  0xA
0x15b2b  br       loc_15C49
0x15b30  ldarg.0
0x15b31  ldfld    class [mscorlib]System.Collections.Generic.List`1<class AllTypes> Microsoft.Crm.Application.Components.UI.ConnectionRoleObjectTypeList::allTypes
0x15b36  ldloc.s  0xA
0x15b38  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<class AllTypes>::get_Item(!!T0)
0x15b3d  stloc.s  9
0x15b3f  ldstr    aLi_1// "li"
0x15b44  newobj   instance void [System.Web]System.Web.UI.HtmlControls.HtmlGenericControl::.ctor(string)
0x15b49  stloc.s  0xB
0x15b4b  newobj   instance void Microsoft.Crm.Application.Components.UI.CheckBox::.ctor()
0x15b50  stloc.s  0xC
0x15b52  ldloc.s  0xC
0x15b54  ldloc.s  9
0x15b56  callvirt instance string AllTypes::get_LogicalName()
0x15b5b  callvirt instance void Microsoft.Crm.Application.Components.UI.CheckBox::set_Value(string value)
0x15b60  ldloc.s  0xC
0x15b62  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x15b67  ldstr    a0Checkbox1// "{0}_CheckBox{1}"
0x15b6c  ldc.i4.2
0x15b6d  newarr   [mscorlib]System.Object
0x15b72  dup
0x15b73  ldc.i4.0
0x15b74  ldarg.0
0x15b75  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x15b7a  stelem.ref
0x15b7b  dup
0x15b7c  ldc.i4.1
0x15b7d  ldloc.s  9
0x15b7f  callvirt instance string AllTypes::get_LogicalName()
0x15b84  stelem.ref
0x15b85  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x15b8a  callvirt instance void [System.Web]System.Web.UI.Control::set_ID(string)
0x15b8f  ldloc.s  0xC
0x15b91  ldstr    aDonotsubmit// "DoNotSubmit"
0x15b96  ldstr    a1// "1"
0x15b9b  callvirt instance void Microsoft.Crm.Application.Components.UI.CrmUIControl::AddExpando(string name, string value)
0x15ba0  ldloc.s  0xC
0x15ba2  ldarg.0
0x15ba3  call     instance class [mscorlib]System.Collections.ObjectModel.Collection`1<string> Microsoft.Crm.Application.Components.UI.ConnectionRoleObjectTypeList::get_ObjectTypes()
0x15ba8  ldloc.s  9
0x15baa  callvirt instance string AllTypes::get_LogicalName()
0x15baf  callvirt instance bool class [mscorlib]System.Collections.ObjectModel.Collection`1<string>::Contains(var<u1>)
0x15bb4  callvirt instance void Microsoft.Crm.Application.Components.UI.CheckBox::set_Checked(bool value)
0x15bb9  ldloc.s  0xC
0x15bbb  ldarg.0
0x15bbc  callvirt instance bool Microsoft.Crm.Application.Components.UI.CrmUIControl::get_ReadOnly()
0x15bc1  ldloc.0
0x15bc2  or
0x15bc3  callvirt instance void Microsoft.Crm.Application.Components.UI.CrmUIControlBase::set_Disabled(bool value)
0x15bc8  ldloc.s  0xB
0x15bca  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0x15bcf  ldloc.s  0xC
0x15bd1  callvirt instance void [System.Web]System.Web.UI.ControlCollection::Add(class [System.Web]System.Web.UI.Control)
0x15bd6  ldstr    aSpan_1// "span"
0x15bdb  newobj   instance void [System.Web]System.Web.UI.HtmlControls.HtmlGenericControl::.ctor(string)
0x15be0  stloc.s  4
0x15be2  ldloc.s  4
0x15be4  ldloc.s  9
0x15be6  callvirt instance string AllTypes::get_DisplayName()
0x15beb  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlEncode(string)
0x15bf0  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlContainerControl::set_InnerHtml(string)
0x15bf5  ldstr    aLabel// "label"
0x15bfa  newobj   instance void [System.Web]System.Web.UI.HtmlControls.HtmlGenericControl::.ctor(string)
0x15bff  stloc.s  5
0x15c01  ldloc.s  5
0x15c03  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0x15c08  ldstr    aFor// "for"
0x15c0d  ldloc.s  0xC
0x15c0f  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x15c14  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::Add(string, string)
0x15c19  ldloc.s  5
0x15c1b  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0x15c20  ldloc.s  4
0x15c22  callvirt instance void [System.Web]System.Web.UI.ControlCollection::Add(class [System.Web]System.Web.UI.Control)
0x15c27  ldloc.s  0xB
0x15c29  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0x15c2e  ldloc.s  5
0x15c30  callvirt instance void [System.Web]System.Web.UI.ControlCollection::Add(class [System.Web]System.Web.UI.Control)
0x15c35  ldloc.s  8
0x15c37  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0x15c3c  ldloc.s  0xB
0x15c3e  callvirt instance void [System.Web]System.Web.UI.ControlCollection::Add(class [System.Web]System.Web.UI.Control)
0x15c43  ldloc.s  0xA
0x15c45  ldc.i4.1
0x15c46  add
0x15c47  stloc.s  0xA
0x15c49  ldloc.s  0xA
0x15c4b  ldarg.0
0x15c4c  ldfld    class [mscorlib]System.Collections.Generic.List`1<class AllTypes> Microsoft.Crm.Application.Components.UI.ConnectionRoleObjectTypeList::allTypes
0x15c51  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class AllTypes>::get_Count()
0x15c56  blt      loc_15B30
0x15c5b  ldloc.s  7
0x15c5d  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0x15c62  ldloc.s  8
0x15c64  callvirt instance void [System.Web]System.Web.UI.ControlCollection::Add(class [System.Web]System.Web.UI.Control)
0x15c69  ldloc.2
0x15c6a  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0x15c6f  ldloc.s  7
0x15c71  callvirt instance void [System.Web]System.Web.UI.ControlCollection::Add(class [System.Web]System.Web.UI.Control)
0x15c76  ldloc.1
0x15c77  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0x15c7c  ldloc.2
0x15c7d  callvirt instance void [System.Web]System.Web.UI.ControlCollection::Add(class [System.Web]System.Web.UI.Control)
0x15c82  ldarg.0
0x15c83  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0x15c88  ldloc.1
0x15c89  callvirt instance void [System.Web]System.Web.UI.ControlCollection::Add(class [System.Web]System.Web.UI.Control)
0x15c8e  ret
```
