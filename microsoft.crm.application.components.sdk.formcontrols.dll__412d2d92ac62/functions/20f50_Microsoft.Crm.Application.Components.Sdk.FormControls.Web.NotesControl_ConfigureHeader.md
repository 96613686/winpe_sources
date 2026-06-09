# Microsoft.Crm.Application.Components.Sdk.FormControls.Web.NotesControl::ConfigureHeader

- ea: `0x20f50`
- end: `0x21240`
- name: `Microsoft.Crm.Application.Components.Sdk.FormControls.Web.NotesControl::ConfigureHeader`
- size: `752`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x20f50`
- `0x21240`
- `0x216a0`
- `0x216c0`
- `0x216e0`

## string_xrefs

- `0x20f74`: `/_static/_common/scripts/SalesCommonImported.js`
- `0x20f84`: `/_static/_common/scripts/CrmInternalUtility.js`
- `0x20f94`: `/_static/_common/scripts/SalesCommonFramework.js`
- `0x20fa4`: `/_static/_common/scripts/SalesCrmSoapProxyService.js`
- `0x20fb4`: `/_static/_common/scripts/Wall.Interfaces.js`
- `0x20fc4`: `/_static/_common/scripts/Wall.Control.js`
- `0x2105a`: `masterComponentId`
- `0x210b0`: `isControlReadOnly`
- `0x20fd4`: `/_static/_common/scripts/jqueryplugins.js`
- `0x2106a`: `/_controls/notes/notesv2template.aspx`
- `0x210c6`: `isNoteReadEnabled`
- `0x210e7`: `isNoteCreateEnabled`
- `0x2113f`: `isNoteDeleteEnabled`
- `0x2121b`: `_notesV2DownloadToken`

## pseudocode

```c

```

## disassembly

```asm
0x20f50  ldarg.0
0x20f51  call     instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::ConfigureHeader()
0x20f56  ldarg.0
0x20f57  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x20f5c  ldc.i4.1
0x20f5d  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::set_LoadJQuery(bool)
0x20f62  ldarg.0
0x20f63  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x20f68  ldc.i4.1
0x20f69  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::set_LoadJQueryTemplate(bool)
0x20f6e  ldarg.0
0x20f6f  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x20f74  ldstr    aStaticCommonSc_0// "/_static/_common/scripts/SalesCommonImp"...
0x20f79  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x20f7e  ldarg.0
0x20f7f  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x20f84  ldstr    aStaticCommonSc_1// "/_static/_common/scripts/CrmInternalUti"...
0x20f89  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x20f8e  ldarg.0
0x20f8f  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x20f94  ldstr    aStaticCommonSc_2// "/_static/_common/scripts/SalesCommonFra"...
0x20f99  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x20f9e  ldarg.0
0x20f9f  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x20fa4  ldstr    aStaticCommonSc_3// "/_static/_common/scripts/SalesCrmSoapPr"...
0x20fa9  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x20fae  ldarg.0
0x20faf  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x20fb4  ldstr    aStaticCommonSc_4// "/_static/_common/scripts/Wall.Interface"...
0x20fb9  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x20fbe  ldarg.0
0x20fbf  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x20fc4  ldstr    aStaticCommonSc_5// "/_static/_common/scripts/Wall.Control.j"...
0x20fc9  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x20fce  ldarg.0
0x20fcf  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x20fd4  ldstr    aStaticCommonSc_11// "/_static/_common/scripts/jqueryplugins."...
0x20fd9  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x20fde  ldarg.0
0x20fdf  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x20fe4  ldstr    aControlsTabsTa// "/_controls/tabs/tabs.css.aspx"
0x20fe9  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0x20fee  ldarg.0
0x20fef  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x20ff4  ldstr    aStaticFormsTab// "/_static/_forms/Tabs.js"
0x20ff9  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x20ffe  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentUICulture()
0x21003  callvirt instance int32 [mscorlib]System.Globalization.CultureInfo::get_LCID()
0x21008  stloc.s  6
0x2100a  ldloca.s 6
0x2100c  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x21011  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x21016  stloc.0
0x21017  ldarg.0
0x21018  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x2101d  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x21022  ldstr    aStaticCss0Note// "/_static/css/{0}/notesv2.css.aspx"
0x21027  ldc.i4.1
0x21028  newarr   [mscorlib]System.Object
0x2102d  dup
0x2102e  ldc.i4.0
0x2102f  ldloc.0
0x21030  stelem.ref
0x21031  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x21036  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0x2103b  ldarg.0
0x2103c  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x21041  ldstr    aStaticFormsNot// "/_static/_forms/Notesv2.js"
0x21046  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x2104b  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::.ctor()
0x21050  stloc.1
0x21051  ldarg.0
0x21052  call     instance string Microsoft.Crm.Application.Components.Sdk.FormControls.Web.NotesControl::get_MasterComponentId()
0x21057  brfalse.s loc_2106A
0x21059  ldloc.1
0x2105a  ldstr    aMastercomponen// "masterComponentId"
0x2105f  ldarg.0
0x21060  call     instance string Microsoft.Crm.Application.Components.Sdk.FormControls.Web.NotesControl::get_MasterComponentId()
0x21065  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x2106a  ldstr    aControlsNotesN// "/_controls/notes/notesv2template.aspx"
0x2106f  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x21074  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::CreateWebResourceUri(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x21079  dup
0x2107a  ldc.i4.1
0x2107b  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::set_UseVersionStamp(bool)
0x21080  dup
0x21081  callvirt instance class [System]System.Collections.Generic.SortedDictionary`2<string, string> [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::get_Query()
0x21086  ldstr    aLcid// "lcid"
0x2108b  ldloc.0
0x2108c  callvirt instance void class [System]System.Collections.Generic.SortedDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x21091  callvirt instance string [mscorlib]System.Object::ToString()
0x21096  stloc.2
0x21097  ldloc.1
0x21098  ldstr    aWallcontentpag// "wallContentPageUrl"
0x2109d  ldloc.2
0x2109e  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x210a3  ldc.i4.5
0x210a4  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x210a9  newobj   instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::.ctor(int32, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x210ae  stloc.3
0x210af  ldloc.1
0x210b0  ldstr    aIscontrolreado// "isControlReadOnly"
0x210b5  ldarg.0
0x210b6  call     instance bool Microsoft.Crm.Application.Components.Sdk.FormControls.Web.NotesControl::get_IsControlReadOnly()
0x210bb  box      [mscorlib]System.Boolean
0x210c0  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x210c5  ldloc.1
0x210c6  ldstr    aIsnotereadenab// "isNoteReadEnabled"
0x210cb  ldloc.3
0x210cc  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::get_LogicalName()
0x210d1  ldc.i4.1
0x210d2  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x210d7  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::HasPrivilege(string, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.PrivilegeType, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x210dc  box      [mscorlib]System.Boolean
0x210e1  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x210e6  ldloc.1
0x210e7  ldstr    aIsnotecreateen// "isNoteCreateEnabled"
0x210ec  ldloc.3
0x210ed  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::get_LogicalName()
0x210f2  ldc.i4.0
0x210f3  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x210f8  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::HasPrivilege(string, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.PrivilegeType, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x210fd  brfalse.s loc_21112
0x210ff  ldarg.0
0x21100  call     instance string Microsoft.Crm.Application.Components.Sdk.FormControls.Web.NotesControl::get_ParentLogicalName()
0x21105  ldc.i4.7
0x21106  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x2110b  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::HasPrivilege(string, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.PrivilegeType, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x21110  br.s     loc_21113
0x21112  ldc.i4.0
0x21113  box      [mscorlib]System.Boolean
0x21118  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x2111d  ldloc.1
0x2111e  ldstr    aIsnoteeditenab// "isNoteEditEnabled"
0x21123  ldloc.3
0x21124  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::get_LogicalName()
0x21129  ldc.i4.2
0x2112a  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x2112f  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::HasPrivilege(string, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.PrivilegeType, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x21134  box      [mscorlib]System.Boolean
0x21139  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x2113e  ldloc.1
0x2113f  ldstr    aIsnotedeleteen// "isNoteDeleteEnabled"
0x21144  ldloc.3
0x21145  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::get_LogicalName()
0x2114a  ldc.i4.3
0x2114b  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x21150  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::HasPrivilege(string, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.PrivilegeType, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x21155  box      [mscorlib]System.Boolean
0x2115a  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x2115f  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::.ctor()
0x21164  stloc.s  4
0x21166  ldloc.s  4
0x21168  ldstr    aEventmanager// "eventManager"
0x2116d  ldstr    aPageCrmeventma// "__Page_crmEventManager"
0x21172  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x21177  ldarg.0
0x21178  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x2117d  ldstr    aMscrmForminput_2// "Mscrm.FormInputControl.NotesV2.NotesCon"...
0x21182  ldloc.1
0x21183  ldnull
0x21184  ldloc.s  4
0x21186  ldarg.0
0x21187  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x2118c  ldstr    aContainer// "_container"
0x21191  call     string [mscorlib]System.String::Concat(string, string)
0x21196  ldc.i4.1
0x21197  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::CreateClientAjaxComponent(string, class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>, class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>, class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>, string, bool)
0x2119c  ldarg.0
0x2119d  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x211a2  ldstr    aNotesv2strings// "_notesV2Strings"
0x211a7  ldarg.0
0x211a8  call     instance string Microsoft.Crm.Application.Components.Sdk.FormControls.Web.NotesControl::GenerateClientStrings()
0x211ad  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0x211b2  ldstr    aActivitiesAtta// "/Activities/Attachment/download.aspx"
0x211b7  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x211bc  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x211c1  stloc.s  5
0x211c3  ldloc.s  5
0x211c5  callvirt instance class [System]System.Collections.Generic.SortedDictionary`2<string, string> [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::get_Query()
0x211ca  ldstr    aAttachmenttype// "AttachmentType"
0x211cf  ldc.i4.5
0x211d0  stloc.s  6
0x211d2  ldloca.s 6
0x211d4  ldstr    aD// "D"
0x211d9  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x211de  call     instance string [mscorlib]System.Int32::ToString(string, class [mscorlib]System.IFormatProvider)
0x211e3  callvirt instance void class [System]System.Collections.Generic.SortedDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x211e8  ldloc.s  5
0x211ea  callvirt instance class [System]System.Collections.Generic.SortedDictionary`2<string, string> [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::get_Query()
0x211ef  ldstr    aIsnotestabatta// "IsNotesTabAttachment"
0x211f4  ldstr    a1_0// "1"
0x211f9  callvirt instance void class [System]System.Collections.Generic.SortedDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x211fe  ldarg.0
0x211ff  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x21204  ldstr    aNotesv2downloa// "_notesV2DownloadUrl"
0x21209  ldloc.s  5
0x2120b  callvirt instance string [mscorlib]System.Object::ToString()
0x21210  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0x21215  ldarg.0
0x21216  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x2121b  ldstr    aNotesv2downloa_0// "_notesV2DownloadToken"
0x21220  ldarg.0
0x21221  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Security.WrpcContext [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppControl::get_CurrentWrpcContext()
0x21226  ldstr    aActivitiesAtta// "/Activities/Attachment/download.aspx"
0x2122b  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x21230  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x21235  callvirt instance string [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Security.WrpcContext::GetWrpcTokenAsQueryString(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri)
0x2123a  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0x2123f  ret
```
