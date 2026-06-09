# Microsoft.Crm.Web.Tools.SystemCustomization.RollupFields.Views.SetTargetLinkedStepSectionView::RenderView

- ea: `0xe56f0`
- end: `0xe5859`
- name: `Microsoft.Crm.Web.Tools.SystemCustomization.RollupFields.Views.SetTargetLinkedStepSectionView::RenderView`
- size: `361`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `broker_com_uri`

## callees

- `0xe56f0`
- `0xe5d40`
- `0xe6bf0`
- `0xe6c40`
- `0xeaba0`
- `0xee690`
- `0xee910`
- `0xee940`
- `0xef2f0`

## string_xrefs

- `0xe5747`: `RelatedLinkedRelationshipContainer`
- `0xe5772`: `RelatedLinkedRelationship`
- `0xe5839`: `AddRelatedLinkedEntityButton`

## pseudocode

```c

```

## disassembly

```asm
0xe56f0  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xe56f5  ldstr    a01_8// "{0}_{1}"
0xe56fa  ldc.i4.2
0xe56fb  newarr   [mscorlib]System.Object
0xe5700  dup
0xe5701  ldc.i4.0
0xe5702  ldarg.0
0xe5703  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0xe5708  stelem.ref
0xe5709  dup
0xe570a  ldc.i4.1
0xe570b  ldstr    aSection_0// "section"
0xe5710  stelem.ref
0xe5711  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xe5716  stloc.0
0xe5717  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xe571c  ldstr    aSystemcustomiz_122// "SystemCustomization.BusinessRules.Rollu"...
0xe5721  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xe5726  stloc.1
0xe5727  ldarg.0
0xe5728  ldloc.1
0xe5729  ldloc.0
0xe572a  ldstr    aRolluprelatede_0// "rolluprelatedentitysection hidecontrol"
0xe572f  ldarg.1
0xe5730  ldc.i4.0
0xe5731  call     instance void Microsoft.Crm.Web.Tools.SystemCustomization.BusinessRules.Views.SectionView::RenderSectionStart(string title, string idPrefix, string cssClass, class [System.Web]System.Web.UI.HtmlTextWriter writer, [opt] bool isOptional)
0xe5736  ldarg.1
0xe5737  ldstr    aDiv// "DIV"
0xe573c  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteBeginTag(string)
0xe5741  ldarg.1
0xe5742  ldstr    aId_1// "id"
0xe5747  ldstr    aRelatedlinkedr// "RelatedLinkedRelationshipContainer"
0xe574c  ldc.i4.0
0xe574d  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0xe5752  ldarg.1
0xe5753  ldc.i4.s 0x3E
0xe5755  callvirt instance void [mscorlib]System.IO.TextWriter::Write(char)
0xe575a  ldarg.0
0xe575b  call     instance var<u1> class Microsoft.Crm.Web.Tools.SystemCustomization.BusinessRules.Views.StepSectionView`2<class Microsoft.Crm.Web.Tools.SystemCustomization.RollupFields.ViewModels.SetTargetLinkedStepSectionViewModel, class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.RollupRuleStep>::get_ViewModel()
0xe5760  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.RelatedEntityLinked Microsoft.Crm.Web.Tools.SystemCustomization.RollupFields.ViewModels.SetTargetLinkedStepSectionViewModel::get_RelatedRelationship()
0xe5765  brfalse  loc_E581A
0xe576a  ldarg.0
0xe576b  ldarg.1
0xe576c  ldarg.0
0xe576d  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0xe5772  ldstr    aRelatedlinkedr_0// "RelatedLinkedRelationship"
0xe5777  call     string [mscorlib]System.String::Concat(string, string)
0xe577c  call     instance void class Microsoft.Crm.Web.Tools.SystemCustomization.BusinessRules.Views.StepSectionView`2<class Microsoft.Crm.Web.Tools.SystemCustomization.RollupFields.ViewModels.SetTargetLinkedStepSectionViewModel, class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.RollupRuleStep>::RenderStepStart(class [System.Web]System.Web.UI.HtmlTextWriter, string)
0xe5781  ldarg.0
0xe5782  call     instance var<u1> class Microsoft.Crm.Web.Tools.SystemCustomization.BusinessRules.Views.StepSectionView`2<class Microsoft.Crm.Web.Tools.SystemCustomization.RollupFields.ViewModels.SetTargetLinkedStepSectionViewModel, class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.RollupRuleStep>::get_ViewModel()
0xe5787  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.RelatedEntityLinked Microsoft.Crm.Web.Tools.SystemCustomization.RollupFields.ViewModels.SetTargetLinkedStepSectionViewModel::get_RelatedRelationship()
0xe578c  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntityBase::get_EntityName()
0xe5791  call     string Microsoft.Crm.Web.Tools.SystemCustomization.BusinessRules.EditorClientDataBuilder::GetEntityPuralName(string entityLogicName)
0xe5796  stloc.2
0xe5797  ldarg.0
0xe5798  call     instance var<u1> class Microsoft.Crm.Web.Tools.SystemCustomization.BusinessRules.Views.StepSectionView`2<class Microsoft.Crm.Web.Tools.SystemCustomization.RollupFields.ViewModels.SetTargetLinkedStepSectionViewModel, class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.RollupRuleStep>::get_ViewModel()
0xe579d  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.RelatedEntityLinked Microsoft.Crm.Web.Tools.SystemCustomization.RollupFields.ViewModels.SetTargetLinkedStepSectionViewModel::get_RelatedRelationship()
0xe57a2  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntityBase::get_EntityName()
0xe57a7  ldarg.0
0xe57a8  call     instance var<u1> class Microsoft.Crm.Web.Tools.SystemCustomization.BusinessRules.Views.StepSectionView`2<class Microsoft.Crm.Web.Tools.SystemCustomization.RollupFields.ViewModels.SetTargetLinkedStepSectionViewModel, class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.RollupRuleStep>::get_ViewModel()
0xe57ad  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.RelatedEntityLinked Microsoft.Crm.Web.Tools.SystemCustomization.RollupFields.ViewModels.SetTargetLinkedStepSectionViewModel::get_RelatedRelationship()
0xe57b2  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.RelatedEntity::get_RelatedAttributeName()
0xe57b7  call     string Microsoft.Crm.Web.Tools.SystemCustomization.BusinessRules.EditorClientDataBuilder::GetAttributeLocalizedName(string entityLogicName, string attributeLogicName)
0xe57bc  stloc.3
0xe57bd  ldarg.1
0xe57be  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xe57c3  ldstr    aSystemcustomiz_106// "SystemCustomization.BusinessRules.Rollu"...
0xe57c8  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xe57cd  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlEncodeForFormatString(string)
0xe57d2  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xe57d7  ldstr    aB0B// "<b>{0}</b>"
0xe57dc  ldc.i4.1
0xe57dd  newarr   [mscorlib]System.Object
0xe57e2  dup
0xe57e3  ldc.i4.0
0xe57e4  ldloc.2
0xe57e5  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlEncodeForFormatString(string)
0xe57ea  stelem.ref
0xe57eb  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xe57f0  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xe57f5  ldstr    aB0B// "<b>{0}</b>"
0xe57fa  ldc.i4.1
0xe57fb  newarr   [mscorlib]System.Object
0xe5800  dup
0xe5801  ldc.i4.0
0xe5802  ldloc.3
0xe5803  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlEncodeForFormatString(string)
0xe5808  stelem.ref
0xe5809  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xe580e  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string, object, object)
0xe5813  ldarg.0
0xe5814  ldarg.1
0xe5815  call     instance void class Microsoft.Crm.Web.Tools.SystemCustomization.BusinessRules.Views.StepSectionView`2<class Microsoft.Crm.Web.Tools.SystemCustomization.RollupFields.ViewModels.SetTargetLinkedStepSectionViewModel, class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.RollupRuleStep>::RenderStepEnd(class [System.Web]System.Web.UI.HtmlTextWriter)
0xe581a  ldarg.1
0xe581b  ldstr    aDiv// "DIV"
0xe5820  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteEndTag(string)
0xe5825  ldarg.0
0xe5826  call     instance var<u1> class Microsoft.Crm.Web.Tools.SystemCustomization.BusinessRules.Views.StepSectionView`2<class Microsoft.Crm.Web.Tools.SystemCustomization.RollupFields.ViewModels.SetTargetLinkedStepSectionViewModel, class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.RollupRuleStep>::get_ViewModel()
0xe582b  callvirt instance var<u1> class Microsoft.Crm.Web.Tools.SystemCustomization.BusinessRules.ViewModels.StepSectionViewModel`1<class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.RollupRuleStep>::get_Step()
0xe5830  call     bool Microsoft.Crm.Web.Tools.SystemCustomization.BusinessRules.ViewModels.ManageFormViewModel::IsReadOnly(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase step)
0xe5835  brtrue.s loc_E5843
0xe5837  ldarg.0
0xe5838  ldarg.1
0xe5839  ldstr    aAddrelatedlink// "AddRelatedLinkedEntityButton"
0xe583e  call     instance void Microsoft.Crm.Web.Tools.SystemCustomization.BusinessRules.Views.SectionView::RenderPlusControl(class [System.Web]System.Web.UI.HtmlTextWriter writer, string plusControlId)
0xe5843  ldarg.0
0xe5844  ldfld    class Microsoft.Crm.Web.Tools.SystemCustomization.RollupFields.Views.FilterSectionView Microsoft.Crm.Web.Tools.SystemCustomization.RollupFields.Views.SetTargetLinkedStepSectionView::_filterSectionView
0xe5849  ldarg.1
0xe584a  callvirt instance void Microsoft.Crm.Web.Tools.SystemCustomization.BusinessRules.Views.View::RenderView(class [System.Web]System.Web.UI.HtmlTextWriter writer)
0xe584f  ldarg.0
0xe5850  ldarg.1
0xe5851  ldc.i4.0
0xe5852  ldnull
0xe5853  call     instance void Microsoft.Crm.Web.Tools.SystemCustomization.BusinessRules.Views.SectionView::RenderSectionEnd(class [System.Web]System.Web.UI.HtmlTextWriter writer, bool renderPlusControl, [opt] string plusControlId)
0xe5858  ret
```
