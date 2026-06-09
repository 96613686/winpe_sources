# Microsoft.Crm.Web.Tools.SystemCustomization.Attributes.AttributeListPage::SetPageHeader

- ea: `0xb5860`
- end: `0xb5a49`
- name: `Microsoft.Crm.Web.Tools.SystemCustomization.Attributes.AttributeListPage::SetPageHeader`
- size: `489`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0xb57c0`

## callees

- `0xb5860`
- `0xb6030`
- `0xb6050`
- `0xb6070`
- `0xd6830`

## string_xrefs

- `0xb58bd`: `/_static/_common/scripts/RibbonActions.js`
- `0xb5903`: `AttributeUtil.Messages.CannotDeleteSystemAttribute`
- `0xb5930`: `AttributeUtil.Messages.ConfirmAttributeDelete`
- `0xb594e`: `AttributeUtil.Messages.ConfirmAttributeDeletePhonetic`
- `0xb5a05`: `attributexml`
- `0xb5a32`: `LOCID_ATTRUTL_CONFIRMDELLINKATTR`
- `0xb5a38`: `AttributeUtil.Messages.ConfirmLinkedAttributeDelete`

## pseudocode

```c

```

## disassembly

```asm
0xb5860  ldarg.0
0xb5861  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xb5866  ldc.i4.8
0xb5867  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetHeader(valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.ControlType)
0xb586c  ldarg.0
0xb586d  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xb5872  ldstr    aGridId// "GRID_ID"
0xb5877  ldarg.0
0xb5878  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppGrid Microsoft.Crm.Web.Tools.SystemCustomization.Attributes.AttributeListPage::gridAttributes
0xb587d  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0xb5882  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0xb5887  ldarg.0
0xb5888  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xb588d  ldstr    aStaticGridCmds// "/_static/_grid/cmds/util.js"
0xb5892  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xb5897  ldarg.0
0xb5898  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xb589d  ldstr    aStaticToolsSys_0// "/_static/tools/systemcustomization/scri"...
0xb58a2  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xb58a7  ldarg.0
0xb58a8  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xb58ad  ldstr    aStaticToolsSys_19// "/_static/tools/systemcustomization/attr"...
0xb58b2  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xb58b7  ldarg.0
0xb58b8  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xb58bd  ldstr    aStaticCommonSc_8// "/_static/_common/scripts/RibbonActions."...
0xb58c2  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xb58c7  ldarg.0
0xb58c8  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xb58cd  ldstr    aStaticToolsDep// "/_static/tools/dependency/scripts/depen"...
0xb58d2  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xb58d7  ldarg.0
0xb58d8  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xb58dd  ldstr    aStaticToolsSol// "/_static/tools/solution/scripts/Managed"...
0xb58e2  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xb58e7  ldarg.0
0xb58e8  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xb58ed  ldstr    aStaticControls_18// "/_static/_controls/TreeNav/treenavcontr"...
0xb58f2  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xb58f7  ldarg.0
0xb58f8  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xb58fd  ldstr    aLocidAttrutlCa// "LOCID_ATTRUTL_CANTDELSYSATTR"
0xb5902  ldarg.0
0xb5903  ldstr    aAttributeutilM// "AttributeUtil.Messages.CannotDeleteSyst"...
0xb5908  call     instance string Microsoft.Crm.Web.Tools.SystemCustomization.Attributes.AttributeListPage::GetSCString(string name)
0xb590d  ldc.i4.0
0xb590e  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xb5913  ldstr    aPhoneticbaseds// "PhoneticBasedSearch"
0xb5918  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xb591d  call     bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.FeatureEnabledHelper::IsFeatureEnabled(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xb5922  brtrue.s loc_B5942
0xb5924  ldarg.0
0xb5925  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xb592a  ldstr    aLocidAttrutlCo// "LOCID_ATTRUTL_CONFIRMDELATTR"
0xb592f  ldarg.0
0xb5930  ldstr    aAttributeutilM_0// "AttributeUtil.Messages.ConfirmAttribute"...
0xb5935  call     instance string Microsoft.Crm.Web.Tools.SystemCustomization.Attributes.AttributeListPage::GetSCString(string name)
0xb593a  ldc.i4.0
0xb593b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xb5940  br.s     loc_B595E
0xb5942  ldarg.0
0xb5943  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xb5948  ldstr    aLocidAttrutlCo// "LOCID_ATTRUTL_CONFIRMDELATTR"
0xb594d  ldarg.0
0xb594e  ldstr    aAttributeutilM_1// "AttributeUtil.Messages.ConfirmAttribute"...
0xb5953  call     instance string Microsoft.Crm.Web.Tools.SystemCustomization.Attributes.AttributeListPage::GetSCString(string name)
0xb5958  ldc.i4.0
0xb5959  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xb595e  ldarg.0
0xb595f  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xb5964  ldstr    aLocidAttrutlCr// "LOCID_ATTRUTL_CREATINGATTR"
0xb5969  ldarg.0
0xb596a  ldstr    aAttributeutilM_2// "AttributeUtil.Messages.CreatingAttribut"...
0xb596f  call     instance string Microsoft.Crm.Web.Tools.SystemCustomization.Attributes.AttributeListPage::GetSCString(string name)
0xb5974  ldc.i4.0
0xb5975  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xb597a  ldarg.0
0xb597b  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xb5980  ldstr    aLocidAttrutlDe// "LOCID_ATTRUTL_DELETINGATTR"
0xb5985  ldarg.0
0xb5986  ldstr    aAttributeutilM_3// "AttributeUtil.Messages.DeletingAttribut"...
0xb598b  call     instance string Microsoft.Crm.Web.Tools.SystemCustomization.Attributes.AttributeListPage::GetSCString(string name)
0xb5990  ldc.i4.0
0xb5991  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xb5996  ldarg.0
0xb5997  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xb599c  ldstr    aLocidAttrutlUp// "LOCID_ATTRUTL_UPDATINGATTR"
0xb59a1  ldarg.0
0xb59a2  ldstr    aAttributeutilM_4// "AttributeUtil.Messages.UpdatingAttribut"...
0xb59a7  call     instance string Microsoft.Crm.Web.Tools.SystemCustomization.Attributes.AttributeListPage::GetSCString(string name)
0xb59ac  ldc.i4.0
0xb59ad  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xb59b2  ldarg.0
0xb59b3  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xb59b8  ldstr    aStaticToolsSys_30// "/_static/tools/systemcustomization/attr"...
0xb59bd  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xb59c2  ldarg.0
0xb59c3  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xb59c8  ldstr    aLocidAttrlstMu// "LOCID_ATTRLST_MUSTSELECT"
0xb59cd  ldarg.0
0xb59ce  ldstr    aMessagesNosele_0// "Messages.NoSelectedAttribute"
0xb59d3  call     instance string Microsoft.Crm.Web.Tools.SystemCustomization.Attributes.AttributeListPage::GetString(string name)
0xb59d8  ldc.i4.0
0xb59d9  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xb59de  ldarg.0
0xb59df  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xb59e4  ldarg.0
0xb59e5  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xb59ea  ldc.i4.0
0xb59eb  call     void Microsoft.Crm.Application.Pages.tools.SystemCustomization.Common.SegmentationUtility::SetSegmentationHeaders(class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header currentHeader, class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager currentResourceManager, [opt] bool skipSubcomponentTypes)
0xb59f0  ldarg.0
0xb59f1  call     instance string Microsoft.Crm.Web.Tools.SystemCustomization.Attributes.AttributeListPage::GetLinkedAttributesList()
0xb59f6  stloc.0
0xb59f7  ldloc.0
0xb59f8  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xb59fd  brtrue.s loc_B5A48
0xb59ff  ldarg.0
0xb5a00  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xb5a05  ldstr    aAttributexml// "attributexml"
0xb5a0a  ldloc.0
0xb5a0b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0xb5a10  ldarg.0
0xb5a11  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xb5a16  ldstr    aRecurrenceenti// "recurrenceentityname"
0xb5a1b  ldarg.0
0xb5a1c  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata Microsoft.Crm.Web.Tools.SystemCustomization.Attributes.AttributeListPage::_recurrenceEntityMD
0xb5a21  ldc.i4.1
0xb5a22  call     string [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Utility.WebUtility::GetFmtObjName(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata, valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.NameFormatStyle)
0xb5a27  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0xb5a2c  ldarg.0
0xb5a2d  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xb5a32  ldstr    aLocidAttrutlCo_0// "LOCID_ATTRUTL_CONFIRMDELLINKATTR"
0xb5a37  ldarg.0
0xb5a38  ldstr    aAttributeutilM_5// "AttributeUtil.Messages.ConfirmLinkedAtt"...
0xb5a3d  call     instance string Microsoft.Crm.Web.Tools.SystemCustomization.Attributes.AttributeListPage::GetSCString(string name)
0xb5a42  ldc.i4.0
0xb5a43  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xb5a48  ret
```
