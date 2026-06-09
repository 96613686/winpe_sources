# Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.GridControl::AddQuickAddHiddenContainerToTitleContainer

- ea: `0xdc60`
- end: `0xde3c`
- name: `Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.GridControl::AddQuickAddHiddenContainerToTitleContainer`
- size: `476`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0xbee0`

## callees

- `0xdc60`
- `0x1c730`
- `0x1c7b0`
- `0x1cb30`

## pseudocode

```c

```

## disassembly

```asm
0xdc60  ldnull
0xdc61  stloc.0
0xdc62  ldnull
0xdc63  stloc.1
0xdc64  ldarg.0
0xdc65  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0xdc6a  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string)
0xdc6f  stloc.2
0xdc70  ldarg.0
0xdc71  call     instance string Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl::get_TargetEntityType()
0xdc76  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string)
0xdc7b  stloc.3
0xdc7c  ldarg.0
0xdc7d  call     instance string Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl::get_ConnectionToEntity()
0xdc82  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string)
0xdc87  stloc.s  4
0xdc89  ldstr    aDiv// "div"
0xdc8e  newobj   instance void [System.Web]System.Web.UI.HtmlControls.HtmlGenericControl::.ctor(string)
0xdc93  dup
0xdc94  stloc.0
0xdc95  stloc.s  5
0xdc97  ldloc.0
0xdc98  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0xdc9d  ldstr    aId// "id"
0xdca2  ldstr    asc_359D6// "_"
0xdca7  ldloc.2
0xdca8  call     string [mscorlib]System.String::Concat(string, string)
0xdcad  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::Add(string, string)
0xdcb2  ldloc.0
0xdcb3  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0xdcb8  ldstr    aDummyDataAttri// "dummy-data-attributename"
0xdcbd  ldstr    asc_359D6// "_"
0xdcc2  ldloc.2
0xdcc3  call     string [mscorlib]System.String::Concat(string, string)
0xdcc8  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::Add(string, string)
0xdccd  ldloc.0
0xdcce  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0xdcd3  ldstr    aDataLayout// "data-layout"
0xdcd8  ldstr    a0// "0"
0xdcdd  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::Add(string, string)
0xdce2  ldloc.0
0xdce3  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0xdce8  ldstr    aDataFdeid// "data-fdeid"
0xdced  ldstr    aPrimaryentity// "PrimaryEntity"
0xdcf2  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::Add(string, string)
0xdcf7  ldstr    aDiv// "div"
0xdcfc  newobj   instance void [System.Web]System.Web.UI.HtmlControls.HtmlGenericControl::.ctor(string)
0xdd01  stloc.s  6
0xdd03  ldloc.s  6
0xdd05  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0xdd0a  ldstr    aClass// "class"
0xdd0f  ldstr    aMsCrmInlineVal_3// "ms-crm-Inline-Value"
0xdd14  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::Add(string, string)
0xdd19  ldloc.0
0xdd1a  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0xdd1f  ldloc.s  6
0xdd21  callvirt instance void [System.Web]System.Web.UI.ControlCollection::Add(class [System.Web]System.Web.UI.Control)
0xdd26  leave.s  loc_DD40
0xdd28  ldloc.s  6
0xdd2a  brfalse.s loc_DD33
0xdd2c  ldloc.s  6
0xdd2e  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xdd33  endfinally
0xdd34  ldloc.s  5
0xdd36  brfalse.s loc_DD3F
0xdd38  ldloc.s  5
0xdd3a  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xdd3f  endfinally
0xdd40  ldstr    aDiv// "div"
0xdd45  newobj   instance void [System.Web]System.Web.UI.HtmlControls.HtmlGenericControl::.ctor(string)
0xdd4a  stloc.s  7
0xdd4c  ldloc.s  7
0xdd4e  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0xdd53  ldstr    aId// "id"
0xdd58  ldstr    aQuickAddHidden// "quick_add_hidden_div"
0xdd5d  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::Add(string, string)
0xdd62  ldloc.s  7
0xdd64  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0xdd69  ldstr    aClass// "class"
0xdd6e  ldstr    aMsCrmHiddenCon// "ms-crm-hidden-container"
0xdd73  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::Add(string, string)
0xdd78  ldloc.s  7
0xdd7a  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0xdd7f  ldstr    aTargetentityty// "targetEntityType"
0xdd84  ldloc.3
0xdd85  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::Add(string, string)
0xdd8a  ldloc.s  7
0xdd8c  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0xdd91  ldstr    aConnectiontoen// "connectionToEntity"
0xdd96  ldloc.s  4
0xdd98  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::Add(string, string)
0xdd9d  ldloc.s  7
0xdd9f  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0xdda4  ldstr    aConnectiontoca// "connectionToCategory"
0xdda9  ldarg.0
0xddaa  call     instance unsigned int32 Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl::get_ConnectionToCategory()
0xddaf  stloc.s  8
0xddb1  ldloca.s 8
0xddb3  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentCulture()
0xddb8  call     instance string [mscorlib]System.UInt32::ToString(class [mscorlib]System.IFormatProvider)
0xddbd  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::Add(string, string)
0xddc2  ldstr    aDiv// "div"
0xddc7  newobj   instance void [System.Web]System.Web.UI.HtmlControls.HtmlGenericControl::.ctor(string)
0xddcc  dup
0xddcd  stloc.1
0xddce  stloc.s  5
0xddd0  ldloc.1
0xddd1  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0xddd6  ldstr    aId// "id"
0xdddb  ldstr    aDivEnableedit// "div_enableEdit_"
0xdde0  ldloc.2
0xdde1  call     string [mscorlib]System.String::Concat(string, string)
0xdde6  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::Add(string, string)
0xddeb  ldloc.1
0xddec  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0xddf1  ldstr    aClass// "class"
0xddf6  ldstr    aMsCrmListQuick// "ms-crm-List-QuickAddButton-FlyOut ms-cr"...
0xddfb  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::Add(string, string)
0xde00  ldloc.1
0xde01  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0xde06  ldloc.0
0xde07  callvirt instance void [System.Web]System.Web.UI.ControlCollection::Add(class [System.Web]System.Web.UI.Control)
0xde0c  leave.s  loc_DE1A
0xde0e  ldloc.s  5
0xde10  brfalse.s loc_DE19
0xde12  ldloc.s  5
0xde14  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xde19  endfinally
0xde1a  ldloc.s  7
0xde1c  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0xde21  ldloc.1
0xde22  callvirt instance void [System.Web]System.Web.UI.ControlCollection::Add(class [System.Web]System.Web.UI.Control)
0xde27  ldloc.s  7
0xde29  stloc.s  5
0xde2b  leave.s  loc_DE39
0xde2d  ldloc.s  7
0xde2f  brfalse.s loc_DE38
0xde31  ldloc.s  7
0xde33  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xde38  endfinally
0xde39  ldloc.s  5
0xde3b  ret
```
