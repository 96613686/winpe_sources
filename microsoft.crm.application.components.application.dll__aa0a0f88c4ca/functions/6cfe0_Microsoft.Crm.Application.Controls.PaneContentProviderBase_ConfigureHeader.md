# Microsoft.Crm.Application.Controls.PaneContentProviderBase::ConfigureHeader

- ea: `0x6cfe0`
- end: `0x6d668`
- name: `Microsoft.Crm.Application.Controls.PaneContentProviderBase::ConfigureHeader`
- size: `1672`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x6a720`

## callees

- `0x64190`
- `0x64b60`
- `0x6cfc0`
- `0x6cfe0`

## string_xrefs

- `0x6d0cf`: `Web.Visualization.Update.Notification`
- `0x6cff2`: `PaneWebService`
- `0x6cffd`: `/_controls/CompositeControl/CompositeControl.css.aspx`
- `0x6d0c5`: `LOCID_VP_UPDATECHARTALERT`
- `0x6d182`: `LOCID_VPD_NAMETEMPLATE`
- `0x6d18c`: `Web.Visualization.Designer.NameTemplate`
- `0x6d19d`: `LOCID_VPD_NAMETEMPLATEWITHTOP`
- `0x6d1a7`: `Web.Visualization.Designer.NameTemplateWithTop`
- `0x6d1b8`: `LOCID_VPD_NAMETEMPLATEWITHBOTTOM`
- `0x6d1c2`: `Web.Visualization.Designer.NameTemplateWithBottom`
- `0x6d1d3`: `LOCID_VPD_SERIESNAMETEMPLATE`
- `0x6d1dd`: `Web.Visualization.Designer.SeriesInNameTemplate`
- `0x6d1ee`: `LOCID_VPD_MULSERIESNAMETEMPLATE`
- `0x6d1f8`: `Web.Visualization.Designer.MultipleSeriesInNameTemplate`
- `0x6d209`: `LOCID_VPD_CATEGORYNAMETEMPLATE`
- `0x6d213`: `Web.Visualization.Designer.CategoryInNameTemplate`
- `0x6d224`: `LOCID_VPD_MULCATEGRYNAMETEMPLATE`
- `0x6d22e`: `Web.Visualization.Designer.MultipleCategoryInNameTemplate`
- `0x6d23f`: `LOCID_VPD_ELLIPSISNAMETEMPLATE`
- `0x6d249`: `Web.Visualization.Designer.EllipsisInNameTemplate`
- `0x6d2c6`: `LOCID_VPD_INCOMPLETE_CHART`
- `0x6d2d0`: `Web.Visualization.Designer.IncompleteChart`
- `0x6d2e1`: `LOCID_VPD_COMPLEXCHART`
- `0x6d2eb`: `Web.Visualization.Designer.ComplexChart`

## pseudocode

```c

```

## disassembly

```asm
0x6cfe0  ldarg.1
0x6cfe1  ldc.i4   0x200
0x6cfe6  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetHeader(valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.ControlType)
0x6cfeb  ldarg.1
0x6cfec  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::AddWrpcTokenActionPath()
0x6cff1  ldarg.1
0x6cff2  ldstr    aPanewebservice// "PaneWebService"
0x6cff7  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::AddWrpcTokenActionPathWebService(string)
0x6cffc  ldarg.1
0x6cffd  ldstr    aControlsCompos// "/_controls/CompositeControl/CompositeCo"...
0x6d002  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0x6d007  ldarg.1
0x6d008  ldstr    aLocidVpdInline// "LOCID_VPD_INLINEMSG_ONLOAD"
0x6d00d  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x6d012  ldstr    aWebVisualizati_59// "Web.Visualization.Designer.InlineMessag"...
0x6d017  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x6d01c  ldc.i4.0
0x6d01d  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x6d022  ldarg.1
0x6d023  ldstr    aLocidVpdErrOnl// "LOCID_VPD_ERR_ONLOAD"
0x6d028  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x6d02d  ldstr    aWebVisualizati_60// "Web.Visualization.Designer.ErrorDesigne"...
0x6d032  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x6d037  ldc.i4.0
0x6d038  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x6d03d  ldarg.1
0x6d03e  ldstr    aLocidVpdSaveas// "LOCID_VPD_SAVEAS_SUCCESS"
0x6d043  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x6d048  ldstr    aWebVisualizati_61// "Web.Visualization.Designer.SaveAs.Succe"...
0x6d04d  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x6d052  ldc.i4.0
0x6d053  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x6d058  ldarg.1
0x6d059  ldstr    aLocidVpdSaveSu// "LOCID_VPD_SAVE_SUCCESS"
0x6d05e  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x6d063  ldstr    aWebVisualizati_62// "Web.Visualization.Designer.Save.Success"...
0x6d068  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x6d06d  ldc.i4.0
0x6d06e  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x6d073  ldarg.1
0x6d074  ldstr    aLocidVpdSaveEr// "LOCID_VPD_SAVE_ERROR"
0x6d079  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x6d07e  ldstr    aWebVisualizati_63// "Web.Visualization.Designer.Save.ErrorMe"...
0x6d083  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x6d088  ldc.i4.0
0x6d089  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x6d08e  ldarg.1
0x6d08f  ldstr    aLocidCpNovisua// "LOCID_CP_NOVISUALIZATION"
0x6d094  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x6d099  ldstr    aWebChartsColla// "Web.Charts_Collapsed_No_Visualization"
0x6d09e  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x6d0a3  ldc.i4.0
0x6d0a4  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x6d0a9  ldarg.1
0x6d0aa  ldstr    aLocidVpDrilldo// "LOCID_VP_DRILLDOWNALERT"
0x6d0af  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x6d0b4  ldstr    aWebVisualizati_64// "Web.Visualization.Drilldown.Notificatio"...
0x6d0b9  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x6d0be  ldc.i4.0
0x6d0bf  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x6d0c4  ldarg.1
0x6d0c5  ldstr    aLocidVpUpdatec// "LOCID_VP_UPDATECHARTALERT"
0x6d0ca  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x6d0cf  ldstr    aWebVisualizati_2// "Web.Visualization.Update.Notification"
0x6d0d4  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x6d0d9  ldc.i4.0
0x6d0da  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x6d0df  ldarg.1
0x6d0e0  ldstr    aLocidVpNoassos// "LOCID_VP_NOASSOSVISUALIZATION"
0x6d0e5  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x6d0ea  ldstr    aVisualizationE// "Visualization_EmptyGridMessage"
0x6d0ef  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x6d0f4  ldc.i4.0
0x6d0f5  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x6d0fa  ldarg.1
0x6d0fb  ldstr    aLocidVpQueryap// "LOCID_VP_QUERYAPIVISUALIZATION"
0x6d100  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x6d105  ldstr    aVisualizationQ// "Visualization_QueryApiMessage"
0x6d10a  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x6d10f  ldc.i4.0
0x6d110  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x6d115  ldarg.1
0x6d116  ldstr    aLocidVpdIvSucc// "LOCID_VPD_IV_SUCCESS"
0x6d11b  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x6d120  ldstr    aWebVisualizati_65// "Web.Visualization.Designer.Import.Succe"...
0x6d125  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x6d12a  ldc.i4.0
0x6d12b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x6d130  ldarg.1
0x6d131  ldstr    aLocidVpdIvFail// "LOCID_VPD_IV_FAILURE"
0x6d136  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x6d13b  ldstr    aWebVisualizati_66// "Web.Visualization.Designer.Import.Failu"...
0x6d140  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x6d145  ldc.i4.0
0x6d146  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x6d14b  ldarg.1
0x6d14c  ldstr    aLocidVpdAltTex// "LOCID_VPD_ALT_TEXT"
0x6d151  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x6d156  ldstr    aWebVisualizati_16// "Web.Visualization_Chart_Alt_Text"
0x6d15b  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x6d160  ldc.i4.0
0x6d161  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x6d166  ldarg.1
0x6d167  ldstr    aLocidVpdIvProg// "LOCID_VPD_IV_PROGRESS"
0x6d16c  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x6d171  ldstr    aWebVisualizati_67// "Web.Visualization.Designer.Import.Impor"...
0x6d176  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x6d17b  ldc.i4.0
0x6d17c  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x6d181  ldarg.1
0x6d182  ldstr    aLocidVpdNamete// "LOCID_VPD_NAMETEMPLATE"
0x6d187  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x6d18c  ldstr    aWebVisualizati_68// "Web.Visualization.Designer.NameTemplate"
0x6d191  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x6d196  ldc.i4.0
0x6d197  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x6d19c  ldarg.1
0x6d19d  ldstr    aLocidVpdNamete_0// "LOCID_VPD_NAMETEMPLATEWITHTOP"
0x6d1a2  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x6d1a7  ldstr    aWebVisualizati_69// "Web.Visualization.Designer.NameTemplate"...
0x6d1ac  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x6d1b1  ldc.i4.0
0x6d1b2  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x6d1b7  ldarg.1
0x6d1b8  ldstr    aLocidVpdNamete_1// "LOCID_VPD_NAMETEMPLATEWITHBOTTOM"
0x6d1bd  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x6d1c2  ldstr    aWebVisualizati_70// "Web.Visualization.Designer.NameTemplate"...
0x6d1c7  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x6d1cc  ldc.i4.0
0x6d1cd  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x6d1d2  ldarg.1
0x6d1d3  ldstr    aLocidVpdSeries// "LOCID_VPD_SERIESNAMETEMPLATE"
0x6d1d8  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x6d1dd  ldstr    aWebVisualizati_71// "Web.Visualization.Designer.SeriesInName"...
0x6d1e2  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x6d1e7  ldc.i4.0
0x6d1e8  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x6d1ed  ldarg.1
0x6d1ee  ldstr    aLocidVpdMulser// "LOCID_VPD_MULSERIESNAMETEMPLATE"
0x6d1f3  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x6d1f8  ldstr    aWebVisualizati_72// "Web.Visualization.Designer.MultipleSeri"...
0x6d1fd  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x6d202  ldc.i4.0
0x6d203  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x6d208  ldarg.1
0x6d209  ldstr    aLocidVpdCatego// "LOCID_VPD_CATEGORYNAMETEMPLATE"
0x6d20e  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x6d213  ldstr    aWebVisualizati_73// "Web.Visualization.Designer.CategoryInNa"...
0x6d218  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x6d21d  ldc.i4.0
0x6d21e  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x6d223  ldarg.1
0x6d224  ldstr    aLocidVpdMulcat// "LOCID_VPD_MULCATEGRYNAMETEMPLATE"
0x6d229  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x6d22e  ldstr    aWebVisualizati_74// "Web.Visualization.Designer.MultipleCate"...
0x6d233  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x6d238  ldc.i4.0
0x6d239  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x6d23e  ldarg.1
0x6d23f  ldstr    aLocidVpdEllips// "LOCID_VPD_ELLIPSISNAMETEMPLATE"
0x6d244  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x6d249  ldstr    aWebVisualizati_75// "Web.Visualization.Designer.EllipsisInNa"...
0x6d24e  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x6d253  ldc.i4.0
0x6d254  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x6d259  ldarg.1
0x6d25a  ldstr    aLocidVpdTopico// "LOCID_VPD_TOPICON_TOOLTIP_TOP"
0x6d25f  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x6d264  ldstr    aWebVisualizati_76// "Web.Visualization.Designer.AdvancedOpti"...
0x6d269  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x6d26e  ldc.i4.0
0x6d26f  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x6d274  ldarg.1
0x6d275  ldstr    aLocidVpdTopico_0// "LOCID_VPD_TOPICON_TOOLTIP_BOTTOM"
0x6d27a  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x6d27f  ldstr    aWebVisualizati_77// "Web.Visualization.Designer.AdvancedOpti"...
0x6d284  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x6d289  ldc.i4.0
0x6d28a  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x6d28f  ldarg.1
0x6d290  ldstr    aLocidVpdAxisti// "LOCID_VPD_AXISTITLE"
0x6d295  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x6d29a  ldstr    aWebVisualizati_78// "Web.Visualization.AxisTitle"
0x6d29f  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x6d2a4  ldc.i4.0
0x6d2a5  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x6d2aa  ldarg.1
0x6d2ab  ldstr    aLocidVpdDatela// "LOCID_VPD_DATELABEL"
0x6d2b0  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x6d2b5  ldstr    aWebVisualizati_79// "Web.Visualization.AxisTitle.DateGroupin"...
0x6d2ba  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x6d2bf  ldc.i4.0
0x6d2c0  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x6d2c5  ldarg.1
0x6d2c6  ldstr    aLocidVpdIncomp// "LOCID_VPD_INCOMPLETE_CHART"
0x6d2cb  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x6d2d0  ldstr    aWebVisualizati_80// "Web.Visualization.Designer.IncompleteCh"...
0x6d2d5  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x6d2da  ldc.i4.0
0x6d2db  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x6d2e0  ldarg.1
0x6d2e1  ldstr    aLocidVpdComple// "LOCID_VPD_COMPLEXCHART"
0x6d2e6  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x6d2eb  ldstr    aWebVisualizati_81// "Web.Visualization.Designer.ComplexChart"
0x6d2f0  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x6d2f5  ldc.i4.0
0x6d2f6  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x6d2fb  ldarg.1
0x6d2fc  ldstr    aLocidVpdNodata// "LOCID_VPD_NODATA"
0x6d301  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x6d306  ldstr    aErrorMessage0x_4// "Error_Message_0x8004e011"
0x6d30b  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x6d310  ldc.i4.0
0x6d311  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x6d316  ldarg.1
0x6d317  ldstr    aLocidVpdClosew// "LOCID_VPD_CLOSEWARNING"
0x6d31c  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x6d321  ldstr    aWebVisualizati_82// "Web.Visualization.Designer.OnCloseDesig"...
0x6d326  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x6d32b  ldc.i4.0
0x6d32c  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x6d331  ldarg.1
0x6d332  ldstr    aLocidOnViewCha// "LOCID_ON_VIEW_CHANGE1"
0x6d337  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x6d33c  ldstr    aWebVisualizati_83// "Web.Visualization.Designer.OnViewChange"...
0x6d341  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x6d346  ldc.i4.0
0x6d347  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x6d34c  ldarg.1
0x6d34d  ldstr    aLocidOnViewCha_0// "LOCID_ON_VIEW_CHANGE2"
0x6d352  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x6d357  ldstr    aWebVisualizati_84// "Web.Visualization.Designer.OnViewChange"...
0x6d35c  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x6d361  ldc.i4.0
0x6d362  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x6d367  ldarg.1
0x6d368  ldstr    aLocidVpCollaps// "LOCID_VP_COLLAPSED_VIEW_NAME"
0x6d36d  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x6d372  ldstr    aFormTitleMask// "Form_Title_Mask"
0x6d377  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x6d37c  ldc.i4.0
0x6d37d  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x6d382  ldarg.1
0x6d383  ldstr    aLocidVpClpsdSt// "LOCID_VP_CLPSD_STRIP_HEADER"
0x6d388  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x6d38d  ldstr    aWebChartsColla_0// "Web.Charts_Collapsed_Label"
0x6d392  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x6d397  ldc.i4.0
0x6d398  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x6d39d  ldarg.1
0x6d39e  ldstr    aLocidVpdClpsdS// "LOCID_VPD_CLPSD_STRIP_HEADER"
0x6d3a3  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x6d3a8  ldstr    aWebChartdesign// "Web.ChartDesigner_Collapsed_Label"
0x6d3ad  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x6d3b2  ldc.i4.0
0x6d3b3  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x6d3b8  ldarg.1
0x6d3b9  ldstr    aLocidVpdClpsdN// "LOCID_VPD_CLPSD_NEW_VIS"
0x6d3be  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x6d3c3  ldstr    aWebChartdesign_0// "Web.ChartDesigner_Collapsed_New_Chart_L"...
0x6d3c8  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x6d3cd  ldc.i4.0
0x6d3ce  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x6d3d3  ldarg.1
0x6d3d4  ldstr    aLocidVpCloseEn// "LOCID_VP_CLOSE_ENLARGE_ALT"
0x6d3d9  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x6d3de  ldstr    aWebCloseEnlarg// "Web.Close_Enlarge_Chart_Alt_Text"
0x6d3e3  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x6d3e8  ldc.i4.0
0x6d3e9  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x6d3ee  ldarg.1
0x6d3ef  ldstr    aLocidVpdTextbo// "LOCID_VPD_TEXTBOXALERT"
0x6d3f4  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x6d3f9  ldstr    aWebVisualizati_85// "Web.Visualization.Designer.TextBoxAlert"
0x6d3fe  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x6d403  ldc.i4.0
0x6d404  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x6d409  ldarg.1
0x6d40a  ldstr    aLocidChartIcon// "LOCID_CHART_ICON_TOOLTIP"
0x6d40f  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x6d414  ldstr    aWebVisualizati_43// "Web.Visualization.Designer.ChartIcon.To"...
0x6d419  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x6d41e  ldc.i4.0
0x6d41f  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x6d424  ldarg.1
0x6d425  ldstr    aLocidColumnCha// "LOCID_COLUMN_CHART"
0x6d42a  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x6d42f  ldstr    aRibbonVisualiz// "Ribbon.VisualizationTab.Charts.Column"
0x6d434  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x6d439  ldc.i4.0
0x6d43a  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x6d43f  ldarg.1
0x6d440  ldstr    aLocidStackedco// "LOCID_STACKEDCOLUMN_CHART"
0x6d445  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x6d44a  ldstr    aRibbonVisualiz_12// "Ribbon.VisualizationTab.Charts.StackedC"...
0x6d44f  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x6d454  ldc.i4.0
0x6d455  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x6d45a  ldarg.1
0x6d45b  ldstr    aLocidStackedco_0// "LOCID_STACKEDCOLUMN100_CHART"
  ... truncated ...
```
