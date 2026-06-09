# Microsoft.Crm.Application.WebServices.SystemCustomization.AttributeMapSectionPainter::AddAttributeMapToMandatorySection

- ea: `0x87a0`
- end: `0x89fb`
- name: `Microsoft.Crm.Application.WebServices.SystemCustomization.AttributeMapSectionPainter::AddAttributeMapToMandatorySection`
- size: `603`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x84a0`

## callees

- `0x87a0`
- `0x8f90`
- `0x90d0`

## pseudocode

```c

```

## disassembly

```asm
0x87a0  ldarg.0
0x87a1  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select Microsoft.Crm.Application.WebServices.SystemCustomization.AttributeMapSectionPainter::_sourceFieldsSelectControl
0x87a6  callvirt instance object [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControl::Clone()
0x87ab  castclass [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select
0x87b0  stloc.0
0x87b1  ldarg.2
0x87b2  ldstr    a4Internal// "4-Internal"
0x87b7  call     bool [mscorlib]System.String::op_Equality(string, string)
0x87bc  stloc.1
0x87bd  ldloc.1
0x87be  brfalse.s loc_8802
0x87c0  ldloc.0
0x87c1  callvirt instance class [mscorlib]System.Collections.ArrayList [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select::get_OptionGroups()
0x87c6  ldc.i4.0
0x87c7  callvirt instance object [mscorlib]System.Collections.ArrayList::get_Item(int32)
0x87cc  castclass [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.OptionGroup
0x87d1  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x87d6  ldstr    aImportwizardAt_4// "ImportWizard.AttributeMapPage.Attribute"...
0x87db  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x87e0  ldstr    a4Internal// "4-Internal"
0x87e5  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.OptionGroup::AddItem(string, string)
0x87ea  ldloc.0
0x87eb  ldc.i4.1
0x87ec  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::set_Disabled(bool)
0x87f1  ldloc.0
0x87f2  callvirt instance class [mscorlib]System.Collections.ArrayList [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select::get_ClassNames()
0x87f7  ldstr    aDisabledcontro// "DisabledControl"
0x87fc  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x8801  pop
0x8802  ldloc.0
0x8803  ldarg.1
0x8804  callvirt instance void [System.Web]System.Web.UI.Control::set_ID(string)
0x8809  ldloc.0
0x880a  ldarg.2
0x880b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select::set_Selected(string)
0x8810  newobj   instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.LabelUI::.ctor()
0x8815  stloc.2
0x8816  ldloc.2
0x8817  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0x881c  ldstr    aFor// "for"
0x8821  ldarg.1
0x8822  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::set_Item(string, string)
0x8827  ldloc.2
0x8828  ldarg.0
0x8829  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ImportEntity Microsoft.Crm.Application.WebServices.SystemCustomization.AttributeMapSectionPainter::_targetEntity
0x882e  ldarg.1
0x882f  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ImportEntity::GetAttributeDisplayName(string)
0x8834  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.LabelUI::set_Text(string)
0x8839  ldloc.2
0x883a  ldstr    aTitle// "title"
0x883f  ldloc.2
0x8840  callvirt instance string [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.LabelUI::get_Text()
0x8845  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControl::AddExpando(string, string)
0x884a  newobj   instance void [System.Web]System.Web.UI.HtmlControls.HtmlGenericControl::.ctor()
0x884f  stloc.3
0x8850  newobj   instance void [System.Web]System.Web.UI.HtmlControls.HtmlImage::.ctor()
0x8855  stloc.s  4
0x8857  ldloc.s  4
0x8859  ldarg.1
0x885a  ldstr    aImage_0// "_image"
0x885f  call     string [mscorlib]System.String::Concat(string, string)
0x8864  callvirt instance void [System.Web]System.Web.UI.Control::set_ID(string)
0x8869  ldloc.s  4
0x886b  callvirt instance class [System.Web]System.Web.UI.CssStyleCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Style()
0x8870  ldstr    aHeight// "height"
0x8875  ldstr    a18px// "18px"
0x887a  callvirt instance void [System.Web]System.Web.UI.CssStyleCollection::Add(string, string)
0x887f  ldloc.s  4
0x8881  callvirt instance class [System.Web]System.Web.UI.CssStyleCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Style()
0x8886  ldstr    aVerticalAlign// "vertical-align"
0x888b  ldstr    aMiddle// "middle"
0x8890  callvirt instance void [System.Web]System.Web.UI.CssStyleCollection::Add(string, string)
0x8895  ldloc.s  4
0x8897  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0x889c  ldstr    aInternalmappin// "InternalMapping"
0x88a1  ldloc.1
0x88a2  brtrue.s loc_88AB
0x88a4  ldstr    aFalse// "false"
0x88a9  br.s     loc_88B0
0x88ab  ldstr    aTrue// "true"
0x88b0  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::set_Item(string, string)
0x88b5  ldarg.0
0x88b6  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ImportEntity Microsoft.Crm.Application.WebServices.SystemCustomization.AttributeMapSectionPainter::_targetEntity
0x88bb  ldarg.1
0x88bc  callvirt instance bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ImportEntity::IsLookupAttribute(string)
0x88c1  brfalse.s loc_8921
0x88c3  ldloc.s  4
0x88c5  ldstr    aImgsImportwiza// "/_imgs/importwizard_fielddetails.gif"
0x88ca  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlImage::set_Src(string)
0x88cf  ldloc.s  4
0x88d1  ldstr    aImportwizardAt_5// "ImportWizard.AttributeMapPage.LookupIma"...
0x88d6  call     void Microsoft.Crm.Application.WebServices.SystemCustomization.AttributeMapSectionPainter::AppendToolTipToHtmlImage(class [System.Web]System.Web.UI.HtmlControls.HtmlImage image, string resourceId)
0x88db  ldloc.s  4
0x88dd  callvirt instance class [System.Web]System.Web.UI.CssStyleCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Style()
0x88e2  ldstr    aCursor// "cursor"
0x88e7  ldloc.1
0x88e8  brtrue.s loc_88F1
0x88ea  ldstr    aHand// "hand"
0x88ef  br.s     loc_88F6
0x88f1  ldstr    aDefault// "default"
0x88f6  callvirt instance void [System.Web]System.Web.UI.CssStyleCollection::Add(string, string)
0x88fb  ldloc.s  4
0x88fd  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0x8902  ldstr    aTabindex// "tabindex"
0x8907  ldstr    a0_0// "0"
0x890c  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::set_Item(string, string)
0x8911  ldloc.2
0x8912  ldstr    aMscrmIwAmpTarg// "mscrm-iw-AMP-TargetSelectWithImage"
0x8917  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.LabelUI::set_ClassName(string)
0x891c  br       loc_89D7
0x8921  ldarg.0
0x8922  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ImportEntity Microsoft.Crm.Application.WebServices.SystemCustomization.AttributeMapSectionPainter::_targetEntity
0x8927  ldarg.1
0x8928  callvirt instance bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ImportEntity::IsPicklistAttribute(string)
0x892d  brfalse.s loc_898A
0x892f  ldloc.s  4
0x8931  ldstr    aImgsImportwiza_0// "/_imgs/importwizard_picklist_detail.gif"
0x8936  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlImage::set_Src(string)
0x893b  ldloc.s  4
0x893d  ldstr    aImportwizardAt_6// "ImportWizard.AttributeMapPage.PicklistI"...
0x8942  call     void Microsoft.Crm.Application.WebServices.SystemCustomization.AttributeMapSectionPainter::AppendToolTipToHtmlImage(class [System.Web]System.Web.UI.HtmlControls.HtmlImage image, string resourceId)
0x8947  ldloc.s  4
0x8949  callvirt instance class [System.Web]System.Web.UI.CssStyleCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Style()
0x894e  ldstr    aCursor// "cursor"
0x8953  ldloc.1
0x8954  brtrue.s loc_895D
0x8956  ldstr    aHand// "hand"
0x895b  br.s     loc_8962
0x895d  ldstr    aDefault// "default"
0x8962  callvirt instance void [System.Web]System.Web.UI.CssStyleCollection::Add(string, string)
0x8967  ldloc.s  4
0x8969  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0x896e  ldstr    aTabindex// "tabindex"
0x8973  ldstr    a0_0// "0"
0x8978  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::set_Item(string, string)
0x897d  ldloc.2
0x897e  ldstr    aMscrmIwAmpTarg// "mscrm-iw-AMP-TargetSelectWithImage"
0x8983  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.LabelUI::set_ClassName(string)
0x8988  br.s     loc_89D7
0x898a  ldloc.2
0x898b  ldstr    aMscrmIwAmpTarg_0// "mscrm-iw-AMP-TargetSelectWithoutImage"
0x8990  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.LabelUI::set_ClassName(string)
0x8995  ldloc.s  4
0x8997  callvirt instance class [System.Web]System.Web.UI.CssStyleCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Style()
0x899c  ldstr    aCursor// "cursor"
0x89a1  ldstr    aDefault// "default"
0x89a6  callvirt instance void [System.Web]System.Web.UI.CssStyleCollection::Add(string, string)
0x89ab  ldloc.s  4
0x89ad  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0x89b2  ldstr    aTabindex// "tabindex"
0x89b7  ldstr    a1// "-1"
0x89bc  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::set_Item(string, string)
0x89c1  ldloc.s  4
0x89c3  callvirt instance class [System.Web]System.Web.UI.CssStyleCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Style()
0x89c8  ldstr    aDisplay// "display"
0x89cd  ldstr    aNone// "none"
0x89d2  callvirt instance void [System.Web]System.Web.UI.CssStyleCollection::Add(string, string)
0x89d7  ldloc.3
0x89d8  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0x89dd  ldloc.s  4
0x89df  callvirt instance void [System.Web]System.Web.UI.ControlCollection::Add(class [System.Web]System.Web.UI.Control)
0x89e4  ldloc.3
0x89e5  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0x89ea  ldloc.2
0x89eb  callvirt instance void [System.Web]System.Web.UI.ControlCollection::Add(class [System.Web]System.Web.UI.Control)
0x89f0  ldarg.0
0x89f1  ldloc.0
0x89f2  ldloc.3
0x89f3  ldc.i4.1
0x89f4  call     instance class [System.Web]System.Web.UI.HtmlControls.HtmlTableRow Microsoft.Crm.Application.WebServices.SystemCustomization.AttributeMapSectionPainter::InsertImportFieldMapRow(class [System.Web]System.Web.UI.Control leftColumnControl, class [System.Web]System.Web.UI.Control rightColumnControl, bool insertInMandatoryFieldsSection)
0x89f9  pop
0x89fa  ret
```
