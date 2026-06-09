# Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl::ConfigureControl

- ea: `0x1d330`
- end: `0x1dbcc`
- name: `Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl::ConfigureControl`
- size: `2204`
- prototype: ``
- caller_count: `1`
- callee_count: `52`
- tags: `registry_config, broker_com_uri`

## callers

- `0xde80`

## callees

- `0x178c0`
- `0x17930`
- `0x179b0`
- `0x179f0`
- `0x188d0`
- `0x189e0`
- `0x18a00`
- `0x1a320`
- `0x1a330`
- `0x1a340`
- `0x1a350`
- `0x1a420`
- `0x1c7f0`
- `0x1c850`
- `0x1c870`
- `0x1ca10`
- `0x1ca20`
- `0x1ca70`
- `0x1cae0`
- `0x1cb90`
- `0x1cbb0`
- `0x1cbd0`
- `0x1cc10`
- `0x1cd00`
- `0x1cd90`
- `0x1cda0`
- `0x1cde0`
- `0x1cdf0`
- `0x1ce20`
- `0x1ce40`
- `0x1ce60`
- `0x1ce80`
- `0x1cf20`
- `0x1cf60`
- `0x1d020`
- `0x1d2f0`
- `0x1d320`
- `0x1d330`
- `0x1dbd0`
- `0x1dc70`
- `0x1dd20`
- `0x1dda0`
- `0x1de00`
- `0x1de10`
- `0x1def0`
- `0x1dfb0`
- `0x1dfc0`
- `0x1e0b0`
- `0x1e120`
- `0x1e230`

## string_xrefs

- `0x1d3e4`: `/_forms/read/grid.aspx`
- `0x1d5f9`: `customControlXmlParam`
- `0x1d76d`: `/_static/_common/scripts/BusinessRulesExecution.js`

## pseudocode

```c

```

## disassembly

```asm
0x1d330  ldarg.0
0x1d331  call     instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormControlBase::ConfigureControl()
0x1d336  ldarg.0
0x1d337  call     instance bool Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl::IsCardControl()
0x1d33c  brfalse.s loc_1D394
0x1d33e  ldarg.0
0x1d33f  ldarg.0
0x1d340  callvirt instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.CardControl Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl::get_CardControl()
0x1d345  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::ConfigureChildControl(class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase)
0x1d34a  ldarg.0
0x1d34b  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x1d350  ldstr    aStaticCardcont// "/_static/_cardcontrol/CardControl.js"
0x1d355  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x1d35a  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1d35f  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri)
0x1d364  newobj   instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.DivControlRenderer::.ctor()
0x1d369  stloc.3
0x1d36a  ldloc.3
0x1d36b  ldstr    aMsCrmFormCardL// "ms-crm-Form-Card-Layout"
0x1d370  callvirt instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.IControlRenderer::set_CssClass(string value)
0x1d375  ldarg.0
0x1d376  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0x1d37b  ldloc.3
0x1d37c  callvirt instance class [System.Web]System.Web.UI.HtmlControls.HtmlContainerControl Microsoft.Crm.Application.Components.Sdk.FormControls.Web.IControlRenderer::get_ParentControl()
0x1d381  callvirt instance void [System.Web]System.Web.UI.ControlCollection::Add(class [System.Web]System.Web.UI.Control)
0x1d386  ldarg.0
0x1d387  ldloc.3
0x1d388  call     instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl::AddCardControlToPage(class Microsoft.Crm.Application.Components.Sdk.FormControls.Web.IControlRenderer renderer)
0x1d38d  ldarg.0
0x1d38e  call     instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl::SetCardControlStyleAndAttribute()
0x1d393  ret
0x1d394  ldarg.0
0x1d395  call     instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl::SetDefaultViewForGrid()
0x1d39a  ldarg.0
0x1d39b  call     instance valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.FormControlRenderMode Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormControlBase::get_RenderMode()
0x1d3a0  ldc.i4.1
0x1d3a1  bne.un   loc_1D57B
0x1d3a6  ldarg.0
0x1d3a7  call     instance bool Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl::get_IsLiteSubGrid()
0x1d3ac  brtrue   loc_1D57B
0x1d3b1  ldarg.0
0x1d3b2  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.CustomizableFormExtended Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormControlBase::get_CurrentForm()
0x1d3b7  callvirt instance string [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.CustomizableFormExtended::get_FormDataEntityId()
0x1d3bc  ldstr    aPrimaryentity// "PrimaryEntity"
0x1d3c1  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1d3c6  brfalse  loc_1D524
0x1d3cb  ldstr    aIframe_1// "iframe"
0x1d3d0  newobj   instance void [System.Web]System.Web.UI.HtmlControls.HtmlGenericControl::.ctor(string)
0x1d3d5  stloc.s  4
0x1d3d7  ldloc.s  4
0x1d3d9  ldarg.0
0x1d3da  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x1d3df  callvirt instance void [System.Web]System.Web.UI.Control::set_ID(string)
0x1d3e4  ldstr    aFormsReadGridA// "/_forms/read/grid.aspx"
0x1d3e9  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::Create(string)
0x1d3ee  stloc.s  5
0x1d3f0  ldloc.s  5
0x1d3f2  callvirt instance class [System]System.Collections.Generic.SortedDictionary`2<string, string> [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::get_Query()
0x1d3f7  ldstr    aGridid// "GridId"
0x1d3fc  ldarg.0
0x1d3fd  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x1d402  callvirt instance void class [System]System.Collections.Generic.SortedDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x1d407  ldloc.s  4
0x1d409  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0x1d40e  ldstr    aUrl// "url"
0x1d413  ldloc.s  5
0x1d415  callvirt instance string [mscorlib]System.Object::ToString()
0x1d41a  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::set_Item(string, string)
0x1d41f  ldloc.s  4
0x1d421  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0x1d426  ldstr    aClass// "class"
0x1d42b  ldstr    aSubgridIframe// "subgrid_iframe"
0x1d430  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::set_Item(string, string)
0x1d435  ldloc.s  4
0x1d437  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0x1d43c  ldstr    aScrolling// "scrolling"
0x1d441  ldstr    aNo// "no"
0x1d446  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::set_Item(string, string)
0x1d44b  ldloc.s  4
0x1d44d  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0x1d452  ldstr    aFrameborder// "frameborder"
0x1d457  ldstr    a0// "0"
0x1d45c  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::set_Item(string, string)
0x1d461  ldloc.s  4
0x1d463  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0x1d468  ldstr    aTabindex// "tabindex"
0x1d46d  ldstr    a0// "0"
0x1d472  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::set_Item(string, string)
0x1d477  ldarg.0
0x1d478  ldarg.0
0x1d479  callvirt instance string Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl::get_ChartGridMode()
0x1d47e  ldstr    aChart// "Chart"
0x1d483  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1d488  ldarg.0
0x1d489  call     instance bool Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl::get_EnableViewPicker()
0x1d48e  ldarg.0
0x1d48f  call     instance bool Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl::get_EnableQuickFind()
0x1d494  ldarg.0
0x1d495  call     instance bool Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl::get_EnableJumpBar()
0x1d49a  call     instance int32 Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl::GetGutterValue(bool showChartOnly, bool showViewPicker, bool showSearch, bool showIndex)
0x1d49f  stloc.s  6
0x1d4a1  ldarg.0
0x1d4a2  call     instance unsigned int32 Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl::get_RecordsPerPage()
0x1d4a7  ldc.i4.s 0x1C
0x1d4a9  mul
0x1d4aa  ldloc.s  6
0x1d4ac  ldc.i4.s 0x19
0x1d4ae  mul
0x1d4af  add
0x1d4b0  ldc.i4.s 0x10
0x1d4b2  add
0x1d4b3  stloc.s  7
0x1d4b5  ldloc.s  4
0x1d4b7  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0x1d4bc  ldstr    aStyle// "style"
0x1d4c1  ldstr    aHeight_0// "height: "
0x1d4c6  ldloca.s 7
0x1d4c8  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1d4cd  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x1d4d2  ldstr    aPx// "px;"
0x1d4d7  call     string [mscorlib]System.String::Concat(string, string, string)
0x1d4dc  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::set_Item(string, string)
0x1d4e1  ldloc.s  4
0x1d4e3  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0x1d4e8  ldstr    aSrc// "src"
0x1d4ed  ldstr    aStaticLoadingH// "/_static/loading.htm"
0x1d4f2  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x1d4f7  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1d4fc  callvirt instance string [mscorlib]System.Object::ToString()
0x1d501  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::set_Item(string, string)
0x1d506  ldarg.0
0x1d507  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0x1d50c  ldloc.s  4
0x1d50e  callvirt instance void [System.Web]System.Web.UI.ControlCollection::Add(class [System.Web]System.Web.UI.Control)
0x1d513  leave    loc_1DBCB
0x1d518  ldloc.s  4
0x1d51a  brfalse.s loc_1D523
0x1d51c  ldloc.s  4
0x1d51e  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1d523  endfinally
0x1d524  ldstr    aDiv// "div"
0x1d529  newobj   instance void [System.Web]System.Web.UI.HtmlControls.HtmlGenericControl::.ctor(string)
0x1d52e  stloc.s  8
0x1d530  ldloc.s  8
0x1d532  ldstr    aNoshowdiv// "noShowDiv_"
0x1d537  ldarg.0
0x1d538  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x1d53d  call     string [mscorlib]System.String::Concat(string, string)
0x1d542  callvirt instance void [System.Web]System.Web.UI.Control::set_ID(string)
0x1d547  ldloc.s  8
0x1d549  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x1d54e  ldstr    aInlinesubgridn_0// "InlineSubGridNotSupportedInROForm"
0x1d553  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x1d558  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlContainerControl::set_InnerText(string)
0x1d55d  ldarg.0
0x1d55e  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0x1d563  ldloc.s  8
0x1d565  callvirt instance void [System.Web]System.Web.UI.ControlCollection::Add(class [System.Web]System.Web.UI.Control)
0x1d56a  leave    loc_1DBCB
0x1d56f  ldloc.s  8
0x1d571  brfalse.s loc_1D57A
0x1d573  ldloc.s  8
0x1d575  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1d57a  endfinally
0x1d57b  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x1d580  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1d585  stloc.0
0x1d586  ldarg.0
0x1d587  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppGrid Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl::get_InnerGrid()
0x1d58c  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Grid.DataGrid::get_Parameters()
0x1d591  ldstr    aRelationshipty// "relationshipType"
0x1d596  ldarg.0
0x1d597  call     instance valuetype [Microsoft.Crm]Microsoft.Crm.RibbonRuleRelationshipType Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl::get_RelationshipType()
0x1d59c  box      [Microsoft.Crm]Microsoft.Crm.RibbonRuleRelationshipType
0x1d5a1  ldstr    aD_0// "d"
0x1d5a6  call     instance string [mscorlib]System.Enum::ToString(string)
0x1d5ab  callvirt instance void [System]System.Collections.Specialized.NameValueCollection::set_Item(string, string)
0x1d5b0  ldarg.0
0x1d5b1  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppGrid Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl::get_InnerGrid()
0x1d5b6  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Grid.DataGrid::get_Parameters()
0x1d5bb  ldstr    aRibboncontext// "ribbonContext"
0x1d5c0  ldarg.0
0x1d5c1  call     instance string Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl::get_RibbonContextType()
0x1d5c6  dup
0x1d5c7  brtrue.s loc_1D5CF
0x1d5c9  pop
0x1d5ca  ldstr    aHomepagegrid// "HomePageGrid"
0x1d5cf  callvirt instance void [System]System.Collections.Specialized.NameValueCollection::set_Item(string, string)
0x1d5d4  ldarg.0
0x1d5d5  call     instance bool Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl::get_IsDataSetControlFCBEnabled()
0x1d5da  brfalse.s loc_1D609
0x1d5dc  ldarg.0
0x1d5dd  call     instance string Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl::get_CustomControlXmlParam()
0x1d5e2  ldsfld   string [mscorlib]System.String::Empty
0x1d5e7  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x1d5ec  brfalse.s loc_1D609
0x1d5ee  ldarg.0
0x1d5ef  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppGrid Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl::get_InnerGrid()
0x1d5f4  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Grid.DataGrid::get_Parameters()
0x1d5f9  ldstr    aCustomcontrolx// "customControlXmlParam"
0x1d5fe  ldarg.0
0x1d5ff  call     instance string Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl::get_CustomControlXmlParam()
0x1d604  callvirt instance void [System]System.Collections.Specialized.NameValueCollection::set_Item(string, string)
0x1d609  ldarg.0
0x1d60a  callvirt instance bool Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormControlBase::get_IsEntityBound()
0x1d60f  brfalse.s loc_1D61F
0x1d611  ldarg.0
0x1d612  callvirt instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.VisualizationCompositeControl Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl::get_CompositeControl()
0x1d617  ldc.i4.0
0x1d618  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.VisualizationCompositeControl::set_EnableDrilldown(bool)
0x1d61d  br.s     loc_1D62B
0x1d61f  ldarg.0
0x1d620  callvirt instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.VisualizationCompositeControl Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl::get_CompositeControl()
0x1d625  ldc.i4.1
0x1d626  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.VisualizationCompositeControl::set_IsDashboardComponent(bool)
0x1d62b  ldarg.0
0x1d62c  call     instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl::SetCompositeControlProperties()
0x1d631  ldarg.0
0x1d632  call     instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl::ConfigureAppGridQueryFilter()
0x1d637  ldarg.0
0x1d638  ldarg.0
0x1d639  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppGrid Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl::get_InnerGrid()
0x1d63e  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::ConfigureChildControl(class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase)
0x1d643  ldarg.0
0x1d644  ldarg.0
0x1d645  callvirt instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.VisualizationCompositeControl Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl::get_CompositeControl()
0x1d64a  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::ConfigureChildControl(class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase)
0x1d64f  ldarg.0
0x1d650  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppGridQueryFilter Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl::get_QueryFilter()
0x1d655  brfalse.s loc_1D663
0x1d657  ldarg.0
0x1d658  ldarg.0
0x1d659  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppGridQueryFilter Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl::get_QueryFilter()
0x1d65e  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::ConfigureChildControl(class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase)
0x1d663  newobj   instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.DivControlRenderer::.ctor()
0x1d668  stloc.1
0x1d669  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::.ctor()
0x1d66e  stloc.2
0x1d66f  ldarg.0
0x1d670  ldfld    valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.GridTypeCode Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl::_gridType
0x1d675  ldc.i4.4
0x1d676  beq      loc_1D797
0x1d67b  ldarg.0
0x1d67c  ldfld    bool Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl::_pageHandlerEnabled
0x1d681  brfalse.s loc_1D69B
0x1d683  ldloc.1
0x1d684  ldstr    aMsCrmFormAssoc// "ms-crm-Form-AssociatedGrid-Layout"
0x1d689  ldarg.0
0x1d68a  callvirt instance string Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl::get_CssSuffix()
0x1d68f  call     string [mscorlib]System.String::Concat(string, string)
0x1d694  callvirt instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.IControlRenderer::set_CssClass(string value)
0x1d699  br.s     loc_1D6A6
0x1d69b  ldloc.1
0x1d69c  ldstr    aMsCrmFormGridL// "ms-crm-Form-Grid-Layout"
0x1d6a1  callvirt instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.IControlRenderer::set_CssClass(string value)
0x1d6a6  ldarg.0
0x1d6a7  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppGrid Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl::get_InnerGrid()
0x1d6ac  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Grid.DataGrid::get_Parameters()
0x1d6b1  ldstr    aGridtype// "GridType"
0x1d6b6  ldstr    aAssociatedgrid// "AssociatedGrid"
0x1d6bb  callvirt instance void [System]System.Collections.Specialized.NameValueCollection::set_Item(string, string)
0x1d6c0  ldarg.0
0x1d6c1  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppGrid Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl::get_InnerGrid()
0x1d6c6  callvirt instance int32 [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppGrid::get_ViewEntityTypeCode()
0x1d6cb  ldc.i4   0x2523
0x1d6d0  bne.un.s loc_1D6EC
0x1d6d2  ldarg.0
0x1d6d3  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppGrid Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl::get_InnerGrid()
0x1d6d8  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Grid.DataGrid::get_Parameters()
0x1d6dd  ldstr    aDisablecontext// "DisableContextMenu"
0x1d6e2  ldstr    a1_0// "1"
0x1d6e7  callvirt instance void [System]System.Collections.Specialized.NameValueCollection::set_Item(string, string)
0x1d6ec  call     class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl [Microsoft.Crm.Core]Microsoft.Crm.FeatureControl::get_Current()
0x1d6f1  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl::get_Features()
0x1d6f6  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer::get_EditableGridControlJsEvents()
0x1d6fb  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x1d700  call     bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.FeatureEnabledHelper::IsFeatureEnabled(class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1d705  call     class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl [Microsoft.Crm.Core]Microsoft.Crm.FeatureControl::get_Current()
0x1d70a  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl::get_Features()
0x1d70f  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer::get_EditableGridControlPbl()
0x1d714  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x1d719  call     bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.FeatureEnabledHelper::IsFeatureEnabled(class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1d71e  stloc.s  9
0x1d720  ldc.i4.0
0x1d721  stloc.s  0xA
0x1d723  dup
0x1d724  ldloc.s  9
0x1d726  or
0x1d727  brfalse.s loc_1D740
0x1d729  ldarg.0
0x1d72a  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppGrid Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl::get_InnerGrid()
0x1d72f  callvirt instance int32 [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppGrid::get_ViewEntityTypeCode()
0x1d734  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x1d739  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.DataSetControlUtility::HasWebSupportedDataSetControl(int32, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1d73e  stloc.s  0xA
0x1d740  dup
0x1d741  ldloc.s  0xA
0x1d743  and
0x1d744  brfalse.s loc_1D760
0x1d746  ldarg.0
  ... truncated ...
```
