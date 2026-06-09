# Microsoft.Crm.Application.Controls.DataSetControl::ConfigureHeader

- ea: `0x527b0`
- end: `0x52e51`
- name: `Microsoft.Crm.Application.Controls.DataSetControl::ConfigureHeader`
- size: `1697`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x56580`

## callees

- `0x527b0`
- `0x52e60`
- `0x52ee0`
- `0x52f30`
- `0x53d20`
- `0x53d50`
- `0x53d60`

## string_xrefs

- `0x5287a`: `/_static/_common/scripts/es6-shim.js`
- `0x528dc`: `LoadDataSetControlLibrariesOnConfigureHeader`
- `0x5294d`: `customControlXmlParam`
- `0x52aae`: `customControlXmlParam`
- `0x52ad1`: `/customControl/parameters/msinternal.isvisibleinmocaonly`
- `0x52b58`: `manifest`
- `0x52bd5`: `manifest`
- `0x52ba0`: `/_static/_common/scripts/react.js`
- `0x52bbf`: `/_static/_common/scripts/CustomControlsCommon.js`

## pseudocode

```c

```

## disassembly

```asm
0x527b0  call     bool Microsoft.Crm.Application.Controls.DataSetControl::IsDataSetControlFCBEnabled()
0x527b5  brtrue.s loc_527B8
0x527b7  ret
0x527b8  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x527bd  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.HttpContext::get_Request()
0x527c2  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x527c7  stloc.0
0x527c8  ldloc.0
0x527c9  ldstr    aWorkflowid// "workflowid"
0x527ce  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::Get(string)
0x527d3  stloc.1
0x527d4  ldloc.0
0x527d5  ldstr    aStepid_0// "stepid"
0x527da  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::Get(string)
0x527df  stloc.2
0x527e0  ldloc.1
0x527e1  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x527e6  brtrue.s loc_527F3
0x527e8  ldloc.2
0x527e9  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x527ee  ldc.i4.0
0x527ef  ceq
0x527f1  br.s     loc_527F4
0x527f3  ldc.i4.0
0x527f4  brfalse.s loc_527F7
0x527f6  ret
0x527f7  ldloc.0
0x527f8  ldstr    aPrintpreview// "printpreview"
0x527fd  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::Get(string)
0x52802  ldloca.s 3
0x52804  call     bool [mscorlib]System.Boolean::TryParse(string, bool&)
0x52809  pop
0x5280a  ldloc.3
0x5280b  brtrue.s loc_52828
0x5280d  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x52812  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.HttpContext::get_Request()
0x52817  callvirt instance string [System.Web]System.Web.HttpRequest::get_FilePath()
0x5281c  ldstr    aPrintAspx// "print.aspx"
0x52821  callvirt instance bool [mscorlib]System.String::Contains(string)
0x52826  br.s     loc_52829
0x52828  ldc.i4.1
0x52829  stloc.3
0x5282a  ldloc.3
0x5282b  brfalse.s loc_5282E
0x5282d  ret
0x5282e  ldarg.0
0x5282f  ldfld    class Microsoft.Crm.Application.Controls.AppGrid Microsoft.Crm.Application.Controls.DataSetControl::_appGrid
0x52834  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Grid.DataGrid::get_Parameters()
0x52839  ldstr    aLookupstyle_1// "LookupStyle"
0x5283e  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x52843  brtrue.s loc_5286E
0x52845  ldarg.0
0x52846  ldfld    class Microsoft.Crm.Application.Controls.AppGrid Microsoft.Crm.Application.Controls.DataSetControl::_appGrid
0x5284b  callvirt instance string [System.Web]System.Web.UI.Control::get_TemplateSourceDirectory()
0x52850  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x52855  brtrue.s loc_5286F
0x52857  ldarg.0
0x52858  ldfld    class Microsoft.Crm.Application.Controls.AppGrid Microsoft.Crm.Application.Controls.DataSetControl::_appGrid
0x5285d  callvirt instance string [System.Web]System.Web.UI.Control::get_TemplateSourceDirectory()
0x52862  ldstr    aViewduplicates// "ViewDuplicates"
0x52867  callvirt instance bool [mscorlib]System.String::Contains(string)
0x5286c  brfalse.s loc_5286F
0x5286e  ret
0x5286f  ldarg.0
0x52870  ldfld    class Microsoft.Crm.Application.Controls.AppGrid Microsoft.Crm.Application.Controls.DataSetControl::_appGrid
0x52875  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x5287a  ldstr    aStaticCommonSc_7// "/_static/_common/scripts/es6-shim.js"
0x5287f  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x52884  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x52889  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri)
0x5288e  ldarg.0
0x5288f  ldfld    class Microsoft.Crm.Application.Controls.AppGrid Microsoft.Crm.Application.Controls.DataSetControl::_appGrid
0x52894  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x52899  ldstr    aStaticGridData// "/_static/_grid/DataSetControl.js"
0x5289e  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x528a3  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x528a8  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri)
0x528ad  ldarg.0
0x528ae  call     instance void Microsoft.Crm.Application.Controls.DataSetControl::LoadStaticResources()
0x528b3  ldarg.0
0x528b4  ldfld    class Microsoft.Crm.Application.Controls.AppGrid Microsoft.Crm.Application.Controls.DataSetControl::_appGrid
0x528b9  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Grid.DataGrid::get_Parameters()
0x528be  ldstr    aOtc// "otc"
0x528c3  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x528c8  ldloca.s 4
0x528ca  call     bool [mscorlib]System.Int32::TryParse(string, int32&)
0x528cf  brfalse  loc_52E50
0x528d4  ldarg.0
0x528d5  ldloc.s  4
0x528d7  call     instance void Microsoft.Crm.Application.Controls.DataSetControl::SetControlFlags(int32 otc)
0x528dc  ldstr    aLoaddatasetcon// "LoadDataSetControlLibrariesOnConfigureH"...
0x528e1  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.MetricsStopwatch::.ctor(string)
0x528e6  stloc.s  5
0x528e8  ldloc.s  5
0x528ea  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.MetricsStopwatch::Start()
0x528ef  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x528f4  stloc.s  6
0x528f6  ldsfld   string [mscorlib]System.String::Empty
0x528fb  stloc.s  7
0x528fd  ldarg.0
0x528fe  ldfld    class Microsoft.Crm.Application.Controls.AppGrid Microsoft.Crm.Application.Controls.DataSetControl::_appGrid
0x52903  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Grid.DataGrid::get_Parameters()
0x52908  ldstr    aGridtype// "GridType"
0x5290d  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x52912  ldstr    aSubgrid// "SubGrid"
0x52917  call     bool [mscorlib]System.String::op_Equality(string, string)
0x5291c  stloc.s  8
0x5291e  ldarg.0
0x5291f  ldfld    class Microsoft.Crm.Application.Controls.AppGrid Microsoft.Crm.Application.Controls.DataSetControl::_appGrid
0x52924  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Grid.DataGrid::get_Parameters()
0x52929  ldstr    aGridtype// "GridType"
0x5292e  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x52933  ldstr    aAssociatedgrid// "AssociatedGrid"
0x52938  call     bool [mscorlib]System.String::op_Equality(string, string)
0x5293d  pop
0x5293e  ldloc.s  8
0x52940  brfalse.s loc_529AA
0x52942  ldarg.0
0x52943  ldfld    class Microsoft.Crm.Application.Controls.AppGrid Microsoft.Crm.Application.Controls.DataSetControl::_appGrid
0x52948  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Grid.DataGrid::get_Parameters()
0x5294d  ldstr    aCustomcontrolx// "customControlXmlParam"
0x52952  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x52957  stloc.s  7
0x52959  ldloc.s  7
0x5295b  brfalse  loc_52AC3
0x52960  ldloc.s  7
0x52962  ldsfld   string [mscorlib]System.String::Empty
0x52967  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x5296c  brfalse  loc_52AC3
0x52971  ldloc.s  7
0x52973  call     class [System.Xml]System.Xml.XmlDocument [Microsoft.Crm.Core]Microsoft.Crm.SharedUtil::CreateXmlDocument(string)
0x52978  stloc.s  9
0x5297a  ldarg.0
0x5297b  ldloc.s  9
0x5297d  ldstr    aCustomcontrol// "/customControl"
0x52982  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x52987  stfld    class [System.Xml]System.Xml.XmlNode Microsoft.Crm.Application.Controls.DataSetControl::_customControlNode
0x5298c  ldarg.0
0x5298d  ldfld    class [System.Xml]System.Xml.XmlNode Microsoft.Crm.Application.Controls.DataSetControl::_customControlNode
0x52992  brfalse  loc_52AC3
0x52997  ldarg.0
0x52998  ldarg.0
0x52999  ldfld    class [System.Xml]System.Xml.XmlNode Microsoft.Crm.Application.Controls.DataSetControl::_customControlNode
0x5299e  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Application.Controls.DataSetControl::GetCustomControlIdFromControlNode(class [System.Xml]System.Xml.XmlNode _customControlNode)
0x529a3  stloc.s  6
0x529a5  br       loc_52AC3
0x529aa  ldloc.s  4
0x529ac  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x529b1  ldarg.0
0x529b2  ldflda   class [System.Xml]System.Xml.XmlNode Microsoft.Crm.Application.Controls.DataSetControl::_customControlNode
0x529b7  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.DataSetControlUtility::GetCustomControlId(int32, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext, class [System.Xml]System.Xml.XmlNode&)
0x529bc  stloc.s  6
0x529be  ldloc.s  4
0x529c0  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x529c5  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.DataSetControlUtility::GetCustomControlClassicType(int32, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x529ca  stloc.s  0xA
0x529cc  ldarg.0
0x529cd  ldfld    class [System.Xml]System.Xml.XmlNode Microsoft.Crm.Application.Controls.DataSetControl::_customControlNode
0x529d2  brfalse  loc_52AC3
0x529d7  call     class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl [Microsoft.Crm.Core]Microsoft.Crm.FeatureControl::get_Current()
0x529dc  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl::get_Features()
0x529e1  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer::get_CustomControlSolutionExport()
0x529e6  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x529eb  call     bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.FeatureEnabledHelper::IsFeatureEnabled(class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x529f0  brfalse  loc_52A9B
0x529f5  ldloc.s  0xA
0x529f7  ldstr    aDisable// "disable"
0x529fc  call     bool [mscorlib]System.String::op_Equality(string, string)
0x52a01  brfalse  loc_52A9B
0x52a06  ldloc.s  6
0x52a08  ldsfld   valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.FormControlClassId::GridControl
0x52a0d  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x52a12  brfalse  loc_52A9B
0x52a17  ldsfld   valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.FormControlClassId::GridControl
0x52a1c  stloc.s  6
0x52a1e  ldarg.0
0x52a1f  ldfld    class [System.Xml]System.Xml.XmlNode Microsoft.Crm.Application.Controls.DataSetControl::_customControlNode
0x52a24  ldstr    aParameters// "parameters"
0x52a29  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x52a2e  callvirt instance void [System.Xml]System.Xml.XmlNode::RemoveAll()
0x52a33  ldarg.0
0x52a34  ldfld    class [System.Xml]System.Xml.XmlNode Microsoft.Crm.Application.Controls.DataSetControl::_customControlNode
0x52a39  callvirt instance class [System.Xml]System.Xml.XmlDocument [System.Xml]System.Xml.XmlNode::get_OwnerDocument()
0x52a3e  ldstr    aId_1// "id"
0x52a43  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlDocument::CreateAttribute(string)
0x52a48  stloc.s  0xB
0x52a4a  ldloc.s  0xB
0x52a4c  ldloca.s 6
0x52a4e  constrained. [mscorlib]System.Guid
0x52a54  callvirt instance string [mscorlib]System.Object::ToString()
0x52a59  callvirt instance void [System.Xml]System.Xml.XmlNode::set_Value(string)
0x52a5e  ldarg.0
0x52a5f  ldfld    class [System.Xml]System.Xml.XmlNode Microsoft.Crm.Application.Controls.DataSetControl::_customControlNode
0x52a64  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x52a69  ldloc.s  0xB
0x52a6b  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::Append(class [System.Xml]System.Xml.XmlAttribute)
0x52a70  pop
0x52a71  ldarg.0
0x52a72  ldfld    class [System.Xml]System.Xml.XmlNode Microsoft.Crm.Application.Controls.DataSetControl::_customControlNode
0x52a77  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x52a7c  ldstr    aName// "name"
0x52a81  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x52a86  stloc.s  0xC
0x52a88  ldarg.0
0x52a89  ldfld    class [System.Xml]System.Xml.XmlNode Microsoft.Crm.Application.Controls.DataSetControl::_customControlNode
0x52a8e  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x52a93  ldloc.s  0xC
0x52a95  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::Remove(class [System.Xml]System.Xml.XmlAttribute)
0x52a9a  pop
0x52a9b  ldarg.0
0x52a9c  ldfld    class [System.Xml]System.Xml.XmlNode Microsoft.Crm.Application.Controls.DataSetControl::_customControlNode
0x52aa1  callvirt instance string [System.Xml]System.Xml.XmlNode::get_OuterXml()
0x52aa6  stloc.s  7
0x52aa8  ldarg.0
0x52aa9  ldfld    class Microsoft.Crm.Application.Controls.AppGrid Microsoft.Crm.Application.Controls.DataSetControl::_appGrid
0x52aae  ldstr    aCustomcontrolx// "customControlXmlParam"
0x52ab3  ldarg.0
0x52ab4  ldfld    class [System.Xml]System.Xml.XmlNode Microsoft.Crm.Application.Controls.DataSetControl::_customControlNode
0x52ab9  callvirt instance string [System.Xml]System.Xml.XmlNode::get_OuterXml()
0x52abe  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Grid.DataGrid::AddParameter(string, string)
0x52ac3  ldarg.0
0x52ac4  ldfld    class [System.Xml]System.Xml.XmlNode Microsoft.Crm.Application.Controls.DataSetControl::_customControlNode
0x52ac9  brfalse.s loc_52AFC
0x52acb  ldarg.0
0x52acc  ldfld    class [System.Xml]System.Xml.XmlNode Microsoft.Crm.Application.Controls.DataSetControl::_customControlNode
0x52ad1  ldstr    aCustomcontrolP// "/customControl/parameters/msinternal.is"...
0x52ad6  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x52adb  stloc.s  0xD
0x52add  ldloc.s  0xD
0x52adf  brfalse.s loc_52AFC
0x52ae1  ldloc.s  0xD
0x52ae3  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x52ae8  ldloca.s 0xE
0x52aea  call     bool [mscorlib]System.Boolean::TryParse(string, bool&)
0x52aef  pop
0x52af0  ldloc.s  0xE
0x52af2  brfalse.s loc_52AFC
0x52af4  ldloc.s  5
0x52af6  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.MetricsStopwatch::Stop()
0x52afb  ret
0x52afc  ldloc.s  6
0x52afe  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x52b03  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x52b08  brfalse  loc_52E49
0x52b0d  ldloc.s  6
0x52b0f  ldsfld   valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.FormControlClassId::GridControl
0x52b14  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x52b19  brfalse  loc_52E07
0x52b1e  ldloc.s  6
0x52b20  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x52b25  call     class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.DataSetControlUtility::GetCustomControlResourceList(valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x52b2a  stloc.s  0xF
0x52b2c  ldloc.s  0xF
0x52b2e  ldstr    aScripts// "scripts"
0x52b33  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::ContainsKey(var<u1>)
0x52b38  brfalse.s loc_52B64
0x52b3a  ldloc.s  0xF
0x52b3c  ldstr    aStyles// "styles"
0x52b41  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::ContainsKey(var<u1>)
0x52b46  brfalse.s loc_52B64
0x52b48  ldloc.s  0xF
0x52b4a  ldstr    aConstructor// "constructor"
0x52b4f  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::ContainsKey(var<u1>)
0x52b54  brfalse.s loc_52B64
0x52b56  ldloc.s  0xF
0x52b58  ldstr    aManifest// "manifest"
0x52b5d  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::ContainsKey(var<u1>)
0x52b62  brtrue.s loc_52B6C
0x52b64  ldloc.s  5
0x52b66  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.MetricsStopwatch::Stop()
0x52b6b  ret
0x52b6c  ldarg.0
0x52b6d  ldloc.s  0xF
0x52b6f  ldstr    aConstructor// "constructor"
0x52b74  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::get_Item(void)
0x52b79  castclass [mscorlib]System.String
0x52b7e  stfld    string Microsoft.Crm.Application.Controls.DataSetControl::_typeName
0x52b83  ldarg.0
0x52b84  ldfld    string Microsoft.Crm.Application.Controls.DataSetControl::_typeName
0x52b89  ldsfld   string Microsoft.Crm.Application.Controls.DataSetControl::_editableGridControlName
0x52b8e  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x52b93  brfalse.s loc_52BD3
0x52b95  ldarg.0
0x52b96  ldfld    class Microsoft.Crm.Application.Controls.AppGrid Microsoft.Crm.Application.Controls.DataSetControl::_appGrid
0x52b9b  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x52ba0  ldstr    aStaticCommonSc_8// "/_static/_common/scripts/react.js"
0x52ba5  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x52baa  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x52baf  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri)
0x52bb4  ldarg.0
0x52bb5  ldfld    class Microsoft.Crm.Application.Controls.AppGrid Microsoft.Crm.Application.Controls.DataSetControl::_appGrid
0x52bba  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x52bbf  ldstr    aStaticCommonSc_9// "/_static/_common/scripts/CustomControls"...
0x52bc4  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x52bc9  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x52bce  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri)
0x52bd3  ldloc.s  0xF
0x52bd5  ldstr    aManifest// "manifest"
0x52bda  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::get_Item(void)
0x52bdf  castclass [Microsoft.Crm.ObjectModel]Microsoft.Crm.CustomControl.CustomControlDefinition
  ... truncated ...
```
