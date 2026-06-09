# Microsoft.Crm.Application.WebServices.SystemCustomization.AttributeMapSectionPainter::AddAttributeToNonMandatorySection

- ea: `0x8a00`
- end: `0x8e4d`
- name: `Microsoft.Crm.Application.WebServices.SystemCustomization.AttributeMapSectionPainter::AddAttributeToNonMandatorySection`
- size: `1101`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x84a0`

## callees

- `0x8a00`
- `0x8e50`
- `0x8f90`
- `0x90d0`

## pseudocode

```c

```

## disassembly

```asm
0x8a00  ldarg.0
0x8a01  ldarg.0
0x8a02  ldfld    class [mscorlib]System.Collections.Generic.List`1<string> Microsoft.Crm.Application.WebServices.SystemCustomization.AttributeMapSectionPainter::_attributesEligibleForSelect
0x8a07  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select Microsoft.Crm.Application.WebServices.SystemCustomization.AttributeMapSectionPainter::GetCrmFieldsSelectControl(class [mscorlib]System.Collections.Generic.List`1<string> importabeAttributes)
0x8a0c  stloc.0
0x8a0d  ldarg.1
0x8a0e  callvirt instance bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ImportAttributeMap::get_IsInternalMapping()
0x8a13  brfalse.s loc_8A41
0x8a15  ldloc.0
0x8a16  callvirt instance class [mscorlib]System.Collections.ArrayList [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select::get_OptionGroups()
0x8a1b  ldc.i4.0
0x8a1c  callvirt instance object [mscorlib]System.Collections.ArrayList::get_Item(int32)
0x8a21  castclass [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.OptionGroup
0x8a26  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x8a2b  ldstr    aImportwizardAt_4// "ImportWizard.AttributeMapPage.Attribute"...
0x8a30  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x8a35  ldstr    a4Internal// "4-Internal"
0x8a3a  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.OptionGroup::AddItem(string, string)
0x8a3f  br.s     loc_8AB0
0x8a41  ldarg.1
0x8a42  callvirt instance valuetype [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.ImportWizard.ImportEntityProcessCode [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ImportAttributeMap::get_ProcessCode()
0x8a47  ldc.i4.2
0x8a48  bne.un.s loc_8A76
0x8a4a  ldarg.1
0x8a4b  callvirt instance bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ImportAttributeMap::get_IsMandatoryAttributeMapping()
0x8a50  brtrue.s loc_8A76
0x8a52  ldloc.0
0x8a53  callvirt instance class [mscorlib]System.Collections.ArrayList [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select::get_OptionGroups()
0x8a58  ldc.i4.2
0x8a59  callvirt instance object [mscorlib]System.Collections.ArrayList::get_Item(int32)
0x8a5e  castclass [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.OptionGroup
0x8a63  ldarg.1
0x8a64  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ImportAttributeMap::get_TargetDisplayName()
0x8a69  ldarg.1
0x8a6a  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ImportAttributeMap::get_TargetAttribute()
0x8a6f  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.OptionGroup::AddItem(string, string)
0x8a74  br.s     loc_8AB0
0x8a76  ldarg.1
0x8a77  callvirt instance valuetype [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.ImportWizard.ImportEntityProcessCode [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ImportAttributeMap::get_ProcessCode()
0x8a7c  ldc.i4.3
0x8a7d  bne.un.s loc_8AB0
0x8a7f  ldarg.1
0x8a80  callvirt instance bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ImportAttributeMap::get_IsMandatoryAttributeMapping()
0x8a85  brtrue.s loc_8AB0
0x8a87  ldloc.0
0x8a88  callvirt instance class [mscorlib]System.Collections.ArrayList [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select::get_OptionGroups()
0x8a8d  ldc.i4.1
0x8a8e  callvirt instance object [mscorlib]System.Collections.ArrayList::get_Item(int32)
0x8a93  castclass [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.OptionGroup
0x8a98  dup
0x8a99  ldarg.1
0x8a9a  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ImportAttributeMap::get_TargetDisplayName()
0x8a9f  ldarg.1
0x8aa0  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ImportAttributeMap::get_TargetAttribute()
0x8aa5  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.OptionGroup::AddItem(string, string)
0x8aaa  ldc.i4.1
0x8aab  callvirt instance void [System.Web]System.Web.UI.Control::set_Visible(bool)
0x8ab0  ldloc.0
0x8ab1  ldarg.1
0x8ab2  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ImportAttributeMap::get_Id()
0x8ab7  callvirt instance void [System.Web]System.Web.UI.Control::set_ID(string)
0x8abc  ldloc.0
0x8abd  ldarg.1
0x8abe  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ImportAttributeMap::get_TargetAttribute()
0x8ac3  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select::set_Selected(string)
0x8ac8  ldarg.1
0x8ac9  callvirt instance valuetype [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.ImportWizard.ImportEntityProcessCode [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ImportAttributeMap::get_ProcessCode()
0x8ace  ldc.i4.1
0x8acf  bne.un.s loc_8ADE
0x8ad1  ldloc.0
0x8ad2  ldstr    a1Select// "1-Select"
0x8ad7  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select::set_Selected(string)
0x8adc  br.s     loc_8AF1
0x8ade  ldarg.1
0x8adf  callvirt instance valuetype [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.ImportWizard.ImportEntityProcessCode [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ImportAttributeMap::get_ProcessCode()
0x8ae4  brtrue.s loc_8AF1
0x8ae6  ldloc.0
0x8ae7  ldstr    a3Ignore// "3-Ignore"
0x8aec  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select::set_Selected(string)
0x8af1  ldarg.1
0x8af2  callvirt instance bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ImportAttributeMap::get_IsInternalMapping()
0x8af7  brfalse.s loc_8B1C
0x8af9  ldloc.0
0x8afa  ldstr    a4Internal// "4-Internal"
0x8aff  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select::set_Selected(string)
0x8b04  ldloc.0
0x8b05  ldc.i4.1
0x8b06  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::set_Disabled(bool)
0x8b0b  ldloc.0
0x8b0c  callvirt instance class [mscorlib]System.Collections.ArrayList [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select::get_ClassNames()
0x8b11  ldstr    aDisabledcontro// "DisabledControl"
0x8b16  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x8b1b  pop
0x8b1c  newobj   instance void [System.Web]System.Web.UI.HtmlControls.HtmlImage::.ctor()
0x8b21  stloc.1
0x8b22  ldloc.1
0x8b23  ldloc.0
0x8b24  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x8b29  ldstr    aImage_0// "_image"
0x8b2e  call     string [mscorlib]System.String::Concat(string, string)
0x8b33  callvirt instance void [System.Web]System.Web.UI.Control::set_ID(string)
0x8b38  ldloc.1
0x8b39  callvirt instance class [System.Web]System.Web.UI.CssStyleCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Style()
0x8b3e  ldstr    aHeight// "height"
0x8b43  ldstr    a18px// "18px"
0x8b48  callvirt instance void [System.Web]System.Web.UI.CssStyleCollection::Add(string, string)
0x8b4d  ldloc.1
0x8b4e  callvirt instance class [System.Web]System.Web.UI.CssStyleCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Style()
0x8b53  ldstr    aVerticalAlign// "vertical-align"
0x8b58  ldstr    a10// "-10%"
0x8b5d  callvirt instance void [System.Web]System.Web.UI.CssStyleCollection::Add(string, string)
0x8b62  ldarg.1
0x8b63  callvirt instance valuetype [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.ImportWizard.ImportEntityProcessCode [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ImportAttributeMap::get_ProcessCode()
0x8b68  ldc.i4.1
0x8b69  bne.un.s loc_8BC1
0x8b6b  ldloc.1
0x8b6c  ldstr    aImgsImportwiza_1// "/_imgs/importwizard_yellowwarning.gif"
0x8b71  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlImage::set_Src(string)
0x8b76  ldloc.1
0x8b77  ldstr    aImportwizardAt_7// "ImportWizard.AttributeMapPage.UnmappedI"...
0x8b7c  call     void Microsoft.Crm.Application.WebServices.SystemCustomization.AttributeMapSectionPainter::AppendToolTipToHtmlImage(class [System.Web]System.Web.UI.HtmlControls.HtmlImage image, string resourceId)
0x8b81  ldloc.1
0x8b82  callvirt instance class [System.Web]System.Web.UI.CssStyleCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Style()
0x8b87  ldstr    aCursor// "cursor"
0x8b8c  ldstr    aDefault// "default"
0x8b91  callvirt instance void [System.Web]System.Web.UI.CssStyleCollection::Add(string, string)
0x8b96  ldloc.1
0x8b97  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0x8b9c  ldstr    aTabindex// "tabindex"
0x8ba1  ldstr    a1// "-1"
0x8ba6  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::set_Item(string, string)
0x8bab  ldloc.0
0x8bac  callvirt instance class [mscorlib]System.Collections.ArrayList [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select::get_ClassNames()
0x8bb1  ldstr    aMscrmIwAmpTarg// "mscrm-iw-AMP-TargetSelectWithImage"
0x8bb6  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x8bbb  pop
0x8bbc  br       loc_8DAA
0x8bc1  ldarg.1
0x8bc2  callvirt instance valuetype [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.ImportWizard.ImportEntityProcessCode [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ImportAttributeMap::get_ProcessCode()
0x8bc7  ldc.i4.3
0x8bc8  bne.un.s loc_8C20
0x8bca  ldloc.1
0x8bcb  ldstr    aImgsImportwiza_2// "/_imgs/importwizard_newentity.gif"
0x8bd0  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlImage::set_Src(string)
0x8bd5  ldloc.1
0x8bd6  ldstr    aImportwizardAt_8// "ImportWizard.AttributeMapPage.NewAttrib"...
0x8bdb  call     void Microsoft.Crm.Application.WebServices.SystemCustomization.AttributeMapSectionPainter::AppendToolTipToHtmlImage(class [System.Web]System.Web.UI.HtmlControls.HtmlImage image, string resourceId)
0x8be0  ldloc.1
0x8be1  callvirt instance class [System.Web]System.Web.UI.CssStyleCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Style()
0x8be6  ldstr    aCursor// "cursor"
0x8beb  ldstr    aHand// "hand"
0x8bf0  callvirt instance void [System.Web]System.Web.UI.CssStyleCollection::Add(string, string)
0x8bf5  ldloc.1
0x8bf6  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0x8bfb  ldstr    aTabindex// "tabindex"
0x8c00  ldstr    a0_0// "0"
0x8c05  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::set_Item(string, string)
0x8c0a  ldloc.0
0x8c0b  callvirt instance class [mscorlib]System.Collections.ArrayList [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select::get_ClassNames()
0x8c10  ldstr    aMscrmIwAmpTarg// "mscrm-iw-AMP-TargetSelectWithImage"
0x8c15  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x8c1a  pop
0x8c1b  br       loc_8DAA
0x8c20  ldloc.0
0x8c21  callvirt instance string [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select::get_Selected()
0x8c26  ldarg.1
0x8c27  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ImportAttributeMap::get_TargetAttribute()
0x8c2c  call     bool [mscorlib]System.String::op_Equality(string, string)
0x8c31  brfalse  loc_8D5A
0x8c36  ldarg.0
0x8c37  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ImportEntity Microsoft.Crm.Application.WebServices.SystemCustomization.AttributeMapSectionPainter::_targetEntity
0x8c3c  ldarg.1
0x8c3d  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ImportAttributeMap::get_TargetAttribute()
0x8c42  callvirt instance bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ImportEntity::IsLookupAttribute(string)
0x8c47  brfalse.s loc_8C9F
0x8c49  ldloc.1
0x8c4a  ldstr    aImgsImportwiza// "/_imgs/importwizard_fielddetails.gif"
0x8c4f  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlImage::set_Src(string)
0x8c54  ldloc.1
0x8c55  ldstr    aImportwizardAt_5// "ImportWizard.AttributeMapPage.LookupIma"...
0x8c5a  call     void Microsoft.Crm.Application.WebServices.SystemCustomization.AttributeMapSectionPainter::AppendToolTipToHtmlImage(class [System.Web]System.Web.UI.HtmlControls.HtmlImage image, string resourceId)
0x8c5f  ldloc.1
0x8c60  callvirt instance class [System.Web]System.Web.UI.CssStyleCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Style()
0x8c65  ldstr    aCursor// "cursor"
0x8c6a  ldstr    aHand// "hand"
0x8c6f  callvirt instance void [System.Web]System.Web.UI.CssStyleCollection::Add(string, string)
0x8c74  ldloc.1
0x8c75  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0x8c7a  ldstr    aTabindex// "tabindex"
0x8c7f  ldstr    a0_0// "0"
0x8c84  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::set_Item(string, string)
0x8c89  ldloc.0
0x8c8a  callvirt instance class [mscorlib]System.Collections.ArrayList [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select::get_ClassNames()
0x8c8f  ldstr    aMscrmIwAmpTarg// "mscrm-iw-AMP-TargetSelectWithImage"
0x8c94  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x8c99  pop
0x8c9a  br       loc_8DAA
0x8c9f  ldarg.0
0x8ca0  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ImportEntity Microsoft.Crm.Application.WebServices.SystemCustomization.AttributeMapSectionPainter::_targetEntity
0x8ca5  ldarg.1
0x8ca6  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ImportAttributeMap::get_TargetAttribute()
0x8cab  callvirt instance bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ImportEntity::IsPicklistAttribute(string)
0x8cb0  brfalse.s loc_8D08
0x8cb2  ldloc.1
0x8cb3  ldstr    aImgsImportwiza_0// "/_imgs/importwizard_picklist_detail.gif"
0x8cb8  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlImage::set_Src(string)
0x8cbd  ldloc.1
0x8cbe  ldstr    aImportwizardAt_6// "ImportWizard.AttributeMapPage.PicklistI"...
0x8cc3  call     void Microsoft.Crm.Application.WebServices.SystemCustomization.AttributeMapSectionPainter::AppendToolTipToHtmlImage(class [System.Web]System.Web.UI.HtmlControls.HtmlImage image, string resourceId)
0x8cc8  ldloc.1
0x8cc9  callvirt instance class [System.Web]System.Web.UI.CssStyleCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Style()
0x8cce  ldstr    aCursor// "cursor"
0x8cd3  ldstr    aHand// "hand"
0x8cd8  callvirt instance void [System.Web]System.Web.UI.CssStyleCollection::Add(string, string)
0x8cdd  ldloc.1
0x8cde  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0x8ce3  ldstr    aTabindex// "tabindex"
0x8ce8  ldstr    a0_0// "0"
0x8ced  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::set_Item(string, string)
0x8cf2  ldloc.0
0x8cf3  callvirt instance class [mscorlib]System.Collections.ArrayList [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select::get_ClassNames()
0x8cf8  ldstr    aMscrmIwAmpTarg// "mscrm-iw-AMP-TargetSelectWithImage"
0x8cfd  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x8d02  pop
0x8d03  br       loc_8DAA
0x8d08  ldloc.0
0x8d09  callvirt instance class [mscorlib]System.Collections.ArrayList [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select::get_ClassNames()
0x8d0e  ldstr    aMscrmIwAmpTarg_0// "mscrm-iw-AMP-TargetSelectWithoutImage"
0x8d13  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x8d18  pop
0x8d19  ldloc.1
0x8d1a  callvirt instance class [System.Web]System.Web.UI.CssStyleCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Style()
0x8d1f  ldstr    aDisplay// "display"
0x8d24  ldstr    aNone// "none"
0x8d29  callvirt instance void [System.Web]System.Web.UI.CssStyleCollection::Add(string, string)
0x8d2e  ldloc.1
0x8d2f  callvirt instance class [System.Web]System.Web.UI.CssStyleCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Style()
0x8d34  ldstr    aCursor// "cursor"
0x8d39  ldstr    aDefault// "default"
0x8d3e  callvirt instance void [System.Web]System.Web.UI.CssStyleCollection::Add(string, string)
0x8d43  ldloc.1
0x8d44  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0x8d49  ldstr    aTabindex// "tabindex"
0x8d4e  ldstr    a1// "-1"
0x8d53  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::set_Item(string, string)
0x8d58  br.s     loc_8DAA
0x8d5a  ldloc.0
0x8d5b  callvirt instance class [mscorlib]System.Collections.ArrayList [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select::get_ClassNames()
0x8d60  ldstr    aMscrmIwAmpTarg_0// "mscrm-iw-AMP-TargetSelectWithoutImage"
0x8d65  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x8d6a  pop
0x8d6b  ldloc.1
0x8d6c  callvirt instance class [System.Web]System.Web.UI.CssStyleCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Style()
0x8d71  ldstr    aCursor// "cursor"
0x8d76  ldstr    aDefault// "default"
0x8d7b  callvirt instance void [System.Web]System.Web.UI.CssStyleCollection::Add(string, string)
0x8d80  ldloc.1
0x8d81  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0x8d86  ldstr    aTabindex// "tabindex"
0x8d8b  ldstr    a1// "-1"
0x8d90  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::set_Item(string, string)
0x8d95  ldloc.1
0x8d96  callvirt instance class [System.Web]System.Web.UI.CssStyleCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Style()
0x8d9b  ldstr    aDisplay// "display"
0x8da0  ldstr    aNone// "none"
0x8da5  callvirt instance void [System.Web]System.Web.UI.CssStyleCollection::Add(string, string)
0x8daa  ldloc.0
0x8dab  ldstr    aStyle// "style"
0x8db0  ldstr    aWidth85// "width:85%;"
0x8db5  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select::AddExpando(string, string)
0x8dba  newobj   instance void [System.Web]System.Web.UI.HtmlControls.HtmlGenericControl::.ctor()
0x8dbf  stloc.2
0x8dc0  ldloc.2
0x8dc1  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0x8dc6  ldloc.1
0x8dc7  callvirt instance void [System.Web]System.Web.UI.ControlCollection::Add(class [System.Web]System.Web.UI.Control)
0x8dcc  ldloc.2
0x8dcd  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0x8dd2  ldloc.0
0x8dd3  callvirt instance void [System.Web]System.Web.UI.ControlCollection::Add(class [System.Web]System.Web.UI.Control)
0x8dd8  ldstr    aLabel_0// "Label"
0x8ddd  newobj   instance void [System.Web]System.Web.UI.HtmlControls.HtmlGenericControl::.ctor(string)
0x8de2  stloc.3
0x8de3  ldloc.3
0x8de4  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0x8de9  ldstr    aFor// "for"
0x8dee  ldarg.1
0x8def  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ImportAttributeMap::get_Id()
0x8df4  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::set_Item(string, string)
0x8df9  ldloc.3
0x8dfa  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0x8dff  ldstr    aTitle// "title"
0x8e04  ldarg.1
0x8e05  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ImportAttributeMap::get_SourceColumn()
0x8e0a  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::set_Item(string, string)
0x8e0f  ldloc.3
0x8e10  ldarg.1
0x8e11  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ImportAttributeMap::get_SourceColumn()
0x8e16  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlContainerControl::set_InnerText(string)
0x8e1b  ldarg.0
  ... truncated ...
```
