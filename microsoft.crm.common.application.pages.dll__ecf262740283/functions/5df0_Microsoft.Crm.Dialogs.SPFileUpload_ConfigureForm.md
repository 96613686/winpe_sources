# Microsoft.Crm.Dialogs.SPFileUpload::ConfigureForm

- ea: `0x5df0`
- end: `0x60b3`
- name: `Microsoft.Crm.Dialogs.SPFileUpload::ConfigureForm`
- size: `707`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x5df0`

## string_xrefs

- `0x5e7c`: `servicetype`
- `0x5fb0`: `servicetype`

## pseudocode

```c

```

## disassembly

```asm
0x5df0  ldarg.0
0x5df1  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::ConfigureForm()
0x5df6  ldarg.0
0x5df7  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::crmForm
0x5dfc  isinst   [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.HardCodedForm
0x5e01  stloc.0
0x5e02  ldarg.0
0x5e03  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.Localization.Text Microsoft.Crm.Dialogs.SPFileUpload::dialogTitle
0x5e08  ldstr    aWebGridCmdsDlg_18// "Web._grid.cmds.dlg_sp_upload_title"
0x5e0d  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.Localization.Text::set_ResourceId(string)
0x5e12  ldarg.0
0x5e13  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::crmForm
0x5e18  ldstr    aColumnsetColum// "<columnset><column>filesize</column><co"...
0x5e1d  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm::set_ColumnSetXml(string)
0x5e22  ldarg.0
0x5e23  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::crmForm
0x5e28  ldarg.0
0x5e29  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.EntityPage::get_CurrentEntity()
0x5e2e  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm::Execute(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity)
0x5e33  ldarg.0
0x5e34  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::crmForm
0x5e39  callvirt instance valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.FormState [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm::get_State()
0x5e3e  ldc.i4.1
0x5e3f  bne.un.s loc_5E63
0x5e41  ldarg.0
0x5e42  ldfld    class [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.HiddenInputControl Microsoft.Crm.Dialogs.SPFileUpload::objectid
0x5e47  ldloc.0
0x5e48  callvirt instance string [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.EndUserForm::get_ParentId()
0x5e4d  callvirt instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormDataControlUIWrapper::set_Value(object)
0x5e52  ldarg.0
0x5e53  ldfld    class [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.HiddenInputControl Microsoft.Crm.Dialogs.SPFileUpload::objecttypecode
0x5e58  ldloc.0
0x5e59  callvirt instance string [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.EndUserForm::get_ParentType()
0x5e5e  callvirt instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormDataControlUIWrapper::set_Value(object)
0x5e63  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x5e68  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x5e6d  ldc.i4   0x2524
0x5e72  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(int32)
0x5e77  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IAttributeMetadataCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_AttributesByName()
0x5e7c  ldstr    aServicetype// "servicetype"
0x5e81  callvirt instance bool [mscorlib]System.Collections.IDictionary::Contains(object)
0x5e86  brfalse.s loc_5E94
0x5e88  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x5e8d  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::IsOneDriveIntegrationEnabled(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x5e92  br.s     loc_5E95
0x5e94  ldc.i4.0
0x5e95  stloc.1
0x5e96  ldarg.0
0x5e97  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x5e9c  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x5ea1  ldstr    aPid// "pId"
0x5ea6  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x5eab  ldloca.s 2
0x5ead  call     bool [mscorlib]System.Guid::TryParse(string, valuetype [mscorlib]System.Guid&)
0x5eb2  pop
0x5eb3  ldarg.0
0x5eb4  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x5eb9  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x5ebe  ldstr    aPtype// "pType"
0x5ec3  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x5ec8  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x5ecd  call     int32 [mscorlib]System.Int32::Parse(string, class [mscorlib]System.IFormatProvider)
0x5ed2  stloc.3
0x5ed3  ldloc.2
0x5ed4  ldloc.3
0x5ed5  ldloc.1
0x5ed6  ldc.i4.0
0x5ed7  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ApplicationEntityCollection [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::RetrieveSharePointDocLocation(valuetype [mscorlib]System.Guid, int32, bool, bool)
0x5edc  stloc.s  4
0x5ede  ldc.i4.0
0x5edf  stloc.s  5
0x5ee1  ldstr    asc_1F1DE// ""
0x5ee6  stloc.s  6
0x5ee8  ldarg.0
0x5ee9  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x5eee  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x5ef3  ldstr    aLocationid_0// "locationId"
0x5ef8  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x5efd  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x5f02  brtrue.s loc_5F45
0x5f04  ldarg.0
0x5f05  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x5f0a  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x5f0f  ldstr    aLocationid_0// "locationId"
0x5f14  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x5f19  callvirt instance string [mscorlib]System.String::ToLower()
0x5f1e  callvirt instance string [mscorlib]System.Object::ToString()
0x5f23  ldstr    asc_23884// "{"
0x5f28  ldstr    asc_1F1DE// ""
0x5f2d  callvirt instance string [mscorlib]System.String::Replace(string, string)
0x5f32  ldstr    asc_23888// "}"
0x5f37  ldstr    asc_1F1DE// ""
0x5f3c  callvirt instance string [mscorlib]System.String::Replace(string, string)
0x5f41  stloc.s  6
0x5f43  br.s     loc_5F68
0x5f45  ldloc.s  4
0x5f47  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity>::get_Count()
0x5f4c  ldc.i4.0
0x5f4d  ble.s    loc_5F68
0x5f4f  ldloc.s  4
0x5f51  ldc.i4.0
0x5f52  callvirt instance var<u1> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity>::get_Item(!!T0)
0x5f57  ldstr    aSharepointdocu// "sharepointdocumentlocationid"
0x5f5c  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x5f61  callvirt instance string [mscorlib]System.Object::ToString()
0x5f66  stloc.s  6
0x5f68  ldarg.0
0x5f69  ldfld    class [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.PicklistControl Microsoft.Crm.Dialogs.SPFileUpload::documentLocations
0x5f6e  ldarg.0
0x5f6f  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x5f74  ldstr    aOdbNewuploadDl// "Odb_NewUpload_Dlg_LocationDropdown_Defa"...
0x5f79  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x5f7e  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x5f83  stloc.s  7
0x5f85  ldloca.s 7
0x5f87  constrained. [mscorlib]System.Guid
0x5f8d  callvirt instance string [mscorlib]System.Object::ToString()
0x5f92  callvirt instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.PicklistControl::AddItem(string, string)
0x5f97  ldloc.s  4
0x5f99  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity>::GetEnumerator()
0x5f9e  stloc.s  8
0x5fa0  br.s     loc_6005
0x5fa2  ldloc.s  8
0x5fa4  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity>::get_Current()
0x5fa9  stloc.s  9
0x5fab  ldloc.1
0x5fac  brfalse.s loc_5FD8
0x5fae  ldloc.s  9
0x5fb0  ldstr    aServicetype// "servicetype"
0x5fb5  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x5fba  callvirt instance string [mscorlib]System.Object::ToString()
0x5fbf  ldc.i4.1
0x5fc0  stloc.s  0xA
0x5fc2  ldloca.s 0xA
0x5fc4  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x5fc9  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x5fce  call     bool [mscorlib]System.String::op_Equality(string, string)
0x5fd3  brfalse.s loc_5FD8
0x5fd5  ldc.i4.1
0x5fd6  stloc.s  5
0x5fd8  ldarg.0
0x5fd9  ldfld    class [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.PicklistControl Microsoft.Crm.Dialogs.SPFileUpload::documentLocations
0x5fde  ldloc.s  9
0x5fe0  ldstr    aName// "name"
0x5fe5  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x5fea  callvirt instance string [mscorlib]System.Object::ToString()
0x5fef  ldloc.s  9
0x5ff1  ldstr    aSharepointdocu// "sharepointdocumentlocationid"
0x5ff6  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x5ffb  callvirt instance string [mscorlib]System.Object::ToString()
0x6000  callvirt instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.PicklistControl::AddItem(string, string)
0x6005  ldloc.s  8
0x6007  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x600c  brtrue.s loc_5FA2
0x600e  leave.s  loc_601C
0x6010  ldloc.s  8
0x6012  brfalse.s loc_601B
0x6014  ldloc.s  8
0x6016  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x601b  endfinally
0x601c  ldloc.s  5
0x601e  ldc.i4.0
0x601f  ceq
0x6021  ldloc.1
0x6022  and
0x6023  brfalse.s loc_6054
0x6025  ldarg.0
0x6026  ldfld    class [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.PicklistControl Microsoft.Crm.Dialogs.SPFileUpload::documentLocations
0x602b  ldarg.0
0x602c  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x6031  ldstr    aOdbOptionText// "Odb_Option_Text"
0x6036  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x603b  call     valuetype [mscorlib]System.Guid [Microsoft.Crm]Microsoft.Crm.SharePointUtility::get_OneDriveLocationNotCreatedGuid()
0x6040  stloc.s  7
0x6042  ldloca.s 7
0x6044  constrained. [mscorlib]System.Guid
0x604a  callvirt instance string [mscorlib]System.Object::ToString()
0x604f  callvirt instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.PicklistControl::AddItem(string, string)
0x6054  ldloc.s  6
0x6056  call     bool [Microsoft.Crm]Microsoft.Crm.SharePointUtility::IsAllOrSharedLocation(string)
0x605b  brfalse.s loc_6073
0x605d  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x6062  stloc.s  7
0x6064  ldloca.s 7
0x6066  constrained. [mscorlib]System.Guid
0x606c  callvirt instance string [mscorlib]System.Object::ToString()
0x6071  stloc.s  6
0x6073  ldarg.0
0x6074  ldfld    class [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.PicklistControl Microsoft.Crm.Dialogs.SPFileUpload::documentLocations
0x6079  ldc.i4.1
0x607a  callvirt instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.PicklistControl::set_AllowStringValues(bool)
0x607f  ldloc.s  4
0x6081  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity>::get_Count()
0x6086  ldc.i4.1
0x6087  bne.un.s loc_60A5
0x6089  ldloc.1
0x608a  brtrue.s loc_60A5
0x608c  ldloc.s  4
0x608e  ldc.i4.0
0x608f  callvirt instance var<u1> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity>::get_Item(!!T0)
0x6094  ldstr    aSharepointdocu// "sharepointdocumentlocationid"
0x6099  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x609e  callvirt instance string [mscorlib]System.Object::ToString()
0x60a3  stloc.s  6
0x60a5  ldarg.0
0x60a6  ldfld    class [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.PicklistControl Microsoft.Crm.Dialogs.SPFileUpload::documentLocations
0x60ab  ldloc.s  6
0x60ad  callvirt instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormDataControlUIWrapper::set_Value(object)
0x60b2  ret
```
