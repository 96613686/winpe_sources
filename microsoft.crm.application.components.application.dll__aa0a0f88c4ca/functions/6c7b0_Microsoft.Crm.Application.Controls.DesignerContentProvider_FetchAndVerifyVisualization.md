# Microsoft.Crm.Application.Controls.DesignerContentProvider::FetchAndVerifyVisualization

- ea: `0x6c7b0`
- end: `0x6c86c`
- name: `Microsoft.Crm.Application.Controls.DesignerContentProvider::FetchAndVerifyVisualization`
- size: `188`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x6a640`

## callees

- `0x63f90`
- `0x640b0`
- `0x6ace0`
- `0x6c7b0`
- `0x6cfc0`
- `0x6dbf0`

## string_xrefs

- `0x6c7f3`: `currentPresentationXml`
- `0x6c7ff`: `currentDataXml`
- `0x6c81d`: `isComplexChart`

## pseudocode

```c

```

## disassembly

```asm
0x6c7b0  ldarg.0
0x6c7b1  call     instance class Microsoft.Crm.Application.Controls.VisualizationPane Microsoft.Crm.Application.Controls.PaneContentProviderBase::get_VisualizationPane()
0x6c7b6  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity Microsoft.Crm.Application.Controls.VisualizationPane::get_CurrentVisualization()
0x6c7bb  ldstr    aPresentationde// "presentationdescription"
0x6c7c0  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x6c7c5  castclass [mscorlib]System.String
0x6c7ca  stloc.0
0x6c7cb  ldarg.0
0x6c7cc  call     instance class Microsoft.Crm.Application.Controls.VisualizationPane Microsoft.Crm.Application.Controls.PaneContentProviderBase::get_VisualizationPane()
0x6c7d1  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity Microsoft.Crm.Application.Controls.VisualizationPane::get_CurrentVisualization()
0x6c7d6  ldstr    aDatadescriptio// "datadescription"
0x6c7db  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x6c7e0  castclass [mscorlib]System.String
0x6c7e5  stloc.1
0x6c7e6  ldarg.0
0x6c7e7  ldloc.1
0x6c7e8  newobj   instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Visualization.VisualizationDataDescription::.ctor(string)
0x6c7ed  stfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Visualization.VisualizationDataDescription Microsoft.Crm.Application.Controls.DesignerContentProvider::vizDataDescription
0x6c7f2  ldarg.0
0x6c7f3  ldstr    aCurrentpresent// "currentPresentationXml"
0x6c7f8  ldloc.0
0x6c7f9  call     instance void Microsoft.Crm.Application.Controls.PaneContentProviderBase::SetParameter(string name, string value)
0x6c7fe  ldarg.0
0x6c7ff  ldstr    aCurrentdataxml// "currentDataXml"
0x6c804  ldloc.1
0x6c805  call     instance void Microsoft.Crm.Application.Controls.PaneContentProviderBase::SetParameter(string name, string value)
0x6c80a  ldarg.0
0x6c80b  ldarg.0
0x6c80c  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Visualization.VisualizationDataDescription Microsoft.Crm.Application.Controls.DesignerContentProvider::vizDataDescription
0x6c811  ldloc.0
0x6c812  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Visualization.VisualizationAppHelper::IsComplexVisualization(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Visualization.VisualizationDataDescription, string)
0x6c817  stfld    bool Microsoft.Crm.Application.Controls.DesignerContentProvider::isComplexChart
0x6c81c  ldarg.0
0x6c81d  ldstr    aIscomplexchart// "isComplexChart"
0x6c822  ldarg.0
0x6c823  ldflda   bool Microsoft.Crm.Application.Controls.DesignerContentProvider::isComplexChart
0x6c828  call     instance string [mscorlib]System.Boolean::ToString()
0x6c82d  call     instance void Microsoft.Crm.Application.Controls.PaneContentProviderBase::SetParameter(string name, string value)
0x6c832  ldarg.0
0x6c833  ldstr    aUsedaliasindat// "usedAliasInDataDescription"
0x6c838  ldarg.0
0x6c839  call     instance string Microsoft.Crm.Application.Controls.DesignerContentProvider::GetUsedAlias()
0x6c83e  call     instance void Microsoft.Crm.Application.Controls.PaneContentProviderBase::SetParameter(string name, string value)
0x6c843  ldarg.0
0x6c844  call     instance class Microsoft.Crm.Application.Controls.VisualizationPane Microsoft.Crm.Application.Controls.PaneContentProviderBase::get_VisualizationPane()
0x6c849  callvirt instance valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.VisualizationType Microsoft.Crm.Application.Controls.VisualizationPane::get_VisualizationType()
0x6c84e  ldc.i4   0x457
0x6c853  bne.un.s loc_6C86B
0x6c855  ldarg.0
0x6c856  ldarg.0
0x6c857  call     instance class Microsoft.Crm.Application.Controls.VisualizationPane Microsoft.Crm.Application.Controls.PaneContentProviderBase::get_VisualizationPane()
0x6c85c  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity Microsoft.Crm.Application.Controls.VisualizationPane::get_CurrentVisualization()
0x6c861  callvirt instance bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityProxy::get_IsInstanceCustomizable()
0x6c866  stfld    bool Microsoft.Crm.Application.Controls.DesignerContentProvider::_canBeEdited
0x6c86b  ret
```
