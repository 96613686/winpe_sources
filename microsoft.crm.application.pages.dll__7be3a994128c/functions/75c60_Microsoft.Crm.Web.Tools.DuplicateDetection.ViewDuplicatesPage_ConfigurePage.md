# Microsoft.Crm.Web.Tools.DuplicateDetection.ViewDuplicatesPage::ConfigurePage

- ea: `0x75c60`
- end: `0x76271`
- name: `Microsoft.Crm.Web.Tools.DuplicateDetection.ViewDuplicatesPage::ConfigurePage`
- size: `1553`
- prototype: ``
- caller_count: `0`
- callee_count: `15`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x75c60`
- `0x76280`
- `0x76410`
- `0x764f0`
- `0x76860`
- `0x768a0`
- `0x769a0`
- `0x769c0`
- `0x769e0`
- `0x769f0`
- `0x76a00`
- `0x76a10`
- `0x76a20`
- `0x76a30`
- `0x76bb0`

## string_xrefs

- `0x75e3a`: `dataxml`
- `0x75ef0`: `dataxml`
- `0x761c0`: `dataxml`
- `0x75e23`: `/_common/styles/duplicatedialogrefresh.css`
- `0x75de0`: `My_UpdatedRecord_ViewDuplicates_aspx`
- `0x75eb0`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x75f1c`: `entitydataxml`
- `0x760a2`: `Outlook_CreateInOnline_UserAction_ViewDuplicates_aspx`
- `0x760f0`: `accKeyCreateInOnline`

## pseudocode

```c

```

## disassembly

```asm
0x75c60  ldarg.0
0x75c61  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.DialogBase::ConfigurePage()
0x75c66  newobj   instance void Microsoft.Crm.Web.Tools.DuplicateDetection.ViewDuplicatesView::.ctor()
0x75c6b  stloc.0
0x75c6c  ldloc.0
0x75c6d  ldarg.0
0x75c6e  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x75c73  callvirt instance void Microsoft.Crm.Web.Tools.DuplicateDetection.IViewDuplicatesView::set_Request(class [System.Web]System.Web.HttpRequest value)
0x75c78  ldloc.0
0x75c79  ldarg.0
0x75c7a  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x75c7f  callvirt instance void Microsoft.Crm.Web.Tools.DuplicateDetection.IViewDuplicatesView::set_CurrentHeader(class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header value)
0x75c84  ldloc.0
0x75c85  ldarg.0
0x75c86  ldfld    valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util/DuplicatesSource Microsoft.Crm.Web.Tools.DuplicateDetection.ViewDuplicatesPage::duplicatesSource
0x75c8b  callvirt instance void Microsoft.Crm.Web.Tools.DuplicateDetection.IViewDuplicatesView::set_DuplicatesSource(valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util/DuplicatesSource value)
0x75c90  ldloc.0
0x75c91  ldarg.0
0x75c92  ldfld    int32 Microsoft.Crm.Web.Tools.DuplicateDetection.ViewDuplicatesPage::dialogType
0x75c97  callvirt instance void Microsoft.Crm.Web.Tools.DuplicateDetection.IViewDuplicatesView::set_DialogTypeProperty(int32 value)
0x75c9c  ldloc.0
0x75c9d  callvirt instance void Microsoft.Crm.Web.Tools.DuplicateDetection.IViewDuplicatesView::SetDuplicateSourceAndDialogType()
0x75ca2  ldarg.0
0x75ca3  ldloc.0
0x75ca4  callvirt instance valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util/DuplicatesSource Microsoft.Crm.Web.Tools.DuplicateDetection.IViewDuplicatesView::get_DuplicatesSource()
0x75ca9  stfld    valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util/DuplicatesSource Microsoft.Crm.Web.Tools.DuplicateDetection.ViewDuplicatesPage::duplicatesSource
0x75cae  ldarg.0
0x75caf  ldloc.0
0x75cb0  callvirt instance int32 Microsoft.Crm.Web.Tools.DuplicateDetection.IViewDuplicatesView::get_DialogTypeProperty()
0x75cb5  stfld    int32 Microsoft.Crm.Web.Tools.DuplicateDetection.ViewDuplicatesPage::dialogType
0x75cba  ldarg.0
0x75cbb  ldloc.0
0x75cbc  callvirt instance string Microsoft.Crm.Web.Tools.DuplicateDetection.IViewDuplicatesView::get_Source()
0x75cc1  stfld    string Microsoft.Crm.Web.Tools.DuplicateDetection.ViewDuplicatesPage::source
0x75cc6  ldarg.0
0x75cc7  ldfld    valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util/DuplicatesSource Microsoft.Crm.Web.Tools.DuplicateDetection.ViewDuplicatesPage::duplicatesSource
0x75ccc  ldc.i4.1
0x75ccd  bne.un.s loc_75D0C
0x75ccf  ldarg.0
0x75cd0  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x75cd5  callvirt instance class [mscorlib]System.IO.Stream [System.Web]System.Web.HttpRequest::get_InputStream()
0x75cda  callvirt instance int64 [mscorlib]System.IO.Stream::get_Length()
0x75cdf  ldc.i4.0
0x75ce0  conv.i8
0x75ce1  ble.s    loc_75D0C
0x75ce3  ldarg.0
0x75ce4  ldfld    int32 Microsoft.Crm.Web.Tools.DuplicateDetection.ViewDuplicatesPage::dialogType
0x75ce9  ldc.i4.3
0x75cea  bne.un.s loc_75CF3
0x75cec  ldarg.0
0x75ced  call     instance void Microsoft.Crm.Web.Tools.DuplicateDetection.ViewDuplicatesPage::ProcessOnlineCreateUpdate()
0x75cf2  ret
0x75cf3  ldarg.0
0x75cf4  ldfld    int32 Microsoft.Crm.Web.Tools.DuplicateDetection.ViewDuplicatesPage::dialogType
0x75cf9  ldc.i4.1
0x75cfa  beq.s    loc_75D05
0x75cfc  ldarg.0
0x75cfd  ldfld    int32 Microsoft.Crm.Web.Tools.DuplicateDetection.ViewDuplicatesPage::dialogType
0x75d02  ldc.i4.2
0x75d03  bne.un.s loc_75D0C
0x75d05  ldarg.0
0x75d06  call     instance void Microsoft.Crm.Web.Tools.DuplicateDetection.ViewDuplicatesPage::ReturnUserDecision()
0x75d0b  ret
0x75d0c  ldarg.0
0x75d0d  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x75d12  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::AddWrpcTokenActionPath()
0x75d17  ldarg.0
0x75d18  ldsfld   string [mscorlib]System.String::Empty
0x75d1d  stfld    string Microsoft.Crm.Web.Tools.DuplicateDetection.ViewDuplicatesPage::asyncJobId
0x75d22  ldarg.0
0x75d23  ldfld    valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util/DuplicatesSource Microsoft.Crm.Web.Tools.DuplicateDetection.ViewDuplicatesPage::duplicatesSource
0x75d28  stloc.1
0x75d29  ldloc.1
0x75d2a  ldc.i4.1
0x75d2b  sub
0x75d2c  switch   loc_75D4A, loc_761B4, loc_75E2E, loc_75E2E, loc_75E2E, loc_75E2E
0x75d49  ret
0x75d4a  ldarg.0
0x75d4b  ldarg.0
0x75d4c  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x75d51  ldstr    aViewduplicates_1// "ViewDuplicates_aspx_BaseRecordsIframe_O"...
0x75d56  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x75d5b  stfld    string Microsoft.Crm.Web.Tools.DuplicateDetection.ViewDuplicatesPage::baseRecordsFrameHeight
0x75d60  ldarg.0
0x75d61  ldarg.0
0x75d62  ldfld    int32 Microsoft.Crm.Web.Tools.DuplicateDetection.ViewDuplicatesPage::dialogType
0x75d67  ldc.i4.2
0x75d68  beq.s    loc_75D7C
0x75d6a  ldarg.0
0x75d6b  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x75d70  ldstr    aViewduplicates_2// "ViewDuplicates_aspx_DuplicatesListIfram"...
0x75d75  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x75d7a  br.s     loc_75D8C
0x75d7c  ldarg.0
0x75d7d  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x75d82  ldstr    aViewduplicates_3// "ViewDuplicates_aspx_DuplicatesListIfram"...
0x75d87  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x75d8c  stfld    string Microsoft.Crm.Web.Tools.DuplicateDetection.ViewDuplicatesPage::duplicatesListFrameHeight
0x75d91  ldarg.0
0x75d92  ldarg.0
0x75d93  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x75d98  ldstr    aViewduplicates_4// "ViewDuplicates_aspx_DuplicateRecordsIfr"...
0x75d9d  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x75da2  stfld    string Microsoft.Crm.Web.Tools.DuplicateDetection.ViewDuplicatesPage::duplicateRecordsFrameHeight
0x75da7  ldarg.0
0x75da8  ldarg.0
0x75da9  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x75dae  ldstr    aViewduplicates_5// "ViewDuplicates_aspx_MyRecordLabel_Onlin"...
0x75db3  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x75db8  stfld    string Microsoft.Crm.Web.Tools.DuplicateDetection.ViewDuplicatesPage::myRecordTextHeight
0x75dbd  ldarg.0
0x75dbe  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x75dc3  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x75dc8  ldstr    aOid// "oid"
0x75dcd  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x75dd2  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x75dd7  brtrue.s loc_75DF1
0x75dd9  ldarg.0
0x75dda  ldarg.0
0x75ddb  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x75de0  ldstr    aMyUpdatedrecor// "My_UpdatedRecord_ViewDuplicates_aspx"
0x75de5  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x75dea  stfld    string Microsoft.Crm.Web.Tools.DuplicateDetection.ViewDuplicatesPage::myRecordResourceString
0x75def  br.s     loc_75E1D
0x75df1  ldarg.0
0x75df2  ldarg.0
0x75df3  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x75df8  ldstr    aMyNewrecordVie// "My_NewRecord_ViewDuplicates_aspx"
0x75dfd  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x75e02  stfld    string Microsoft.Crm.Web.Tools.DuplicateDetection.ViewDuplicatesPage::myRecordResourceString
0x75e07  ldarg.0
0x75e08  ldarg.0
0x75e09  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x75e0e  ldstr    aNewrecordDialo// "NewRecord_Dialog_Description_ViewDuplic"...
0x75e13  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x75e18  stfld    string Microsoft.Crm.Web.Tools.DuplicateDetection.ViewDuplicatesPage::dialogDescription
0x75e1d  ldarg.0
0x75e1e  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x75e23  ldstr    aCommonStylesDu// "/_common/styles/duplicatedialogrefresh."...
0x75e28  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0x75e2d  ret
0x75e2e  ldarg.0
0x75e2f  ldarg.0
0x75e30  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x75e35  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_Form()
0x75e3a  ldstr    aDataxml// "dataxml"
0x75e3f  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x75e44  stfld    string Microsoft.Crm.Web.Tools.DuplicateDetection.ViewDuplicatesPage::formData
0x75e49  ldarg.0
0x75e4a  ldfld    valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util/DuplicatesSource Microsoft.Crm.Web.Tools.DuplicateDetection.ViewDuplicatesPage::duplicatesSource
0x75e4f  ldc.i4.3
0x75e50  bne.un   loc_75ED9
0x75e55  ldarg.0
0x75e56  ldfld    string Microsoft.Crm.Web.Tools.DuplicateDetection.ViewDuplicatesPage::formData
0x75e5b  call     string Microsoft.Crm.Web.Tools.DuplicateDetection.ViewDuplicatesHelper::GetEntityNameFromDataXml(string dataXml)
0x75e60  stloc.2
0x75e61  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::get_Current()
0x75e66  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.ISecurityPrincipal::get_OrganizationId()
0x75e6b  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::.ctor(valuetype [mscorlib]System.Guid)
0x75e70  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x75e75  ldloc.2
0x75e76  ldc.i4.1
0x75e77  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(string, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.NameMappingType)
0x75e7c  stloc.3
0x75e7d  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::get_Current()
0x75e82  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser::get_SystemUserId()
0x75e87  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::get_Current()
0x75e8c  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.ISecurityPrincipal::get_OrganizationId()
0x75e91  call     void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.SerializationState::OnBeginRequest(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x75e96  ldloc.3
0x75e97  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::get_Current()
0x75e9c  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.ISecurityPrincipal::get_OrganizationId()
0x75ea1  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.EntityClassFactory::CreateInstance(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata, valuetype [mscorlib]System.Guid)
0x75ea6  stloc.s  4
0x75ea8  ldloc.s  4
0x75eaa  ldarg.0
0x75eab  ldfld    string Microsoft.Crm.Web.Tools.DuplicateDetection.ViewDuplicatesPage::formData
0x75eb0  ldstr    aHttpSchemasMic_0// "http://schemas.microsoft.com/crm/2007/W"...
0x75eb5  ldsfld   string [mscorlib]System.String::Empty
0x75eba  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.SdkEntityDeserializationStrategy [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.EntitySerializationStrategyFactory::CreateEntityDeserializationStrategy(string, string)
0x75ebf  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::Deserialize(string, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IEntityDeserializationStrategy)
0x75ec4  ldarg.0
0x75ec5  ldloc.s  4
0x75ec7  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::Serialize()
0x75ecc  stfld    string Microsoft.Crm.Web.Tools.DuplicateDetection.ViewDuplicatesPage::formData
0x75ed1  leave.s  loc_75ED9
0x75ed3  call     void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.SerializationState::OnEndRequest()
0x75ed8  endfinally
0x75ed9  ldarg.0
0x75eda  ldfld    valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util/DuplicatesSource Microsoft.Crm.Web.Tools.DuplicateDetection.ViewDuplicatesPage::duplicatesSource
0x75edf  ldc.i4.5
0x75ee0  bne.un   loc_76000
0x75ee5  ldarg.0
0x75ee6  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x75eeb  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_Form()
0x75ef0  ldstr    aDataxml// "dataxml"
0x75ef5  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x75efa  ldarg.0
0x75efb  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x75f00  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x75f05  ldstr    aPrimaryname// "primaryname"
0x75f0a  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x75f0f  stloc.s  5
0x75f11  ldarg.0
0x75f12  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x75f17  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_Form()
0x75f1c  ldstr    aEntitydataxml// "entitydataxml"
0x75f21  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x75f26  stloc.s  6
0x75f28  ldnull
0x75f29  stloc.s  7
0x75f2b  ldtoken  [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest
0x75f30  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x75f35  newobj   instance void [System.Runtime.Serialization]System.Runtime.Serialization.DataContractSerializer::.ctor(class [mscorlib]System.Type)
0x75f3a  stloc.s  8
0x75f3c  newobj   instance void [mscorlib]System.IO.StringReader::.ctor(string)
0x75f41  stloc.s  0xA
0x75f43  ldloc.s  0xA
0x75f45  call     class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.XmlReader::Create(class [mscorlib]System.IO.TextReader)
0x75f4a  stloc.s  0xB
0x75f4c  ldloc.s  8
0x75f4e  ldloc.s  0xB
0x75f50  callvirt instance object [System.Runtime.Serialization]System.Runtime.Serialization.XmlObjectSerializer::ReadObject(class [System.Xml]System.Xml.XmlReader)
0x75f55  isinst   [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest
0x75f5a  stloc.s  7
0x75f5c  leave.s  loc_75F76
0x75f5e  ldloc.s  0xB
0x75f60  brfalse.s loc_75F69
0x75f62  ldloc.s  0xB
0x75f64  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x75f69  endfinally
0x75f6a  ldloc.s  0xA
0x75f6c  brfalse.s loc_75F75
0x75f6e  ldloc.s  0xA
0x75f70  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x75f75  endfinally
0x75f76  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x75f7b  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::get_Current()
0x75f80  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.ISecurityPrincipal::get_OrganizationId()
0x75f85  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.UserAndOrganizationContext::.ctor(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x75f8a  ldc.i4.m1
0x75f8b  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.ConversionContext::.ctor(class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext, int32)
0x75f90  ldloc.s  7
0x75f92  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::get_Parameters()
0x75f97  ldstr    aTarget_0// "Target"
0x75f9c  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0x75fa1  ldtoken  [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity
0x75fa6  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x75fab  call     object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.ConversionHelpers::Convert(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.ICrmConversionContext, object, class [mscorlib]System.Type)
0x75fb0  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity
0x75fb5  stloc.s  9
0x75fb7  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::get_Current()
0x75fbc  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser::get_SystemUserId()
0x75fc1  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::get_Current()
0x75fc6  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.ISecurityPrincipal::get_OrganizationId()
0x75fcb  call     void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.SerializationState::OnBeginRequest(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x75fd0  ldarg.0
0x75fd1  ldarg.0
0x75fd2  ldloc.s  9
0x75fd4  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::Serialize()
0x75fd9  ldloc.s  6
0x75fdb  ldloc.s  9
0x75fdd  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Metadata()
0x75fe2  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_PrimaryField()
0x75fe7  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_LogicalName()
0x75fec  ldloc.s  5
0x75fee  call     instance string Microsoft.Crm.Web.Tools.DuplicateDetection.ViewDuplicatesPage::AddEntityDataToEntityXml(string entityXml, string entityDataXml, string logicalName, string name)
0x75ff3  stfld    string Microsoft.Crm.Web.Tools.DuplicateDetection.ViewDuplicatesPage::formData
0x75ff8  leave.s  loc_76000
0x75ffa  call     void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.SerializationState::OnEndRequest()
0x75fff  endfinally
0x76000  ldarg.0
0x76001  ldc.i4.1
0x76002  stfld    bool Microsoft.Crm.Web.Tools.DuplicateDetection.ViewDuplicatesPage::isFromOutlook
0x76007  ldarg.0
0x76008  ldarg.0
0x76009  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x7600e  ldstr    aViewduplicates_6// "ViewDuplicates_aspx_BaseRecordsIframe_O"...
0x76013  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x76018  stfld    string Microsoft.Crm.Web.Tools.DuplicateDetection.ViewDuplicatesPage::baseRecordsFrameHeight
0x7601d  ldarg.0
0x7601e  ldarg.0
0x7601f  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x76024  ldstr    aViewduplicates_7// "ViewDuplicates_aspx_MyRecordLabel_Outlo"...
0x76029  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x7602e  stfld    string Microsoft.Crm.Web.Tools.DuplicateDetection.ViewDuplicatesPage::myRecordTextHeight
0x76033  ldarg.0
0x76034  ldfld    valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util/DuplicatesSource Microsoft.Crm.Web.Tools.DuplicateDetection.ViewDuplicatesPage::duplicatesSource
0x76039  ldc.i4.3
0x7603a  beq.s    loc_76048
0x7603c  ldarg.0
0x7603d  ldfld    valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util/DuplicatesSource Microsoft.Crm.Web.Tools.DuplicateDetection.ViewDuplicatesPage::duplicatesSource
0x76042  ldc.i4.5
0x76043  bne.un   loc_76145
0x76048  ldarg.0
0x76049  ldarg.0
0x7604a  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x7604f  ldstr    aOutlookSelecte// "Outlook_SelectedOfflineRecord_ViewDupli"...
0x76054  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x76059  stfld    string Microsoft.Crm.Web.Tools.DuplicateDetection.ViewDuplicatesPage::myRecordResourceString
  ... truncated ...
```
