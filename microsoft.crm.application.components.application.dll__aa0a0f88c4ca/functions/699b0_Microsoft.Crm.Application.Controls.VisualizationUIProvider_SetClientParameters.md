# Microsoft.Crm.Application.Controls.VisualizationUIProvider::SetClientParameters

- ea: `0x699b0`
- end: `0x69d3c`
- name: `Microsoft.Crm.Application.Controls.VisualizationUIProvider::SetClientParameters`
- size: `908`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x695e0`

## callees

- `0xa1f0`
- `0x665f0`
- `0x667a0`
- `0x667d0`
- `0x66810`
- `0x66850`
- `0x699b0`
- `0x69d40`
- `0x69da0`

## string_xrefs

- `0x699ed`: `<input type="hidden" id="aggFetchXml" name="aggFetchXml" value="`
- `0x69a17`: `<input type="hidden" id="filterFetchXml" name="filterFetchXml" value="`
- `0x69a6b`: `<input type="hidden" id="presXml" name="presXml" value="`
- `0x69cce`: `<input type="hidden" id="alreadyViewByAttr" name="alreadyViewByAttr" value="`
- `0x69d12`: `<input type="hidden" id="resultXml" name="resultXml" value="`

## pseudocode

```c

```

## disassembly

```asm
0x699b0  ldarg.0
0x699b1  ldfld    bool Microsoft.Crm.Application.Controls.VisualizationUIProvider::_isChartDrillable
0x699b6  brfalse.s loc_699CE
0x699b8  ldstr    aDrilldownparam// "drilldownparams"
0x699bd  ldarg.0
0x699be  ldfld    class [System]System.Collections.Specialized.NameValueCollection Microsoft.Crm.Application.Controls.VisualizationUIProvider::_parameters
0x699c3  call     class [System.Web]System.Web.UI.HtmlControls.HtmlGenericControl Microsoft.Crm.Utility.VisualizationUtility::GetParametersDiv(string id, class [System]System.Collections.Specialized.NameValueCollection parameters)
0x699c8  ldarg.1
0x699c9  callvirt instance void [System.Web]System.Web.UI.Control::RenderControl(class [System.Web]System.Web.UI.HtmlTextWriter)
0x699ce  ldarg.1
0x699cf  callvirt instance class [mscorlib]System.IO.TextWriter [System.Web]System.Web.UI.HtmlTextWriter::get_InnerWriter()
0x699d4  stloc.0
0x699d5  ldarg.0
0x699d6  ldloc.0
0x699d7  call     instance void Microsoft.Crm.Application.Controls.VisualizationUIProvider::SetTestabilityParameters(class [mscorlib]System.IO.TextWriter writer)
0x699dc  ldarg.0
0x699dd  ldfld    bool Microsoft.Crm.Application.Controls.VisualizationUIProvider::_testabilityEnabled
0x699e2  brtrue.s loc_699EC
0x699e4  ldarg.0
0x699e5  ldfld    bool Microsoft.Crm.Application.Controls.VisualizationUIProvider::_isChartDrillable
0x699ea  brfalse.s loc_69A40
0x699ec  ldloc.0
0x699ed  ldstr    aInputTypeHidde_25// "<input type=\"hidden\" id=\"aggFetchXml"...
0x699f2  ldarg.0
0x699f3  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Visualization.IVisualizationDataProvider Microsoft.Crm.Application.Controls.VisualizationUIProvider::_visualizationDataProvider
0x699f8  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Visualization.IVisualizationDataProvider::get_AggregationFetchXml()
0x699fd  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Visualization.VisualizationAppHelper::Compress(string)
0x69a02  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string)
0x69a07  ldstr    asc_F5D2A// "\">"
0x69a0c  call     string [mscorlib]System.String::Concat(string, string, string)
0x69a11  callvirt instance void [mscorlib]System.IO.TextWriter::WriteLine(string)
0x69a16  ldloc.0
0x69a17  ldstr    aInputTypeHidde_26// "<input type=\"hidden\" id=\"filterFetch"...
0x69a1c  ldarg.0
0x69a1d  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Visualization.IVisualizationDataProvider Microsoft.Crm.Application.Controls.VisualizationUIProvider::_visualizationDataProvider
0x69a22  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Visualization.IVisualizationDataProvider::get_FilterFetchXml()
0x69a27  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Visualization.VisualizationAppHelper::Compress(string)
0x69a2c  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string)
0x69a31  ldstr    asc_F5D2A// "\">"
0x69a36  call     string [mscorlib]System.String::Concat(string, string, string)
0x69a3b  callvirt instance void [mscorlib]System.IO.TextWriter::WriteLine(string)
0x69a40  ldarg.0
0x69a41  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Visualization.IVisualizationDataProvider Microsoft.Crm.Application.Controls.VisualizationUIProvider::_visualizationDataProvider
0x69a46  callvirt instance bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Visualization.IVisualizationDataProvider::get_CanUseCachedData()
0x69a4b  brfalse.s loc_69A5A
0x69a4d  ldarg.0
0x69a4e  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Visualization.IVisualizationDataProvider Microsoft.Crm.Application.Controls.VisualizationUIProvider::_visualizationDataProvider
0x69a53  callvirt instance bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Visualization.IVisualizationDataProvider::get_UseCachedData()
0x69a58  brtrue.s loc_69A8A
0x69a5a  ldarg.0
0x69a5b  ldfld    bool Microsoft.Crm.Application.Controls.VisualizationUIProvider::_isChartDrillable
0x69a60  brfalse.s loc_69A8A
0x69a62  ldarg.0
0x69a63  call     instance bool Microsoft.Crm.Application.Controls.VisualizationUIProvider::get_IsDrilldown()
0x69a68  brtrue.s loc_69A8A
0x69a6a  ldloc.0
0x69a6b  ldstr    aInputTypeHidde_27// "<input type=\"hidden\" id=\"presXml\" n"...
0x69a70  ldarg.0
0x69a71  call     instance string Microsoft.Crm.Application.Controls.VisualizationUIProvider::get_PresentationDescriptionXml()
0x69a76  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string)
0x69a7b  ldstr    asc_F5D2A// "\">"
0x69a80  call     string [mscorlib]System.String::Concat(string, string, string)
0x69a85  callvirt instance void [mscorlib]System.IO.TextWriter::WriteLine(string)
0x69a8a  ldarg.0
0x69a8b  call     instance bool Microsoft.Crm.Application.Controls.VisualizationUIProvider::get_IsDrilldown()
0x69a90  brfalse.s loc_69AB7
0x69a92  ldloc.0
0x69a93  ldstr    aInputTypeHidde_28// "<input type=\"hidden\" id=\"drillDownCh"...
0x69a98  ldarg.0
0x69a99  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Visualization.DrilldownInfo Microsoft.Crm.Application.Controls.VisualizationUIProvider::get_DrilldownData()
0x69a9e  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Visualization.DrilldownInfo::get_ChartTitle()
0x69aa3  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string)
0x69aa8  ldstr    asc_F5D2A// "\">"
0x69aad  call     string [mscorlib]System.String::Concat(string, string, string)
0x69ab2  callvirt instance void [mscorlib]System.IO.TextWriter::WriteLine(string)
0x69ab7  ldarg.0
0x69ab8  call     instance bool Microsoft.Crm.Application.Controls.VisualizationUIProvider::get_IsDrilldown()
0x69abd  brfalse.s loc_69ACF
0x69abf  ldarg.0
0x69ac0  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Visualization.DrilldownInfo Microsoft.Crm.Application.Controls.VisualizationUIProvider::get_DrilldownData()
0x69ac5  callvirt instance bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Visualization.DrilldownInfo::get_BackNavigation()
0x69aca  brtrue   loc_69C97
0x69acf  ldarg.0
0x69ad0  ldfld    bool Microsoft.Crm.Application.Controls.VisualizationUIProvider::_isChartDrillable
0x69ad5  brfalse  loc_69C97
0x69ada  ldarg.0
0x69adb  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Visualization.IVisualizationDataProvider Microsoft.Crm.Application.Controls.VisualizationUIProvider::_visualizationDataProvider
0x69ae0  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Visualization.VisualizationDataDescription [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Visualization.IVisualizationDataProvider::get_VisualizationDataDescription()
0x69ae5  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Visualization.VisualizationCategory> [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Visualization.VisualizationDataDescription::get_CategoryCollection()
0x69aea  ldc.i4.0
0x69aeb  callvirt instance var<u1> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Visualization.VisualizationCategory>::get_Item(!!T0)
0x69af0  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Visualization.VisualizationGroupBy [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Visualization.VisualizationCategory::get_PrimaryGroupBy()
0x69af5  callvirt instance bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Visualization.VisualizationGroupBy::get_IsNull()
0x69afa  brtrue   loc_69BD5
0x69aff  ldarg.0
0x69b00  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Visualization.IVisualizationDataProvider Microsoft.Crm.Application.Controls.VisualizationUIProvider::_visualizationDataProvider
0x69b05  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Visualization.VisualizationDataDescription [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Visualization.IVisualizationDataProvider::get_VisualizationDataDescription()
0x69b0a  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Visualization.VisualizationCategory> [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Visualization.VisualizationDataDescription::get_CategoryCollection()
0x69b0f  ldc.i4.0
0x69b10  callvirt instance var<u1> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Visualization.VisualizationCategory>::get_Item(!!T0)
0x69b15  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Visualization.VisualizationGroupBy [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Visualization.VisualizationCategory::get_PrimaryGroupBy()
0x69b1a  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Visualization.VisualizationAttribute [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Visualization.VisualizationGroupBy::get_VisualizationAttribute()
0x69b1f  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.AttributeExpression [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Visualization.VisualizationAttribute::get_AttributeExpression()
0x69b24  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.AttributeExpression::get_ParentEntity()
0x69b29  brfalse.s loc_69B6D
0x69b2b  ldarg.0
0x69b2c  ldarg.0
0x69b2d  call     instance string Microsoft.Crm.Application.Controls.VisualizationUIProvider::get_AlreadyViewByAttribute()
0x69b32  ldstr    asc_12FE0A// ":"
0x69b37  ldarg.0
0x69b38  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Visualization.IVisualizationDataProvider Microsoft.Crm.Application.Controls.VisualizationUIProvider::_visualizationDataProvider
0x69b3d  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Visualization.VisualizationDataDescription [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Visualization.IVisualizationDataProvider::get_VisualizationDataDescription()
0x69b42  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Visualization.VisualizationCategory> [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Visualization.VisualizationDataDescription::get_CategoryCollection()
0x69b47  ldc.i4.0
0x69b48  callvirt instance var<u1> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Visualization.VisualizationCategory>::get_Item(!!T0)
0x69b4d  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Visualization.VisualizationGroupBy [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Visualization.VisualizationCategory::get_PrimaryGroupBy()
0x69b52  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Visualization.VisualizationAttribute [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Visualization.VisualizationGroupBy::get_VisualizationAttribute()
0x69b57  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Visualization.VisualizationAttribute::get_AttributeMetadata()
0x69b5c  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_LogicalName()
0x69b61  call     string [mscorlib]System.String::Concat(string, string, string)
0x69b66  call     instance void Microsoft.Crm.Application.Controls.VisualizationUIProvider::set_AlreadyViewByAttribute(string value)
0x69b6b  br.s     loc_69BD5
0x69b6d  ldarg.0
0x69b6e  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Visualization.IVisualizationDataProvider Microsoft.Crm.Application.Controls.VisualizationUIProvider::_visualizationDataProvider
0x69b73  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Visualization.VisualizationDataDescription [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Visualization.IVisualizationDataProvider::get_VisualizationDataDescription()
0x69b78  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Visualization.VisualizationCategory> [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Visualization.VisualizationDataDescription::get_CategoryCollection()
0x69b7d  ldc.i4.0
0x69b7e  callvirt instance var<u1> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Visualization.VisualizationCategory>::get_Item(!!T0)
0x69b83  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Visualization.VisualizationGroupBy [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Visualization.VisualizationCategory::get_PrimaryGroupBy()
0x69b88  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Visualization.VisualizationAttribute [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Visualization.VisualizationGroupBy::get_VisualizationAttribute()
0x69b8d  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.AttributeExpression [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Visualization.VisualizationAttribute::get_AttributeExpression()
0x69b92  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.LinkEntityExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.AttributeExpression::get_ParentLinkEntity()
0x69b97  brfalse.s loc_69BD5
0x69b99  ldarg.0
0x69b9a  ldarg.0
0x69b9b  call     instance string Microsoft.Crm.Application.Controls.VisualizationUIProvider::get_AlreadyViewByAttribute()
0x69ba0  ldstr    asc_12FE0A// ":"
0x69ba5  ldarg.0
0x69ba6  ldarg.0
0x69ba7  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Visualization.IVisualizationDataProvider Microsoft.Crm.Application.Controls.VisualizationUIProvider::_visualizationDataProvider
0x69bac  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Visualization.VisualizationDataDescription [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Visualization.IVisualizationDataProvider::get_VisualizationDataDescription()
0x69bb1  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Visualization.VisualizationCategory> [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Visualization.VisualizationDataDescription::get_CategoryCollection()
0x69bb6  ldc.i4.0
0x69bb7  callvirt instance var<u1> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Visualization.VisualizationCategory>::get_Item(!!T0)
0x69bbc  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Visualization.VisualizationGroupBy [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Visualization.VisualizationCategory::get_PrimaryGroupBy()
0x69bc1  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Visualization.VisualizationAttribute [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Visualization.VisualizationGroupBy::get_VisualizationAttribute()
0x69bc6  call     instance string Microsoft.Crm.Application.Controls.VisualizationUIProvider::GetAttributeNameFromLinkedEntity(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Visualization.VisualizationAttribute attribute)
0x69bcb  call     string [mscorlib]System.String::Concat(string, string, string)
0x69bd0  call     instance void Microsoft.Crm.Application.Controls.VisualizationUIProvider::set_AlreadyViewByAttribute(string value)
0x69bd5  ldarg.0
0x69bd6  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Visualization.IVisualizationDataProvider Microsoft.Crm.Application.Controls.VisualizationUIProvider::_visualizationDataProvider
0x69bdb  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Visualization.VisualizationDataDescription [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Visualization.IVisualizationDataProvider::get_VisualizationDataDescription()
0x69be0  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Visualization.VisualizationCategory> [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Visualization.VisualizationDataDescription::get_CategoryCollection()
0x69be5  ldc.i4.0
0x69be6  callvirt instance var<u1> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Visualization.VisualizationCategory>::get_Item(!!T0)
0x69beb  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Visualization.VisualizationMeasureCollection> [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Visualization.VisualizationCategory::get_MeasureCollections()
0x69bf0  ldc.i4.0
0x69bf1  callvirt instance var<u1> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Visualization.VisualizationMeasureCollection>::get_Item(!!T0)
0x69bf6  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Visualization.VisualizationGroupBy> [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Visualization.VisualizationMeasureCollection::get_SecondaryGroupBys()
0x69bfb  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Visualization.VisualizationGroupBy>::GetEnumerator()
0x69c00  stloc.1
0x69c01  br.s     loc_69C80
0x69c03  ldloc.1
0x69c04  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Visualization.VisualizationGroupBy>::get_Current()
0x69c09  stloc.2
0x69c0a  ldloc.2
0x69c0b  callvirt instance bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Visualization.VisualizationGroupBy::get_IsNull()
0x69c10  brtrue.s loc_69C80
0x69c12  ldloc.2
0x69c13  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Visualization.VisualizationAttribute [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Visualization.VisualizationGroupBy::get_VisualizationAttribute()
0x69c18  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.AttributeExpression [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Visualization.VisualizationAttribute::get_AttributeExpression()
0x69c1d  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.AttributeExpression::get_ParentEntity()
0x69c22  brfalse.s loc_69C4C
0x69c24  ldarg.0
0x69c25  ldarg.0
0x69c26  call     instance string Microsoft.Crm.Application.Controls.VisualizationUIProvider::get_AlreadyViewByAttribute()
0x69c2b  ldstr    asc_12FE0A// ":"
0x69c30  ldloc.2
0x69c31  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Visualization.VisualizationAttribute [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Visualization.VisualizationGroupBy::get_VisualizationAttribute()
0x69c36  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Visualization.VisualizationAttribute::get_AttributeMetadata()
0x69c3b  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_LogicalName()
0x69c40  call     string [mscorlib]System.String::Concat(string, string, string)
0x69c45  call     instance void Microsoft.Crm.Application.Controls.VisualizationUIProvider::set_AlreadyViewByAttribute(string value)
0x69c4a  br.s     loc_69C80
0x69c4c  ldloc.2
0x69c4d  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Visualization.VisualizationAttribute [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Visualization.VisualizationGroupBy::get_VisualizationAttribute()
0x69c52  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.AttributeExpression [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Visualization.VisualizationAttribute::get_AttributeExpression()
0x69c57  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.LinkEntityExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.AttributeExpression::get_ParentLinkEntity()
0x69c5c  brfalse.s loc_69C80
0x69c5e  ldarg.0
0x69c5f  ldarg.0
0x69c60  call     instance string Microsoft.Crm.Application.Controls.VisualizationUIProvider::get_AlreadyViewByAttribute()
0x69c65  ldstr    asc_12FE0A// ":"
0x69c6a  ldarg.0
0x69c6b  ldloc.2
0x69c6c  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Visualization.VisualizationAttribute [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Visualization.VisualizationGroupBy::get_VisualizationAttribute()
0x69c71  call     instance string Microsoft.Crm.Application.Controls.VisualizationUIProvider::GetAttributeNameFromLinkedEntity(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Visualization.VisualizationAttribute attribute)
0x69c76  call     string [mscorlib]System.String::Concat(string, string, string)
0x69c7b  call     instance void Microsoft.Crm.Application.Controls.VisualizationUIProvider::set_AlreadyViewByAttribute(string value)
0x69c80  ldloc.1
0x69c81  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x69c86  brtrue   loc_69C03
0x69c8b  leave.s  loc_69CCD
0x69c8d  ldloc.1
0x69c8e  brfalse.s loc_69C96
0x69c90  ldloc.1
0x69c91  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x69c96  endfinally
0x69c97  ldarg.0
0x69c98  call     instance string Microsoft.Crm.Application.Controls.VisualizationUIProvider::get_AlreadyViewByAttribute()
0x69c9d  ldc.i4.s 0x3A
0x69c9f  callvirt instance int32 [mscorlib]System.String::LastIndexOf(char)
0x69ca4  ldc.i4.0
0x69ca5  ble.s    loc_69CCD
0x69ca7  ldarg.0
0x69ca8  ldfld    bool Microsoft.Crm.Application.Controls.VisualizationUIProvider::_isChartDrillable
0x69cad  brfalse.s loc_69CCD
0x69caf  ldarg.0
0x69cb0  ldarg.0
0x69cb1  call     instance string Microsoft.Crm.Application.Controls.VisualizationUIProvider::get_AlreadyViewByAttribute()
0x69cb6  ldarg.0
0x69cb7  call     instance string Microsoft.Crm.Application.Controls.VisualizationUIProvider::get_AlreadyViewByAttribute()
0x69cbc  ldc.i4.s 0x3A
0x69cbe  callvirt instance int32 [mscorlib]System.String::LastIndexOf(char)
0x69cc3  callvirt instance string [mscorlib]System.String::Remove(int32)
0x69cc8  call     instance void Microsoft.Crm.Application.Controls.VisualizationUIProvider::set_AlreadyViewByAttribute(string value)
0x69ccd  ldloc.0
0x69cce  ldstr    aInputTypeHidde_29// "<input type=\"hidden\" id=\"alreadyView"...
0x69cd3  ldarg.0
0x69cd4  call     instance string Microsoft.Crm.Application.Controls.VisualizationUIProvider::get_AlreadyViewByAttribute()
0x69cd9  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string)
0x69cde  ldstr    asc_F5D2A// "\">"
0x69ce3  call     string [mscorlib]System.String::Concat(string, string, string)
0x69ce8  callvirt instance void [mscorlib]System.IO.TextWriter::WriteLine(string)
0x69ced  ldarg.0
0x69cee  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Visualization.IVisualizationDataProvider Microsoft.Crm.Application.Controls.VisualizationUIProvider::_visualizationDataProvider
0x69cf3  callvirt instance bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Visualization.IVisualizationDataProvider::get_CanUseCachedData()
0x69cf8  brfalse.s loc_69D3B
0x69cfa  ldarg.0
0x69cfb  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Visualization.IVisualizationDataProvider Microsoft.Crm.Application.Controls.VisualizationUIProvider::_visualizationDataProvider
0x69d00  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Visualization.IVisualizationDataProvider::get_ResultXml()
0x69d05  callvirt instance int32 [mscorlib]System.String::get_Length()
0x69d0a  ldc.i4   0x4C4B40
0x69d0f  bgt.s    loc_69D3B
0x69d11  ldloc.0
0x69d12  ldstr    aInputTypeHidde_30// "<input type=\"hidden\" id=\"resultXml\""...
0x69d17  ldarg.0
0x69d18  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Visualization.IVisualizationDataProvider Microsoft.Crm.Application.Controls.VisualizationUIProvider::_visualizationDataProvider
0x69d1d  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Visualization.IVisualizationDataProvider::get_ResultXml()
0x69d22  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Visualization.VisualizationAppHelper::Compress(string)
0x69d27  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string)
0x69d2c  ldstr    asc_F5D2A// "\">"
0x69d31  call     string [mscorlib]System.String::Concat(string, string, string)
0x69d36  callvirt instance void [mscorlib]System.IO.TextWriter::WriteLine(string)
0x69d3b  ret
```
